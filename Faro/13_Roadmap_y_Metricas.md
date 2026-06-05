# 13 · Roadmap y Métricas

> *Una visión sin secuencia es un sueño; una secuencia sin métrica es ir a ciegas. Aquí está el cómo y el cómo sabemos que funciona.*

Este documento traza las fases de construcción de Faro (del MVP a la plataforma) y el sistema de métricas que dice si Faro cumple su misión.

---

## 1. Filosofía de construcción

1. **Profundidad antes que amplitud.** Un cuerpo y un núcleo excelentes antes que diez cuerpos mediocres (Doc 02 §7.1).
2. **El acompañamiento entra pronto.** Es el diferencial; no se deja "para la fase 2". Aunque sea simple al principio, debe estar desde el MVP.
3. **Cada fase entrega valor real al opositor.** Nada de seis meses construyendo en la oscuridad. Iteración con usuarios reales.
4. **Medir para cuidar, no para vigilar.** Las métricas guían el producto y demuestran la misión, nunca justifican dark patterns.

## 2. Roadmap por fases

### 🌑 Fase 0 — Fundamentos (preparar el terreno)
**Objetivo:** dejar listas las bases para construir bien.
- Sistema de diseño y tokens vivos (Doc 08); voz y guía de comunicación (Doc 09).
- Arquitectura base, modelo de datos núcleo, auth/roles (Doc 12).
- Modelado del **primer cuerpo beachhead** y carga inicial de su temario + corpus + banco verificado (Doc 07).
- **Entregable:** cimientos técnicos + contenido fiable de 1 cuerpo + identidad de marca.

### 🌒 Fase 1 — El MVP: "El núcleo que ya cuida"
**Objetivo:** un opositor real puede preparar su oposición con Faro de principio a fin, y sentirse acompañado.
- **Onboarding** que convierte caos en plan (Doc 10 §2).
- **El Hoy** + sesión de estudio diseñada (Doc 06 §6, Doc 10 §3).
- **Temario** estructurado con recuerdo activo (Doc 10 §4).
- **Banco de preguntas + repaso espaciado** (Doc 10 §5, Doc 06 §7).
- **Travesía** (plan vivo) con **re-planificación sin culpa** (Doc 06 §5).
- **Acompañamiento básico:** check-in, Vigía v1 (estados clave + respuestas), voz de Faro (Doc 05, Doc 09).
- **Seguimiento honesto** "¿voy bien?" (Doc 10 §6).
- Suscripción Free + Plus (Doc 03).
- **Entregable:** producto usable, con alma, para el cuerpo beachhead. → Validar adherencia y retención.

### 🌓 Fase 2 — Profundizar: "Mejor preparación, mejor cuidado"
**Objetivo:** subir la calidad del estudio y del acompañamiento con datos reales.
- **Simulacros** en condiciones reales + análisis de errores (Doc 06 §8, Doc 10 §5).
- **Vigía v2:** detección más fina de meseta/bache/sobre-exigencia; respuestas adaptadas a la persona (Doc 05 §3).
- **Cuaderno de Bitácora** y perspectiva del camino (Doc 10 §8).
- **Modo recta final** y guiones de momentos límite (Doc 09 §7, Doc 10 §6).
- Analítica de producto y panel Admin básico (Doc 11 §2).
- **Entregable:** la experiencia diferencial completa para 1 cuerpo. → Validar evitación de abandono y primeros aprobados.

### 🌔 Fase 3 — Crecer: "Más opositores, más cuerpos"
**Objetivo:** escalar la demanda y el catálogo.
- Añadir **cuerpos de la misma familia** (multi-oposición madura — Doc 07 §8).
- Pipeline de contenido robusto y herramientas Admin completas (Doc 11 §3).
- Optimización de conversión y retención; programa de **embajadores/aprobados** (Doc 03 §6).
- **Entregable:** Faro como producto de referencia en una familia de oposiciones.

### 🌕 Fase 4 — Plataforma: "Faro para todos"
**Objetivo:** abrir Faro a preparadores y academias (B2B2C).
- **Rol Preparador/Academia** completo: su contenido, sus alumnos, su analítica (Doc 11 §5).
- Multi-tenant maduro; gobernanza de calidad para terceros (Doc 12).
- Camino hacia marketplace de preparadores sobre Faro.
- **Entregable:** Faro como infraestructura del sector; el estándar de cómo se oposita.

```
Fase 0 ──► Fase 1 (MVP) ──► Fase 2 ──► Fase 3 ──► Fase 4
Bases     Núcleo que       Diferencial Escala      Plataforma
          ya cuida         completo    multi-cuerpo B2B2C
          ▲
          └── desde aquí ya hay acompañamiento: el alma entra pronto
```

