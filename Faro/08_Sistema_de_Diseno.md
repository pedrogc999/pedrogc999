# 08 · Sistema de Diseño (UI/UX)

> *La calma es diseño. Cada pantalla, color y espacio debe restar tensión al opositor, no sumarla.*

Este documento define el lenguaje visual y de interacción de Faro, desde la filosofía hasta los tokens concretos. Escrito desde el rol de experto UX/UI. Es la base material de la promesa "sencilla, elegante, precisa, profesional".

---

## 1. Filosofía de diseño

> El opositor ya vive en ansiedad. **Faro debe sentirse como entrar en un espacio sereno y ordenado**, no en un panel de control que abruma. La estética no es decoración: es terapéutica. La calma es una funcionalidad.

Cuatro principios visuales, derivados de los principios rectores (README §5):

1. **Serenidad** — espacio en blanco generoso, paleta sobria, cero estridencia. El silencio visual es lujo.
2. **Claridad** — una jerarquía obvia; en cada pantalla, una sola acción principal evidente.
3. **Calidez profesional** — serio pero humano; cálido sin ser infantil; elegante sin ser frío.
4. **Foco** — la interfaz desaparece para que el opositor piense en el estudio, no en la app.

### Anti-patrones prohibidos
- ❌ Rojos agresivos para "tareas atrasadas", contadores que culpan, números que gritan.
- ❌ Gamificación estridente (confeti, insignias chillonas, rankings públicos).
- ❌ Densidad de dashboard tipo "panel de trading".
- ❌ Estética infantil (mascotas bobas, colores de caramelo) — Faro es para una meta seria.
- ❌ Notificaciones ansiosas ("¡Llevas 2 días sin estudiar!").

## 2. La metáfora visual del faro

El lenguaje visual nace del faro y el mar nocturno sereno:

- **La luz** — el acento de Faro: un haz cálido que guía. Se usa con moderación, para señalar "lo siguiente", el progreso, los momentos de logro. La luz es preciosa porque es escasa.
- **La noche serena** — el lienzo: tonos profundos, calmados (azules nocturnos, no negros duros), que descansan la vista y permiten que la luz destaque. Ideal también para estudiar de noche (cuando muchos opositores trabajan).
- **El horizonte** — la dirección: composiciones limpias, horizontales, que sugieren rumbo y avance.
- **El pulso de la luz** — el ritmo: micro-animaciones suaves, que respiran, nunca nerviosas.

## 3. Color (tokens)

> Valores orientativos para fijar la dirección; se afinan en implementación. Pensado para **modo claro y modo oscuro** (el oscuro no es un extra: es central por el estudio nocturno y la serenidad).

### Paleta base — "Noche serena"
| Token | Rol | Aprox. |
|-------|-----|--------|
| `--faro-deep` | Fondo oscuro principal (azul noche, no negro) | `#0E1726` |
| `--faro-deep-2` | Superficies elevadas en oscuro | `#16223A` |
| `--faro-mist` | Fondo claro principal (blanco cálido, no puro) | `#F7F8FA` |
| `--faro-mist-2` | Superficies en claro | `#FFFFFF` |
| `--faro-ink` | Texto principal | `#1A2233` / claro: casi-negro cálido |
| `--faro-ink-soft` | Texto secundario | gris azulado suave |

### Acento — "La luz"
| Token | Rol | Aprox. |
|-------|-----|--------|
| `--faro-light` | Acento principal: el haz cálido (ámbar/dorado suave) | `#F2B65A` |
| `--faro-light-warm`| Variante cálida para logros y calidez | `#F0A24B` |
| `--faro-guide` | Acento secundario sereno (azul-verde calmado) para info/rumbo | `#5BB6C9` |

### Semánticos (suaves, nunca agresivos)
| Token | Rol | Nota |
|-------|-----|------|
| `--faro-ok` | Logro / acierto | verde sereno, no neón |
| `--faro-care` | Atención / a revisar | **ámbar templado, NO rojo de alarma** |
| `--faro-alert` | Error real del sistema | rojo apagado, uso mínimo |

> **Regla cromática clave:** lo "pendiente" o "fallado" **nunca** se pinta de rojo de alarma. El error es aprendizaje (Doc 06), no peligro. Se usa el ámbar templado de "cuidado/atención", que invita sin asustar.

## 4. Tipografía

- **Display / titulares:** una serif humanista y elegante, o una sans geométrica cálida, que transmita seriedad serena (sensación "editorial de confianza", no "startup ruidosa").
- **Texto / UI:** una sans muy legible y neutra para lecturas largas de temario (la legibilidad es salud: el opositor lee horas).
- **Escala tipográfica** (modular, p. ej. ratio 1.25):
  | Token | Uso | Aprox. |
  |-------|-----|--------|
  | `--text-display` | Título de pantalla / momento | 32–40 |
  | `--text-h1`/`h2`/`h3` | Jerarquía de secciones | 28 / 22 / 18 |
  | `--text-body` | Cuerpo, temario | 16–17 (cómodo para leer) |
  | `--text-small` | Metadatos, ayudas | 13–14 |
- **Interlineado generoso** en temario (≈1.6) — leer denso cansa y angustia.
- **Medida de línea** controlada (≈60–75 caracteres) para lectura cómoda.

## 5. Espacio, layout y forma

