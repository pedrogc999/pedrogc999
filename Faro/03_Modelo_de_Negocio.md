# 03 · Modelo de Negocio

> *Faro debe ser sostenible para poder cuidar a largo plazo. Un faro apagado no guía a nadie.*

Este documento responde: ¿cómo gana dinero Faro sin traicionar su misión? Precios, planes, unit economics y la gestión del negocio (que se opera desde el rol Admin, Doc 11).

---

## 1. Principio económico rector

> **El modelo de negocio nunca debe entrar en conflicto con el bienestar del opositor.**

Esto descarta de raíz: vender los datos emocionales, oscurecer el progreso para crear enganche ansioso, dark patterns para retener, o cobrar por funciones de seguridad emocional. Faro gana **cuando el opositor avanza sano**, no cuando sufre. La alineación de incentivos es parte del producto.

## 2. Modelo principal: suscripción (freemium → premium)

El opositor ya está acostumbrado a gastar en su preparación (academia, libros, apps). Faro captura una fracción de ese gasto a cambio de hacerlo todo mejor y en un sitio.

### 2.1 Niveles

| Plan | Precio orientativo | Para quién | Qué incluye |
|------|--------------------|-----------|-------------|
| **Faro Free** | 0 € | Quien empieza / prueba | Plan básico, acceso limitado al temario, test diario limitado, check-in emocional básico, seguimiento esencial |
| **Faro Plus** | ~9–15 €/mes | El opositor serio (núcleo del negocio) | Plan vivo completo, temario completo de su cuerpo, banco de preguntas y simulacros ilimitados, repaso espaciado, seguimiento avanzado, acompañamiento emocional completo |
| **Faro Pro / Anual** | ~descuento anual | El comprometido a largo plazo | Todo Plus + descuento por compromiso anual (alineado con la duración real de una oposición) + funciones avanzadas (informes, exportación, prioridad) |
| **Faro con Preparador** (B2B2C) | variable | Quien va con academia/preparador | Faro como plataforma del preparador; lo paga el alumno o la academia (ver §5) |

> Los precios son hipótesis a validar. Principio: **por debajo del coste mensual de una academia**, claramente, para que Faro sea un "sí" fácil.

### 2.2 Filosofía freemium

- **El Free es generoso de verdad**, no un trozo inútil. Debe permitir empezar a opositar con Faro y enamorarse del método.
- **Nunca se paga por el cuidado emocional básico.** El check-in y el apoyo en un bajón fuerte no se ponen tras un muro de pago: sería contrario al manifiesto. El premium está en la *profundidad* del estudio (temario completo, simulacros ilimitados, analítica avanzada), no en la *seguridad de la persona*.
- **El salto a Plus se gana, no se fuerza.** Cuando el opositor ve que Faro le orienta y le sostiene, pagar es natural.

## 3. Unit economics (marco)

> Números a modelar con datos reales; aquí el marco para razonarlos.

- **ARPU** (ingreso medio por usuario) = mezcla de Free (0) y de pago. Palanca: tasa de conversión Free→Plus.
- **LTV** (valor de vida): clave que una oposición dura **meses o años** → si Faro retiene durante toda la travesía, el LTV es alto (12–36+ meses de suscripción). La retención es el motor del LTV, y la retención la produce el **acompañamiento** (foso emocional, Doc 02).
- **CAC** (coste de adquisición): minimizado por boca-oreja de aprobados y contenido de marca (Doc 02 §7). Cada aprobado reduce el CAC efectivo.
- **Regla de oro:** LTV/CAC saludable se logra **reteniendo bien**, no captando barato. Por eso el cuidado emocional no es solo ética: es la mejor estrategia de retención posible.
- **Churn:** el enemigo. Dos tipos: (a) churn por abandono de la oposición —Faro lo combate con acompañamiento— y (b) churn por aprobar —¡el "buen churn"! El que aprueba se va feliz y nos recomienda. Diseñar un "egreso celebrado" (ver §6).

## 4. Métricas de negocio que importan (detalle en Doc 13)

- **Conversión Free → Plus** (y tiempo hasta conversión).
- **Retención por cohortes** (30/90/180 días) — la métrica reina del modelo de suscripción.
- **Adherencia** (días activos vs. plan) — predice retención y aprobados.
- **MRR / ARR** y su crecimiento.
- **Tasa de aprobados entre usuarios activos** — la métrica que justifica el precio y alimenta el boca-oreja.

## 5. Modelo B2B2C: Faro para preparadores y academias

Una segunda fuente de ingresos y un acelerador de distribución: **preparadores y academias usan Faro como su plataforma** (rol Admin, Doc 11).

- El preparador sube/gestiona su temario y banco, planifica a sus alumnos, ve su analítica y se apoya en el sistema emocional de Faro.
- Modelos posibles: **licencia por alumno activo**, **revenue share**, o **plan academia** con cupos.
- Ventaja estratégica: convierte a competidores potenciales (academias) en **canal y en clientes**, y aporta a Faro contenido y alumnos. Es el paso a "plataforma" (Doc 02 §7.3).

## 6. Momentos económicos delicados (tratados con ética)

| Momento | Tentación comercial | Decisión Faro |
|---------|---------------------|----------------|
| Opositor en bajón fuerte | Empujar upsell "para motivarte" | **Prohibido.** En un bajón, cero presión comercial. Solo cuidado. |
| Opositor que aprueba | Retenerlo con fricción | **Egreso celebrado:** felicitarle, facilitar la baja, pedirle su historia, ofrecer modo "ex-alumno" embajador. El buen churn se honra. |
| Opositor que suspende y vuelve a intentarlo | — | Acompañamiento especial de "segunda vuelta": es un momento de máxima fragilidad y máxima lealtad si se cuida bien. |
| Periodo sin convocatoria | Cobrar igual sin valor | Plan "en pausa" o reducido: no cobrar valor que no se entrega. |

## 7. Lo que NO monetizamos (líneas rojas)

- **Los datos emocionales del opositor.** Nunca, bajo ningún modelo. (Manifiesto, principio 7.)
- **La ansiedad.** No hay mecánicas diseñadas para crear enganche ansioso.
- **La comparación.** Nada de rankings públicos pay-to-win que humillen.
- **El miedo.** No se vende con "si no pagas, suspenderás".

## 8. Cómo se gestiona el negocio en el producto (puente al rol Admin)

Todo lo anterior se **opera** desde el rol Administrador (Doc 11): gestión de planes y precios, suscripciones y pagos, cupones y campañas, cuadro de mando de MRR/retención/conversión, gestión de preparadores y academias, y soporte. El negocio no es un PDF aparte: vive como funcionalidad dentro de Faro.

---

### Resumen del documento

Faro se sostiene con **suscripción freemium** (Free generoso → Plus/Anual), donde el premium está en la profundidad del estudio y nunca en la seguridad emocional. La retención —producida por el acompañamiento— es el motor del LTV y la mejor estrategia del modelo. Una segunda línea **B2B2C** convierte a academias y preparadores en canal y clientes. Hay líneas rojas innegociables (no monetizar datos emocionales, ansiedad, comparación ni miedo) y momentos delicados gestionados con ética (bajón sin upsell, "egreso celebrado" al aprobar). Todo se opera desde el rol Admin (Doc 11) y se mide con las métricas del Doc 13.
