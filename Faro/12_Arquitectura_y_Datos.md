# 12 · Arquitectura y Datos

> *Cómo se construye Faro por dentro para que por fuera se sienta sencillo, fiable y sereno.*

Este documento traza la arquitectura técnica, el stack, el modelo de datos y el papel de la IA. Es una guía de dirección, no un contrato cerrado: fija decisiones y principios, deja libertad de implementación.

---

## 1. Principios de arquitectura

1. **Sencillez antes que sofisticación.** La complejidad técnica es deuda; se asume solo cuando aporta valor real al opositor.
2. **Móvil-first, web responsive.** Una sola base que sirve la mejor experiencia en móvil y escritorio (Doc 08 §9), con posibilidad futura de empaquetar como app.
3. **El método y el contenido como núcleo de dominio.** La planificación, el repaso y el modelo de oposición son el corazón; lo demás (auth, pagos) es infraestructura.
4. **IA como capacidad de servicio, no como dependencia frágil.** La IA mejora el cuidado y el contenido, pero el producto funciona y es fiable; los fallos de IA degradan con gracia, no rompen.
5. **Privacidad y seguridad por diseño.** Los datos emocionales son sagrados (Manifiesto 7); el sistema los protege como requisito, no como añadido.
6. **Preparado para escalar por cuerpos.** Multi-oposición y multi-tenant (B2B2C) desde el modelo de datos.

## 2. Stack tecnológico (dirección recomendada)

Coherente con la elección de **app web** y el uso de **TypeScript** (los repos `Proyecto-Faro` y `faro-cowork-banco` ya son TS):

| Capa | Recomendación | Por qué |
|------|---------------|---------|
| **Lenguaje** | **TypeScript** end-to-end | Un solo lenguaje front+back; tipado que da fiabilidad; ya es el stack del proyecto |
| **Front** | Framework web moderno (React/Next.js o similar) | SSR/SEO para marca, gran ecosistema, PWA para experiencia móvil-first |
| **Estilos / UI** | Sistema de design tokens + librería de componentes propia (Doc 08) | Coherencia de marca, modo claro/oscuro, accesibilidad |
| **Back** | API en TypeScript (Node) | Mismo lenguaje, lógica de dominio compartida |
| **Datos** | Base relacional (PostgreSQL) | El modelo es muy relacional (temarios, progreso, suscripciones); integridad y consultas ricas |
| **Búsqueda/IA de contenido** | Índice + embeddings sobre el corpus | Soporta el banco corpus-céntrico y la trazabilidad (Doc 07) |
| **IA** | Modelos de lenguaje vía API, con orquestación propia | Vigía, voz, generación de preguntas anclada al corpus (§6) |
| **Infra** | Cloud gestionado, infra como código | Fiabilidad, escalado, despliegue reproducible |
| **Pagos** | Pasarela de suscripciones establecida | No reinventar cobros; cumplimiento |

> Recomendación de modelo de IA: usar **modelos Claude de Anthropic** (familia 4.x — p. ej. Opus para razonamiento de contenido/cuidado fino y un modelo más rápido para interacciones ligeras), por su calidad en tareas de lenguaje sensible y seguimiento de instrucciones de seguridad. La arquitectura debe permitir cambiar/mezclar proveedores sin reescribir el dominio.

> **Nota:** el stack es una recomendación de partida. La regla manda: sencillez, fiabilidad, TypeScript, y no acoplar el dominio a ninguna pieza concreta.

## 3. Arquitectura lógica (vista de alto nivel)