- **Espaciado en escala de 4/8 px** (`4, 8, 12, 16, 24, 32, 48, 64`). El aire generoso es seña de identidad: pantallas que respiran.
- **Composición:** centrada, contenida, con mucho margen. Nada de paredes de información. **Una pantalla, una intención.**
- **Radios suaves** (`--radius: 12–16px`) — esquinas redondeadas, amables, nada cortante.
- **Sombras sutiles y difusas** (como luz suave), nunca duras. Elevación que sugiere calma.
- **Iconografía** lineal, fina, coherente, serena. Nada de iconos chillones o rellenos agresivos.

## 6. Movimiento (micro-interacciones)

> El movimiento de Faro **respira**, como el pulso de un faro. Nunca nervioso, nunca gratuito.

- Transiciones suaves (`ease`, duraciones 200–400 ms), sin rebotes histéricos.
- **El haz de luz** como recurso de animación: aparece suave al señalar el siguiente paso o un logro.
- **Celebración contenida:** al completar algo importante, una animación cálida y breve (un destello de luz que crece), no una lluvia de confeti estridente. La alegría de Faro es serena pero real.
- **Respeto a `prefers-reduced-motion`:** accesibilidad y respeto a quien se marea o se distrae.

## 7. Componentes núcleo (biblioteca)

La librería de componentes, todos bajo la filosofía de calma:

- **Tarjeta "Hoy"** — el componente estrella: muestra la única decisión del día (Doc 06 §5.2). Grande, clara, una acción.
- **Botón primario "la luz"** — el acento cálido; solo uno por pantalla (la acción principal).
- **Barra de rumbo / progreso** — progreso como avance sereno hacia el horizonte/puerto, no como porcentaje frío que culpa.
- **Tarjeta de tema / concepto** — bloque de temario legible, con su estado de dominio sutil.
- **Componente de pregunta** — enunciado limpio, opciones espaciadas, feedback con el porqué tras responder.
- **Check-in emocional** — gesto sereno para "¿cómo llegas?" (Doc 05 §4).
- **Mapa de la Travesía** — visualización del plan como una ruta hacia el puerto (opcional, para quien quiera ver el todo).
- **Panel de ánimo / mensajes de Faro** — donde aparece la voz del Faro (Doc 09), siempre con tono y forma cuidados.
- **Estados vacíos y de error** — incluso el error es amable y sereno (Doc 09 §6).

> Todos los componentes existen en **modo claro y oscuro**, con estados accesibles (foco, hover, activo, deshabilitado) bien definidos.

## 8. Accesibilidad (no negociable)

La calma incluye a todos:

- **Contraste AA mínimo** (AAA donde se pueda) en texto.
- **Navegable por teclado** y compatible con lectores de pantalla.
- **Tamaños de toque** cómodos (móvil-first) y tipografía escalable.
- **No depender solo del color** para transmitir estado (texto/icono además del color) — clave porque evitamos el rojo y usamos matices suaves.
- **Reduced motion** respetado.
- **Lenguaje claro** (la accesibilidad cognitiva importa con un usuario estresado): frases cortas, sin jerga.

## 9. Diseño responsive (web, móvil-first)

Faro es web responsive (decisión de plataforma del usuario), pero **el móvil es el escenario principal** (Doc 04 §1.1):

- **Móvil primero:** todo se diseña para la pantalla pequeña y la mano única; el escritorio amplía, no al revés.
- **El "Hoy" cabe en una pantalla de móvil** sin scroll para la acción principal.
- **Escritorio:** aprovecha el espacio para vistas de estudio cómodas y, en Admin, para paneles de gestión densos (el Admin sí puede ser más denso: es una herramienta de trabajo, no un espacio de calma).
- **Continuidad:** empezar en el móvil de camino y seguir en el portátil en casa, sin fricción.

## 10. Dos pieles, una alma

El sistema de diseño sirve a los dos roles, con tono distinto:

- **Estudiante:** máxima serenidad, foco, calidez. Es un santuario.
- **Administrador:** la misma identidad de marca, pero **eficiencia y densidad** propias de una herramienta profesional de gestión (tablas, paneles, filtros). Sereno y elegante, sí, pero optimizado para trabajar, no para calmar. (Detalle en Doc 11.)

## 11. Entrega del sistema de diseño

Para que esto sea código vivo y no un PDF muerto:
- **Tokens de diseño** (color, tipografía, espacio, radios, sombras, movimiento) como fuente única, consumidos por el front (Doc 12).
- **Biblioteca de componentes** documentada (estados, variantes, accesibilidad).
- **Modo claro/oscuro** desde el día uno.
- **Guía de uso** que conecta cada componente con su intención emocional (por qué el botón de la luz es uno solo, por qué no hay rojo de alarma…).

---

### Resumen del documento

El diseño de Faro tiene una tesis: **la calma es una funcionalidad** para un usuario ansioso. Su lenguaje visual nace de la metáfora del faro —**la luz** (acento cálido escaso), **la noche serena** (lienzo profundo, ideal para estudio nocturno y para modo oscuro central), **el horizonte** y **el pulso**—. Define tokens concretos de color (con la regla de oro de **no usar rojo de alarma** para lo pendiente/fallado, sino ámbar templado), tipografía legible para lecturas largas, espacio generoso que respira, forma amable, movimiento que respira y celebración contenida. Tiene una biblioteca de componentes liderada por la **tarjeta "Hoy"**, es **accesible** y **responsive móvil-first**, y ofrece **dos pieles** —el santuario sereno del estudiante y la herramienta densa y eficiente del administrador— bajo una misma identidad, entregado como **tokens + componentes** vivos (Doc 12).