## 3. El MVP, con más detalle (qué sí y qué no)

| Incluir en MVP | Dejar para después |
|----------------|---------------------|
| 1 cuerpo beachhead con contenido verificado | Catálogo amplio de cuerpos |
| El Hoy, Temario, banco + repaso espaciado | Simulacros avanzados con análisis profundo |
| Travesía + re-planificación sin culpa | Optimizaciones finas del algoritmo de plan |
| Check-in + Vigía v1 + voz de Faro | Vigía v2, Bitácora con perspectiva |
| Seguimiento "¿voy bien?" básico | Analítica avanzada y dashboards ricos |
| Free + Plus | B2B2C, preparadores |

> **Regla del MVP:** debe poder llevar a un opositor real desde el día 1 hasta el examen **y sostenerlo emocionalmente**, aunque de forma simple. Si quitamos el acompañamiento, deja de ser Faro y es "otra app de estudio".

## 4. Sistema de métricas

### 4.1 North Star
> **Opositores con preparación activa y saludable, semana a semana, hasta su examen** (Doc 01 §7).

"Activa" = estudia de verdad. "Saludable" = sin romperse. Las dos a la vez.

### 4.2 Métricas por capa

**Misión (las que de verdad importan)**
- **Tasa de aprobados entre usuarios activos** — la prueba final del valor.
- **Abandono de la oposición evitado** tras un bajón detectado por el Vigía.
- **Adherencia saludable** (cumple el plan *sin* señales de sobre-exigencia/burnout).

**Producto (predictores)**
- **Adherencia:** % de días con sesión vs. plan.
- **Retención por cohortes:** activos a 7 / 30 / 90 / 180 días.
- **Activación:** % que completa onboarding y hace ≥N sesiones la primera semana.
- **Uso del acompañamiento:** % que usa check-in/Bitácora; respuesta a intervenciones del Vigía.
- **Calidad de estudio:** retención del conocimiento (rendimiento en repaso/simulacro a lo largo del tiempo).

**Negocio (sostenibilidad)**
- **Conversión Free→Plus** y tiempo hasta conversión.
- **MRR/ARR** y crecimiento.
- **Churn** (distinguiendo el "buen churn" del aprobado — Doc 03 §3).
- **LTV/CAC.**

### 4.3 Cómo se leen las métricas (ética del dato)
- **La adherencia nunca se usa para culpar al opositor.** Es para ajustar el plan y activar el cuidado (Doc 06, Doc 05).
- **Las métricas de cuidado se agregan y anonimizan;** los datos sensibles individuales no se exponen (Manifiesto 7, Doc 11 §8).
- **Ninguna métrica justifica un dark pattern.** Si subir un número exige dañar al opositor, no se hace (Doc 03 §7).

## 5. Hipótesis a validar (qué tiene que ser cierto)

1. **El opositor valora el acompañamiento lo suficiente para pagar y quedarse** → medir retención y disposición a pagar de quienes usan el Vigía/Bitácora.
2. **El plan vivo + re-planificación sin culpa reduce el abandono** → comparar adherencia/retención con baseline.
3. **El Vigía detecta bajones a tiempo y la intervención los revierte** → medir abandono evitado.
4. **El contenido corpus-céntrico genera confianza** (pocos reportes de error, alta percepción de fiabilidad).
5. **El boca-oreja de aprobados baja el CAC** → medir referidos y origen de altas.

## 6. Definición de éxito (a 12–18 meses del MVP)

> Faro tiene éxito si, en su cuerpo beachhead, un número creciente de opositores **se prepara con Faro de forma activa y saludable hasta el examen, los aprobados empiezan a recomendarlo por su cuenta, y los que pasan por un bajón se quedan en lugar de abandonar.** Eso —no el MRR aislado— es la señal de que el faro ilumina de verdad.

---

### Resumen del documento

Faro se construye en cinco fases —**0 Fundamentos → 1 MVP "el núcleo que ya cuida" → 2 Profundizar → 3 Crecer (multi-cuerpo) → 4 Plataforma (B2B2C)**— con la regla de oro de que **el acompañamiento entra desde el MVP** (sin él no es Faro) y de profundidad antes que amplitud (un cuerpo excelente primero). Se mide con una **North Star** —opositores con preparación *activa y saludable* hasta el examen— y un sistema de métricas en tres capas: **misión** (tasa de aprobados, abandono evitado, adherencia saludable), **producto** (adherencia, retención, activación, uso del cuidado, retención del conocimiento) y **negocio** (conversión, MRR, churn distinguiendo el "buen churn", LTV/CAC). El dato se usa **para cuidar, nunca para culpar ni para dark patterns**. El éxito real: opositores que llegan al examen activos y enteros, aprobados que recomiendan, y bajones que no acaban en abandono.
