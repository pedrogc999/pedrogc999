# 🪧 Proyecto Faro — El Big Bang

> **Faro** es el preparador de oposiciones definitivo: el sistema que te da todo lo que necesitas para preparar, planificar y superar una oposición en España, que hace seguimiento real de tu progreso, que te acompaña emocionalmente cada día y en cada bache, y que lo hace con una experiencia sencilla, elegante, precisa y profesional.
>
> No es una app de estudio. Es **la luz que te guía hasta la plaza**.

---

## 0. Cómo leer este documento

Este es el documento fundacional de Faro: la fuente única de verdad. Está dividido en pilares. Cada pilar es un documento independiente, hiper-detallado, que responde **todo** sobre su dominio. Léelos en orden la primera vez; consúltalos por separado después.

| # | Documento | Qué responde | Rol principal |
|---|-----------|--------------|----------------|
| 00 | **README** (este archivo) | La visión global, el mapa, los principios rectores | Todos |
| 01 | [`01_Vision_y_Manifiesto.md`](01_Vision_y_Manifiesto.md) | Por qué existe Faro, qué promete, sus principios | Todos |
| 02 | [`02_Estrategia_y_Mercado.md`](02_Estrategia_y_Mercado.md) | El mercado, la competencia, la diferenciación, el foso | Admin |
| 03 | [`03_Modelo_de_Negocio.md`](03_Modelo_de_Negocio.md) | Cómo gana dinero Faro, precios, unit economics | Admin |
| 04 | [`04_El_Opositor_Investigacion.md`](04_El_Opositor_Investigacion.md) | Quién es el opositor, su viaje, su psicología, personas | Todos |
| 05 | [`05_Acompanamiento_Emocional.md`](05_Acompanamiento_Emocional.md) | El sistema psicológico: motivación y apoyo emocional | Estudiante |
| 06 | [`06_Metodologia_y_Planificacion.md`](06_Metodologia_y_Planificacion.md) | Cómo se planifica el estudio y los temarios (ciencia del aprendizaje) | Estudiante |
| 07 | [`07_Creacion_de_Temarios.md`](07_Creacion_de_Temarios.md) | Cómo se crean, estructuran y mantienen los temarios | Admin |
| 08 | [`08_Sistema_de_Diseno.md`](08_Sistema_de_Diseno.md) | El sistema de diseño visual (UI), tokens, componentes | Todos |
| 09 | [`09_Sistema_de_Comunicacion.md`](09_Sistema_de_Comunicacion.md) | Voz, tono, copy, notificaciones, la "voz del Faro" | Todos |
| 10 | [`10_Rol_Estudiante.md`](10_Rol_Estudiante.md) | Todas las funcionalidades del opositor | Estudiante |
| 11 | [`11_Rol_Administrador.md`](11_Rol_Administrador.md) | Todas las funcionalidades de gestión del negocio | Admin |
| 12 | [`12_Arquitectura_y_Datos.md`](12_Arquitectura_y_Datos.md) | Stack, arquitectura, modelo de datos, IA | Técnico |
| 13 | [`13_Roadmap_y_Metricas.md`](13_Roadmap_y_Metricas.md) | Fases de construcción, MVP, KPIs y métricas | Admin |

---

## 1. El problema, en una frase

> Preparar una oposición en España es **uno de los procesos más largos, solitarios e inciertos** que una persona afronta voluntariamente: 1 a 4 años de estudio, sin garantía de plaza, con tu identidad y tu economía en juego, y casi siempre **en soledad**.

Las herramientas actuales (academias, PDFs, apps de test, Excel, grupos de Telegram) resuelven **fragmentos**: contenido, o test, o planificación. **Ninguna resuelve a la persona completa**: el cerebro que aprende *y* el corazón que aguanta.

Faro nace para resolver **a la persona entera**.

## 2. La promesa de Faro

Faro le promete al opositor cuatro cosas, en este orden:

1. **Te diré exactamente qué estudiar hoy.** Nunca más la angustia de la página en blanco ni el "¿voy bien?".
2. **Sabré cómo vas de verdad.** Seguimiento honesto, no sensación. Datos que te orientan, no que te castigan.
3. **No estarás solo.** Faro te acompaña como lo haría un buen preparador y un buen psicólogo: te empuja cuando puedes más, te sostiene cuando no puedes, y te entiende siempre.
4. **Será fácil y bonito.** Una experiencia tan clara y serena que abrir Faro *calme* en vez de abrumar.

## 3. Los cuatro pilares del producto

