# 11 · Rol Administrador — Gestión del Negocio

> *La sala de máquinas de Faro. Donde se crea el contenido, se cuida a los alumnos, se opera el negocio y se mantiene encendida la luz.*

Este documento enumera **todas** las funcionalidades del rol Administrador: la cara profesional de Faro, usada por el equipo de Faro y —en el modelo B2B2C— por preparadores y academias (Doc 03 §5). Su diseño es la "segunda piel": misma marca, pero densa y eficiente, herramienta de trabajo (Doc 08 §10).

---

## 1. Mapa del panel de administración

```
┌──────────────────────────────────────────────────────────────────┐
│  FARO · Admin                                                     │
├──────────┬───────────┬───────────┬───────────┬───────────┬────────┤
│ CUADRO   │ CONTENIDO │ ALUMNOS   │ PREPARA-  │ NEGOCIO   │ SISTEMA│
│ DE MANDO │ (temarios)│           │ DORES     │ (suscrip.)│        │
└──────────┴───────────┴───────────┴───────────┴───────────┴────────┘
```

Seis áreas: **Cuadro de mando** (analítica), **Contenido** (temarios y banco), **Alumnos** (gestión y cuidado), **Preparadores** (B2B2C), **Negocio** (suscripciones, precios, marketing), **Sistema** (configuración, roles, seguridad).

## 2. Cuadro de mando (analítica del negocio y del cuidado)

La salud de Faro de un vistazo (métricas en Doc 13). Pilar de gestión: **decidir con datos**.

- **F-ADM-CM-1 · KPIs de negocio.** MRR/ARR, conversión Free→Plus, churn, LTV/CAC.
- **F-ADM-CM-2 · KPIs de producto.** Adherencia, retención por cohortes, uso por funcionalidad.
- **F-ADM-CM-3 · KPI de misión.** Tasa de aprobados entre activos; adherencia saludable (North Star, Doc 01 §7).
- **F-ADM-CM-4 · Salud del cuidado.** Indicadores agregados y anónimos de detección de bajones y abandono evitado (sin exponer datos íntimos individuales — Manifiesto 7).
- **F-ADM-CM-5 · Embudo.** De visita → registro → activación → pago → aprobado.
- **F-ADM-CM-6 · Alertas de negocio.** Caídas de retención, picos de churn, anomalías.

## 3. Gestión de contenido (temarios y banco) — el activo central

Operación del pipeline del Doc 07. Pilar de gestión: **crear y mantener el contenido**.

- **F-ADM-CO-1 · Catálogo de oposiciones.** Crear/configurar cuerpos: estructura de prueba, baremo, calendario (Doc 06 §3).
- **F-ADM-CO-2 · Ingesta de convocatorias y corpus.** Cargar bases, temario oficial y fuentes verificables (Doc 07 §4).
- **F-ADM-CO-3 · Editor estructurado de temario.** Crear/editar la jerarquía tema → epígrafe → concepto (Doc 07 §2).
- **F-ADM-CO-4 · Gestión del corpus.** Fuentes, versiones, vínculos contenido↔fuente (trazabilidad, Doc 07 §3).
- **F-ADM-CO-5 · Generador asistido de preguntas.** IA anclada al corpus propone; experto verifica (Doc 07 §4.1, conexión `faro-cowork-banco`).
- **F-ADM-CO-6 · Banco de preguntas.** Crear/editar test, casos, supuestos, desarrollo; con explicación del porqué y metadatos (Doc 07 §5).
- **F-ADM-CO-7 · Flujo de revisión y verificación.** Estados borrador → revisión → verificado → publicado; doble verificación de lo crítico (Doc 07 §6).
- **F-ADM-CO-8 · Versionado y publicación.** Publicar por convocatoria; migrar a alumnos con aviso (Doc 07 §7).
- **F-ADM-CO-9 · Detección de impacto normativo.** Ante cambio en el corpus, identificar contenido afectado → cola de revisión dirigida (Doc 07 §7).
- **F-ADM-CO-10 · Cola de reportes de alumnos.** Gestionar dudas/errores señalados por opositores (Doc 07 §6).
- **F-ADM-CO-11 · Etiquetado de peso/relevancia.** Marcar "lo que más cae" y dificultad para alimentar la priorización (Doc 06 §4).

## 4. Gestión de alumnos (con la ética de Faro)

Cuidar a los opositores también desde dentro. Pilar de gestión: **soporte y cuidado**.

- **F-ADM-AL-1 · Directorio de alumnos.** Buscar, filtrar, ver estado de preparación (con privacidad: nunca exponer el contenido íntimo de la Bitácora — Manifiesto 7).
- **F-ADM-AL-2 · Soporte y tickets.** Atender consultas; historial de soporte.
- **F-ADM-AL-3 · Salud de la cohorte.** Detección agregada de alumnos en riesgo de abandono para acciones de cuidado (no comerciales en bajón — Doc 03 §6).
- **F-ADM-AL-4 · Gestión de incidencias de cuenta.** Accesos, pagos, datos, derecho a exportar/borrar (privacidad, Doc 12).
- **F-ADM-AL-5 · Comunicación responsable.** Envío de comunicaciones bajo las reglas de voz y notificación (Doc 09) — nunca presión ni alarma.

## 5. Gestión de preparadores y academias (B2B2C)

