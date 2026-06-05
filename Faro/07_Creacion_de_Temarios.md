# 07 · Creación de Temarios

> *El contenido es el cuerpo de Faro; el método es su cabeza; el acompañamiento, su corazón. Sin un temario riguroso, fiable y actualizado, nada de lo demás importa.*

Este documento responde: ¿cómo se estructuran, crean, mantienen y verifican los temarios y el banco de preguntas? Es trabajo del **rol Administrador** (Doc 11) y conecta con el activo `faro-cowork-banco` ("banco de preguntas corpus-céntrico").

---

## 1. Principios del contenido en Faro

1. **Fidelidad a la convocatoria.** El temario de Faro refleja exactamente el temario oficial de la convocatoria vigente. Ni más, ni menos, ni desordenado.
2. **Trazabilidad / corpus-céntrico.** Cada afirmación y cada pregunta nace de una **fuente verificable** (el texto legal, el manual, el BOE). El contenido no "se inventa": se ancla a un corpus. (Esto es el alma del repo `faro-cowork-banco`.)
3. **Actualización viva.** Las oposiciones cambian: leyes que se reforman, convocatorias nuevas, temarios que se reordenan. El contenido desactualizado destruye la confianza → pipeline de actualización serio.
4. **Estructurado para el método.** El contenido no es un PDF: es una estructura granular (temas → epígrafes → conceptos) que el motor de estudio y de repaso puede explotar (Doc 06).
5. **Calidad pedagógica.** Claro, bien jerarquizado, con lo esencial destacado. Pensado para aprender, no solo para "estar completo".

## 2. La anatomía del contenido (modelo conceptual)

El contenido de Faro se organiza en una jerarquía granular (datos en Doc 12):

```
Oposición (cuerpo)
└── Temario (versión, ligada a una convocatoria)
    └── Tema (el "tema 14" oficial)
        └── Epígrafe / bloque
            └── Concepto / ítem de conocimiento  ← unidad atómica
                ├── Explicación (anclada a fuente del corpus)
                ├── Puntos clave / lo que más cae
                ├── Preguntas asociadas (banco)
                └── Estado de dominio del opositor (por usuario)
```

Granular a propósito: el repaso espaciado, la priorización y el seguimiento operan a nivel de **concepto**, no de "tema entero". Así Faro puede decir "dominas el tema 14 salvo el epígrafe de plazos, que se te resiste".

## 3. El corpus: la fuente de verdad

El **corpus** es el conjunto de fuentes autorizadas de las que deriva todo el contenido: textos legales (leyes, reglamentos), el BOE, manuales de referencia, las bases de la convocatoria. Principios:

- **Toda explicación y toda pregunta apunta a su fuente en el corpus.** Trazabilidad total.
- **El corpus se versiona.** Cuando una ley cambia, se sabe qué contenido depende de ella y hay que revisarlo.
- **Corpus-céntrico** significa que el contenido es un *reflejo derivado y verificable* del corpus, no un texto suelto sin respaldo. Esto es lo que hace fiable a Faro frente a apps con preguntas erróneas o desactualizadas.

## 4. El pipeline de creación de temarios

Cómo nace un temario en Faro, paso a paso (operado desde el rol Admin):

```
1. INGESTA        → Cargar la convocatoria, bases y temario oficial + fuentes del corpus
2. ESTRUCTURACIÓN → Descomponer en temas → epígrafes → conceptos (la jerarquía §2)
3. REDACCIÓN      → Crear explicaciones claras de cada concepto, ancladas al corpus
4. ENRIQUECIMIENTO→ Marcar peso/relevancia, puntos clave, dificultad
5. GENERACIÓN DE  → Crear preguntas (test, casos, supuestos) ligadas a cada concepto
   PREGUNTAS
6. VERIFICACIÓN   → Revisión experta: corrección legal, fidelidad a la fuente, calidad
7. PUBLICACIÓN    → Versionar y publicar; queda disponible para el plan de los alumnos
8. MANTENIMIENTO  → Vigilar cambios (BOE, nueva convocatoria) → revisar → re-versionar
```

### 4.1 El papel de la IA (con red de seguridad humana)

La IA acelera ingesta, estructuración, borradores de explicación y generación de preguntas a partir del corpus. **Pero:**
- La IA **propone**, el experto **dispone**. Nada de contenido legal publicado sin verificación humana (paso 6). En oposiciones, una pregunta mal corregida o una norma desactualizada erosiona la confianza de forma grave.
- La IA trabaja **anclada al corpus** (corpus-céntrico): genera a partir de las fuentes, citándolas, no de su memoria general. Esto reduce errores y permite trazar cada ítem.
- (Conexión con `faro-cowork-banco`: ese es el espacio de intercambio para la generación de banco de preguntas corpus-céntrico. Faro consume ese activo.)