```
                          ┌─────────────────────────┐
                          │         FARO            │
                          │  "La luz que te guía"   │
                          └────────────┬────────────┘
            ┌──────────────┬───────────┼───────────┬──────────────┐
            ▼              ▼           ▼           ▼              ▼
     ┌────────────┐ ┌────────────┐ ┌─────────┐ ┌────────────┐ ┌────────────┐
     │ PLANIFICAR │ │  ESTUDIAR  │ │ MEDIR   │ │ ACOMPAÑAR  │ │  (BASE)    │
     │            │ │ +ENTRENAR  │ │         │ │ EMOCIONAL  │ │ Diseño +   │
     │ Plan vivo  │ │ Temario +  │ │ Métrica │ │ Coaching + │ │ Comunica-  │
     │ adaptativo │ │ banco preg.│ │ honesta │ │ psicología │ │ ción       │
     └────────────┘ └────────────┘ └─────────┘ └────────────┘ └────────────┘
```

1. **Planificar** — Un plan de estudio vivo que se calcula a partir de tu temario, tu fecha de examen y tus horas reales, y que **se re-planifica solo** cuando la vida se interpone. → Doc 06
2. **Estudiar y entrenar** — El temario estructurado + el banco de preguntas corpus-céntrico (test, casos, supuestos) con repetición espaciada. → Docs 06, 07
3. **Medir** — Seguimiento honesto del progreso, retención y rendimiento, presentado para orientar, no para culpar. → Docs 10, 13
4. **Acompañar emocionalmente** — El diferencial: un sistema psicológico que motiva, detecta el bajón y sostiene. → Doc 05

Y por debajo, la **base transversal**: el sistema de **diseño** (Doc 08) y el sistema de **comunicación** (Doc 09) que hacen que todo se sienta sencillo, elegante y humano.

## 4. Los dos roles

Faro es una plataforma con dos caras claramente separadas:

- **🎓 Rol Estudiante (Opositor).** La experiencia de preparación completa. Es el corazón del producto. → Doc 10
- **🛠️ Rol Administrador (Negocio).** La gestión integral: contenido/temarios, alumnos, preparadores, suscripciones, analítica, soporte y crecimiento. → Doc 11

Un preparador o academia usa el rol Admin para **operar su negocio sobre Faro**; el opositor usa el rol Estudiante para **ganar su plaza**. Ambos comparten datos pero ven mundos distintos.

## 5. Principios rectores (la constitución de Faro)

Estos principios resuelven empates. Cuando dudemos en cualquier decisión —de producto, diseño, copy o negocio— volvemos aquí.

1. **La persona antes que el contenido.** Hay mil sitios con temario. Solo hay un sitio que cuida al que estudia. Cuando haya conflicto, gana el bienestar del opositor.
2. **Honestidad amable.** Faro nunca miente sobre tu progreso para que te sientas bien, ni te golpea con la verdad. Dice la verdad *con cuidado*.
3. **Calma por defecto.** El opositor ya vive en ansiedad. Cada pantalla debe restar tensión, no sumarla. Menos es más. Silencio antes que ruido.
4. **Una sola decisión a la vez.** Faro siempre sabe cuál es el siguiente paso y lo presenta sin fricción. La parálisis por elección es el enemigo.
5. **Adaptativo, no rígido.** La vida del opositor es caótica. El plan se dobla, no se rompe. Saltarse un día no es un fracaso, es un dato.
6. **Rigor de preparador.** El consejo de estudio de Faro es el de un preparador de élite: basado en la convocatoria, el BOE, el tribunal y la evidencia, no en frases motivacionales vacías.
7. **Privacidad sagrada.** El opositor nos confía sus miedos y sus datos. Eso es un voto de confianza que no se traiciona ni se monetiza nunca.
8. **Elegancia profesional.** Nada infantil, nada estridente. Faro se siente como una herramienta seria para una meta seria, pero cálida.

## 6. La metáfora del Faro (el alma del producto)

Todo en Faro se deriva de su nombre. Un faro:

- **Guía sin invadir.** No navega por ti; ilumina para que tú navegues. → Faro no estudia por el opositor; le muestra el camino.
- **Es constante.** Está ahí en la noche y en la tormenta. → Faro acompaña en el bajón, no solo en la racha buena.
- **Da seguridad.** Ver el faro es saber dónde estás. → Faro siempre responde "¿voy bien?" y "¿qué toca ahora?".
- **Tiene un ritmo.** Su luz pulsa, regular. → El ritmo de estudio sostenible, no el sprint que quema.

Esta metáfora gobierna el nombre, el logo, la paleta, el tono de voz y hasta los nombres de las funcionalidades (la **Travesía** = tu plan; el **Cuaderno de Bitácora** = tu diario; el **Vigía** = el sistema que detecta tu estado; el **Puerto** = tu meta/plaza). Ver Docs 08 y 09.

## 7. Estado y siguientes pasos

Este documento es **el Big Bang**: la versión 1.0 de la visión completa. A partir de aquí:

1. Validar la estrategia y el modelo de negocio (Docs 02–03).
2. Cerrar el sistema de diseño y comunicación como código vivo (Docs 08–09).
3. Construir el MVP siguiendo el roadmap (Doc 13), empezando por el núcleo **Planificar + Estudiar + Acompañar**.

> *Faro existe para que ningún opositor vuelva a sentir que rema en la oscuridad y en soledad. Encendámoslo.*
