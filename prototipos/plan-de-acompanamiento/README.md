# Prototipo · Plan de Acompañamiento

> Rediseño de alta fidelidad de la pantalla **Plan de Acompañamiento** (Mi Travesía) de Faro.
> Un preparador que te conoce y te planifica el estudio a **corto, medio y largo plazo**.

**Abre [`index.html`](index.html) en cualquier navegador.** Es autocontenido (sin build, sin dependencias) — solo carga las fuentes desde Google Fonts.

| Modo oscuro (por defecto) | Modo claro |
|---|---|
| ![Modo oscuro](preview-dark.png) | ![Modo claro](preview-light.png) |

---

## Qué es esto

Un prototipo navegable que materializa la promesa de Faro —*"rigor de preparador, experiencia de calma"*— en la pantalla donde vive el plan de estudio. No es un mockup estático: tiene tema claro/oscuro, check-in emocional interactivo, animaciones que respiran y diseño responsive.

El concepto central, según el encargo: **el preparador no te da una lista infinita, te sostiene tres horizontes a la vez** — el siguiente paso (corto), el rumbo del mes (medio) y la foto completa hasta el examen (largo).

## Anatomía de la pantalla

1. **Hero + Gantt protagonista** — Titular editorial, un **mensaje personalizado del preparador** (la presencia de Faro, Doc 09) y las métricas clave; debajo, **el Gantt de la Travesía ocupa el lugar de honor** como primera vista de la pantalla.
2. **El Gantt de la Travesía** — La vista de trabajo y centro de la pantalla: bloques del temario, repaso espaciado, simulacros y recta final repartidos **semana a semana** hasta el examen, con la línea de **"Hoy"**. Es el "corto/medio/largo plazo" en una sola foto temporal. Sereno y sin tareas en rojo. Es **interactivo**:
   - **Tooltips** en cada barra, simulacro y celda (detalle, dominio, fechas, notas estimadas).
   - **Zoom Meses ↔ Semanas** para bajar al detalle del corto plazo.
   - **Re-planificación viva** — el botón *"Tuve una semana floja"* recoloca el plan con animación y la voz de Faro (Doc 06 §5.3): el bloque en curso se alarga y el colchón de recta final se ajusta, pero **el examen no se mueve**. Sin culpa, cero rojos.
   - **Carga semanal vs. tu disponibilidad** — una banda muestra las horas planificadas por semana frente a tu tope real; las semanas cargadas se avisan en ámbar templado *antes* de que rompan el plan (Doc 06 §5.3, "avisar de riesgos a tiempo").
3. **Los tres horizontes** — Tres tarjetas (corto / medio / largo plazo), cada una con su línea de horizonte, sus ítems con estado de dominio sutil (*En camino · A repasar · Dominado*) y su progreso sereno. La luz es más cercana en "corto" y más lejana en "largo".
4. **El Hoy** — Una sola decisión, una sola acción primaria (el botón "de la luz"), con la sesión flexible del día (Doc 06 §5.2).
5. **Check-in emocional** — "¿Cómo llegas hoy?": un gesto que adapta la sesión y responde con la voz de Faro (Doc 05 §4). **Interactivo.**
6. **¿Voy bien? — el seguimiento honesto** — La respuesta a la pregunta crónica del opositor (Doc 10 F-TRA-3), con cuatro métricas de valor: **dominio por bloque**, **proyección a examen** (gauge de cobertura prevista + confianza calibrada), **repaso espaciado de la semana** (qué vuelve y retención) y **constancia** (heatmap sereno que no castiga los huecos).
7. **Hitos + Una palabra de Faro** — Línea de tiempo sin culpa (cero rojo de tareas vencidas) y el panel de acompañamiento con control de intensidad (Doc 05 §3.3).

## Tour guiado por la app

El botón **"Faro te enseña tu plan"** (abajo a la derecha) inicia un recorrido con *spotlight*: Faro, con su voz (Doc 09), te presenta cada zona en cinco pasos (Gantt → tres horizontes → El Hoy → check-in → ¿voy bien?). Navegable con ratón o teclado (← → Esc). Es la traducción del onboarding F-ON ("Encender el faro") a una bienvenida cálida en vez de un formulario.

## Responsive (móvil · tablet · escritorio)

Diseñado **móvil-first** (Doc 08 §9). En móvil el header colapsa a lo esencial, el copy y el mensaje del preparador se apilan sobre el Gantt, las tarjetas se apilan, el botón principal ocupa el ancho, el Gantt se desliza en horizontal y el tour se adapta al viewport. El tablet usa un punto intermedio. Ver capturas en `preview-*` y en el PR.

## Cómo respeta el Sistema de Diseño (Doc 08)

| Principio del Doc 08 | Cómo se aplica aquí |
|---|---|
| **Noche serena** (lienzo azul noche, no negro) | Fondo `#0B1322`/`#131F35`, modo oscuro como experiencia central |
| **La luz** (acento cálido y escaso) | Ámbar `#F2B65A` reservado a "lo siguiente", logros y *una sola* acción primaria por pantalla |
| **Nunca rojo de alarma** | Lo pendiente/a repasar usa ámbar templado y teal sereno; la línea de hitos no acumula culpa visual |
| **Calidez profesional** | Tipografía editorial (Fraunces serif + Inter), nada infantil ni estridente |
| **El pulso del faro** | Micro-animaciones que respiran (haz, glow, nodo "Hoy"), nunca nerviosas |
| **Espacio que respira** | Escala 4/8, márgenes generosos, "una pantalla, una intención" |
| **Accesibilidad** | Contraste AA, navegable por teclado, estados no solo por color, **`prefers-reduced-motion` respetado** |
| **Móvil-first responsive** | Las columnas colapsan con elegancia; la escena pasa arriba en móvil |

La voz de los textos sigue el Doc 09: tú cercano, verbos de avance, validar antes de dirigir, **cero culpa**, breve.

## Stack

HTML + CSS + un toque de JS vainilla, sin frameworks, para que sea fácil de revisar y portar. La dirección técnica del producto (Doc 12) recomienda React/Next.js con design tokens; **las variables CSS de este prototipo (`:root`) son directamente esos tokens** y pueden migrarse tal cual a la librería de componentes.

## Regenerar las capturas

```bash
# requiere el Chromium preinstalado del entorno
node scripts/shot.mjs   # (script de ejemplo; ver historial del PR)
```