```
┌──────────────────────────────────────────────────────────────┐
│  CLIENTES                                                     │
│  · Web Estudiante (PWA, móvil-first)   · Web Admin           │
└───────────────┬──────────────────────────────────────────────┘
                │  API
┌───────────────▼──────────────────────────────────────────────┐
│  SERVICIOS DE DOMINIO                                         │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐ │
│  │ Planifica- │ │ Estudio +  │ │ Acompaña-  │ │ Contenido  │ │
│  │ ción       │ │ Repaso     │ │ miento     │ │ + Corpus   │ │
│  │ (Travesía) │ │ (SR engine)│ │ (Vigía)    │ │ (temarios) │ │
│  └────────────┘ └────────────┘ └────────────┘ └────────────┘ │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐                │
│  │ Identidad  │ │ Suscrip-   │ │ Analítica  │   + Capa IA    │
│  │ + Roles    │ │ ciones     │ │ + Métricas │   (orquestada) │
│  └────────────┘ └────────────┘ └────────────┘                │
└───────────────┬──────────────────────────────────────────────┘
                │
┌───────────────▼──────────────────────────────────────────────┐
│  DATOS:  PostgreSQL  ·  Índice/embeddings del corpus  ·       │
│          almacenamiento seguro de datos sensibles             │
└──────────────────────────────────────────────────────────────┘
```

## 4. Dominios y sus responsabilidades

- **Planificación (Travesía):** genera y re-planifica el plan vivo a partir de temario + fecha + horas + estado (Doc 06 §5).
- **Estudio + Repaso (motor SR):** estado de dominio por concepto, programación de repaso espaciado, selección del "Hoy" (Doc 06 §6–7).
- **Acompañamiento (Vigía):** ingiere señales, estima estado, dispara intervenciones y voz (Doc 05). Bajo gobernanza y límites (Doc 11 §7).
- **Contenido + Corpus:** modelo de oposición, temarios versionados, banco de preguntas, trazabilidad a fuentes (Doc 07).
- **Identidad + Roles:** auth, RBAC (estudiante, admin, editor, soporte, preparador), multi-tenant para B2B2C.
- **Suscripciones:** planes, pagos, estados especiales, egreso celebrado (Doc 03).
- **Analítica + Métricas:** KPIs de negocio, producto y misión (Doc 13), con separación estricta de datos sensibles.

## 5. Modelo de datos (entidades núcleo)

> Esquema conceptual; los detalles se afinan en implementación.

**Contenido / oposición**
- `Oposicion` (cuerpo): estructura de prueba, baremo, calendario.
- `Temario` (versión ligada a convocatoria) → `Tema` → `Epigrafe` → `Concepto` (unidad atómica).
- `FuenteCorpus`: textos legales/manuales versionados; vínculo `Concepto`/`Pregunta` ↔ `FuenteCorpus` (trazabilidad).
- `Pregunta`: tipo (test/caso/supuesto/desarrollo), enunciado, solución, **explicación del porqué**, dificultad, peso, estado de verificación, concepto asociado.

**Usuario / preparación**
- `Usuario` (con rol) · `PerfilOpositor`: oposición elegida, fecha de examen, disponibilidad (patrón semanal), "su porqué".
- `Travesia` (plan vivo) → `SesionPlanificada` (el "Hoy" y futuros).
- `EstadoDominio` (por usuario × concepto): nivel de dominio, próxima fecha de repaso.
- `RegistroEstudio`: sesiones realizadas, tiempo, resultados.
- `IntentoPregunta`: respuesta, acierto/fallo, tiempo → alimenta SR y métricas.
- `Simulacro` + `ResultadoSimulacro`: nota, análisis de errores.

**Acompañamiento (datos sensibles, protegidos aparte)**
- `CheckIn`: estado declarado (con consentimiento).
- `EntradaBitacora`: diario privado (cifrado/aislado, acceso ultra-restringido — Manifiesto 7).
- `EstadoVigia`: estimación del estado emocional/conductual; histórico para adaptar.

**Negocio**
- `Suscripcion`, `Plan`, `Pago`, `Cupon`.
- `Preparador`/`Academia` (tenant) y su relación con `Usuario` y `Contenido` (B2B2C).

> **Diseño con privacidad:** los datos de `Acompañamiento` (Bitácora, check-ins, estados del Vigía) viven con **aislamiento y control de acceso reforzados**, separados de los datos operativos, y **nunca** se exponen al Admin de forma individual identificable (Doc 11 §8).

## 6. La capa de IA (orquestada y con red de seguridad)

La IA sirve a tres funciones, todas **gobernadas** (Doc 11 §7):