La capa que convierte a Faro en plataforma (Doc 02 §7.3, Doc 03 §5). Pilar de gestión: **escalar como plataforma**.

- **F-ADM-PR-1 · Alta de preparadores/academias.** Cuentas, permisos, espacios de contenido propios.
- **F-ADM-PR-2 · Su contenido.** Que suban/gestionen su temario y banco, con el mismo flujo de calidad (Doc 07).
- **F-ADM-PR-3 · Sus alumnos.** Planificar, ver analítica y apoyarse en el sistema de acompañamiento de Faro.
- **F-ADM-PR-4 · Su analítica.** Cuadro de mando del preparador: adherencia y avance de *sus* alumnos.
- **F-ADM-PR-5 · Liquidaciones / modelo.** Licencia por alumno, revenue share o plan academia (Doc 03 §5).
- **F-ADM-PR-6 · Gobernanza de calidad.** Faro mantiene estándares de contenido también para terceros (la marca lo exige).

## 6. Negocio: suscripciones, precios y crecimiento

Operar el modelo del Doc 03. Pilar de gestión: **sostenibilidad**.

- **F-ADM-NE-1 · Planes y precios.** Configurar Free/Plus/Pro/B2B2C; cambios y experimentos de precio.
- **F-ADM-NE-2 · Suscripciones y pagos.** Estado de suscripciones, cobros, reembolsos, dunning amable.
- **F-ADM-NE-3 · Cupones y campañas.** Promociones, becas/descuentos sociales (coherentes con la misión).
- **F-ADM-NE-4 · Gestión del "egreso celebrado".** Flujos de baja por aprobado, captura de historias, programa embajadores (Doc 03 §6).
- **F-ADM-NE-5 · Estados especiales.** Pausa sin convocatoria, segunda vuelta (no cobrar valor no entregado — Doc 03 §6).
- **F-ADM-NE-6 · Marketing de marca.** Gestión de contenido de marca/landing con la voz del Faro (Doc 09).

## 7. Sistema: configuración, roles y seguridad

La base operativa. Pilar de gestión: **fiabilidad y confianza**.

- **F-ADM-SI-1 · Roles y permisos.** Admin, editor de contenido, soporte, preparador, etc. (RBAC, Doc 12).
- **F-ADM-SI-2 · Gobernanza de la IA.** Configurar y auditar reglas del Vigía, generador de preguntas y voz (límites, prohibiciones, derivación — Docs 05, 07, 09).
- **F-ADM-SI-3 · Privacidad y cumplimiento.** Gestión de consentimientos, RGPD, exportación/borrado, retención de datos (Doc 12).
- **F-ADM-SI-4 · Auditoría.** Registro de cambios en contenido y acciones sensibles (trazabilidad).
- **F-ADM-SI-5 · Salud técnica.** Estado del sistema, incidencias, rendimiento (enlazado a Doc 12).
- **F-ADM-SI-6 · Configuración del producto.** Parámetros del método, notificaciones por defecto, feature flags.

## 8. Principios de diseño del Admin

- **Eficiencia sobre serenidad.** A diferencia del estudiante, el Admin es una herramienta de trabajo: tablas densas, filtros, atajos, acciones masivas. Sereno y elegante, pero optimizado para *hacer*, no para *calmar* (Doc 08 §10).
- **La privacidad del opositor manda incluso aquí.** El Admin nunca accede al contenido íntimo (Bitácora, check-ins individuales detallados). Trabaja con lo necesario para operar y cuidar, no con lo sagrado (Manifiesto 7).
- **La misión gobierna el negocio.** Cada herramienta de negocio respeta las líneas rojas (Doc 03 §7): sin monetizar la ansiedad, sin presión en la fragilidad.
- **Calidad de contenido innegociable.** El flujo de verificación no se puede saltar, ni siquiera por prisa (Doc 07 §6).

## 9. Resumen de funcionalidades por área

| Área | Funcionalidades clave |
|------|------------------------|
| **Cuadro de mando** | KPIs de negocio, producto y misión; salud del cuidado; alertas |
| **Contenido** | Catálogo de oposiciones, ingesta, editor de temario, corpus, generador de preguntas, verificación, versionado, reportes |
| **Alumnos** | Directorio, soporte, salud de cohorte, incidencias, comunicación responsable |
| **Preparadores (B2B2C)** | Altas, su contenido, sus alumnos, su analítica, modelo económico, calidad |
| **Negocio** | Planes/precios, suscripciones/pagos, campañas, egreso celebrado, marketing |
| **Sistema** | Roles/permisos, gobernanza IA, privacidad/RGPD, auditoría, salud técnica |

---

### Resumen del documento

El rol Administrador es la sala de máquinas de Faro, organizada en seis áreas: **Cuadro de mando** (KPIs de negocio, producto y misión, incluida la salud del cuidado), **Contenido** (todo el pipeline de temarios y banco corpus-céntrico del Doc 07, con verificación humana innegociable), **Alumnos** (soporte y cuidado con privacidad sagrada), **Preparadores** (la capa B2B2C que convierte a Faro en plataforma), **Negocio** (suscripciones, precios, egreso celebrado y crecimiento bajo las líneas rojas del Doc 03) y **Sistema** (roles, gobernanza de la IA, privacidad/RGPD, auditoría). Su diseño es la "segunda piel": densa y eficiente como herramienta de trabajo, pero atada a la misión —la privacidad del opositor y las líneas rojas mandan también aquí.