## 5. El banco de preguntas

El banco es el activo de práctica. Tipos de pregunta, según la prueba real de cada cuerpo (Doc 02):

| Tipo | Para qué prueba | Qué entrena |
|------|-----------------|-------------|
| **Test** (opción múltiple) | La mayoría de cuerpos | Recuerdo y discriminación; base del repaso espaciado |
| **Verdadero/Falso razonado** | Refuerzo conceptual | Precisión, matices legales |
| **Caso / supuesto práctico** | Justicia, AGE, local | Aplicar el conocimiento a un escenario |
| **Desarrollo** | Cuerpos A, élite | Estructurar y exponer (con rúbrica de corrección) |
| **Oral / "cantar tema"** | Educación, élite | Exposición (con guía y autoevaluación) |

Cada pregunta lleva:
- **enunciado** y **opciones/solución**,
- **explicación del porqué** (no solo "la correcta es la B"): el feedback que enseña,
- **enlace a la fuente** del corpus (trazabilidad),
- **metadatos:** concepto asociado, dificultad, peso, tipo, estado de revisión.

> La **explicación del porqué** es innegociable. Una app que solo dice "incorrecto" no enseña. Faro convierte cada fallo en aprendizaje (Doc 06 §2).

## 6. Calidad y verificación (el control que da confianza)

- **Doble verificación de lo crítico:** corrección legal/factual + fidelidad a la fuente + calidad pedagógica.
- **Estados de contenido:** borrador → en revisión → verificado → publicado → marcado para actualizar. Nada llega al alumno sin "verificado".
- **Reporte desde el alumno:** el opositor puede señalar una pregunta dudosa; entra en cola de revisión. El uso real mejora el banco (foso de datos, Doc 02).
- **Auditoría de actualidad:** revisión periódica contra cambios normativos y nuevas convocatorias.

## 7. Mantenimiento y versionado (el reto continuo)

El contenido de oposiciones **caduca**. Faro lo gestiona como un activo vivo:

- **Versionado por convocatoria:** cada temario se asocia a la convocatoria/normativa vigente; cuando cambia, se crea nueva versión y se migra al alumno con aviso claro.
- **Detección de impacto:** si una ley del corpus cambia, Faro sabe qué conceptos y preguntas dependían de ella → cola de revisión dirigida (no revisar todo a ciegas).
- **Comunicación al alumno:** "El tema 7 se ha actualizado por la reforma de [norma]. Tu progreso se conserva; revisa los cambios marcados." Transparencia que refuerza la confianza.

## 8. Adaptación multi-oposición

El sistema de contenido es **configurable por cuerpo**: cada oposición define su estructura de temario, sus tipos de prueba y su baremo (Doc 06 §3). Así Faro escala de un cuerpo beachhead a familias enteras (Doc 02 §7) **sin rehacer el motor**: solo se añade y verifica contenido nuevo sobre la misma maquinaria.

## 9. Cómo lo gestiona el Admin (puente al Doc 11)

Todo este pipeline se opera desde el **rol Administrador**: ingesta de convocatorias, editor estructurado de temario, gestión del corpus y sus fuentes, generador asistido de preguntas, flujo de revisión y verificación, versionado y publicación, y cola de reportes de alumnos. El contenido es un producto interno con su propio ciclo de vida (Doc 11 §4).

---

### Resumen del documento

El contenido de Faro es **corpus-céntrico**: cada explicación y cada pregunta deriva de una fuente verificable (ley, BOE, manual) y es trazable, fiel a la convocatoria y mantenida viva. Se estructura en una jerarquía granular (oposición → temario → tema → epígrafe → **concepto**) para que el método (repaso espaciado, priorización, seguimiento) opere a nivel atómico. Nace por un **pipeline** de 8 pasos (ingesta → estructuración → redacción → enriquecimiento → generación de preguntas → **verificación humana** → publicación → mantenimiento), donde la IA propone anclada al corpus y el experto dispone. El **banco de preguntas** cubre los tipos reales de cada prueba, siempre con **explicación del porqué** y enlace a la fuente. El contenido se **versiona por convocatoria** y se mantiene ante cambios normativos. Todo es configurable por cuerpo (escala multi-oposición) y se opera desde el rol Admin (Doc 11).