1. **Vigía (acompañamiento):** estima estado y compone mensajes **bajo las reglas de voz y los límites de seguridad** (Docs 05, 09). Si la IA falla, Faro recurre a respuestas seguras predefinidas: **degrada con gracia**, nunca dice algo dañino.
2. **Generación de contenido (corpus-céntrico):** propone explicaciones y preguntas **ancladas al corpus y citando fuentes**; siempre pasan por verificación humana (Doc 07 §4.1). La IA nunca publica sola.
3. **Voz y microcopy adaptativo:** redacta mensajes contextualizados respetando el sistema de comunicación (Doc 09).

Principios de la capa IA:
- **Anclaje al corpus** (recuperación sobre fuentes) para contenido: reduce errores y da trazabilidad.
- **Barandillas de seguridad** explícitas: prohibición de culpar, de frases vacías, protocolo de derivación ante riesgo (Doc 05 §8). Probadas y auditadas.
- **Independencia de proveedor:** la lógica de dominio no se acopla a un modelo concreto.
- **Privacidad:** los datos sensibles se manejan con el mínimo necesario y bajo consentimiento; nunca se usan para fines ajenos al cuidado del propio opositor.

## 7. Seguridad y privacidad (requisito, no añadido)

- **RGPD por diseño:** consentimiento granular, derecho a acceso/exportación/borrado (Doc 10 F-CFG-4, Doc 11 F-ADM-SI-3).
- **Cifrado** en tránsito y en reposo; refuerzo extra para datos de acompañamiento.
- **Minimización:** se recoge solo lo que sirve para cuidar y enseñar mejor.
- **RBAC y auditoría:** acceso por rol, registro de acciones sensibles (Doc 11 §7).
- **No monetización de datos sensibles:** prohibido a nivel de arquitectura y de política (Doc 03 §7).
- **Resiliencia:** copias de seguridad, recuperación, y la promesa al opositor de que **su progreso está a salvo** (Doc 09 §5).

## 8. Calidad, entrega y operación

- **Tipado fuerte** (TypeScript) como primera línea de fiabilidad.
- **Pruebas** del dominio crítico: motor de repaso, re-planificación sin culpa, **barandillas de la IA de acompañamiento** (lo más sensible) y verificación de contenido.
- **Observabilidad:** salud técnica y de producto (Doc 11 F-ADM-SI-5), con métricas (Doc 13).
- **Despliegue reproducible** (infra como código) y entornos separados.
- **Feature flags** para liberar funciones de forma gradual y segura.

## 9. Evolución arquitectónica (alineada al roadmap, Doc 13)

- **MVP:** un núcleo bien hecho (planificación + estudio/repaso + acompañamiento básico + contenido de 1 cuerpo) sobre arquitectura sencilla. No sobre-ingeniería.
- **Crecimiento:** más cuerpos (multi-oposición), afinado de IA del Vigía y del plan, métricas ricas.
- **Plataforma:** multi-tenant maduro para B2B2C, herramientas de preparador, marketplace.

---

### Resumen del documento

Faro se construye **TypeScript end-to-end**, web responsive móvil-first (PWA), sobre una base **PostgreSQL** muy relacional, con principios de **sencillez, fiabilidad, privacidad por diseño y escalado por cuerpos**. Su arquitectura separa dominios claros —**Planificación (Travesía), Estudio+Repaso (motor SR), Acompañamiento (Vigía), Contenido+Corpus**, más identidad/roles, suscripciones y analítica— y un **modelo de datos** que aísla con celo los **datos sensibles** del acompañamiento (Bitácora, check-ins, estado del Vigía), nunca expuestos individualmente al Admin. La **capa de IA** está orquestada y gobernada: ancla el contenido al corpus (con verificación humana), compone la voz bajo barandillas de seguridad, y **degrada con gracia** sin decir nada dañino. Seguridad, RGPD y resiliencia son requisitos, no añadidos, y la arquitectura evoluciona del **MVP** sencillo hacia la **plataforma** B2B2C siguiendo el roadmap (Doc 13).
