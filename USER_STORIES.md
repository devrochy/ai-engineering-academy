# USER_STORIES.md — Historias de Usuario

Historias de usuario derivadas de [PERSONAS.md](./PERSONAS.md) y del alcance funcional definido en [PRODUCT.md](./PRODUCT.md). Los términos usados siguen [GLOSSARY.md](./GLOSSARY.md).

**Estado de este documento:** diseño de producto, pendiente de aprobación. Ninguna historia aquí listada habilita implementación de código por sí sola — según `CLAUDE.md`, cada una requiere además un diseño técnico aprobado y, cuando corresponda, un ADR, antes de pasar a `BACKLOG.md` como "Aprobada".

Formato: `Como [persona], quiero [objetivo], para [beneficio]`, con criterios de aceptación verificables.

---

## Épica 1 — Ruta de aprendizaje estructurada

### US-01 — Explorar la ruta de aprendizaje por niveles

**Como** Daniela (desarrolladora en transición a IA),
**quiero** ver una estructura curricular organizada por niveles (fundamentos → agentes/MCP → producción),
**para** saber en qué orden abordar los proyectos y entender qué voy a aprender en cada etapa.

**Criterios de aceptación:**

- Existe una vista o documento que lista los niveles con su objetivo de aprendizaje.
- Cada nivel indica qué proyectos prácticos lo componen.
- Se indica claramente el prerrequisito de cada nivel respecto al anterior.

---

### US-02 — Entender el objetivo de un proyecto antes de empezarlo

**Como** Sofía (bootcamper construyendo portafolio),
**quiero** leer el objetivo, alcance y resultado esperado de un proyecto antes de iniciarlo,
**para** decidir si es el proyecto adecuado para mi nivel actual y saber qué voy a poder mostrar al terminarlo.

**Criterios de aceptación:**

- Cada proyecto tiene una descripción con: objetivo, nivel, prerrequisitos y resultado esperado (qué se habrá construido).
- Se indica explícitamente qué conceptos de Claude Code o MCP se practican en ese proyecto.

---

## Épica 2 — Proceso de ingeniería aplicado al aprendizaje

### US-03 — Practicar el ciclo completo de ingeniería en un proyecto

**Como** Marco (ML Engineer llevando modelos a producción),
**quiero** que cada proyecto práctico exija historia de usuario, diseño, implementación incremental y pruebas automatizadas,
**para** aprender a construir sistemas de IA con el mismo rigor que un equipo de ingeniería de software real.

**Criterios de aceptación:**

- Cada proyecto incluye una plantilla o guía de historia de usuario antes de la parte de implementación.
- Cada proyecto especifica qué pruebas automatizadas se esperan como criterio de "hecho".
- El material del proyecto referencia explícitamente el proceso descrito en `CLAUDE.md` (historia → diseño → implementación → pruebas → documentación).

---

### US-04 — Registrar decisiones de diseño como lo haría un equipo real

**Como** Daniela (desarrolladora en transición a IA),
**quiero** que los proyectos me guíen a documentar decisiones relevantes en formato ADR,
**para** practicar cómo se justifican y comunican decisiones técnicas en un entorno profesional.

**Criterios de aceptación:**

- Existe una plantilla de ADR accesible desde el material del proyecto.
- Al menos un proyecto del nivel "producción" exige explícitamente redactar un ADR como parte de la entrega.

---

## Épica 3 — Contenido confiable sobre Claude y MCP

### US-05 — Aprender MCP con contenido trazable a la fuente oficial

**Como** Marco (ML Engineer),
**quiero** que todo el contenido sobre Claude y MCP esté basado en documentación oficial de Anthropic y la referencie,
**para** confiar en que lo que aprendo sigue vigente y es correcto, sin depender de interpretaciones no verificadas.

**Criterios de aceptación:**

- Todo contenido educativo sobre Claude o MCP incluye referencia a la fuente oficial de Anthropic en la que se basa.
- Existe un proceso (aunque sea manual) para revisar y actualizar contenido cuando la documentación oficial cambie.

---

## Épica 4 — Evidencia de progreso y portafolio

### US-06 — Mostrar evidencia de un proyecto completado

**Como** Sofía (bootcamper buscando su primer rol),
**quiero** poder generar o exportar evidencia clara de que completé un proyecto (qué construí, cómo lo diseñé, cómo lo probé),
**para** usarla como material de portafolio en procesos de selección.

**Criterios de aceptación:**

- Al completar un proyecto, existe un resumen consultable con: objetivo, decisiones de diseño clave y evidencia de pruebas.
- El formato de evidencia es lo suficientemente autocontenido para compartirse fuera de la plataforma (por ejemplo, como documento o enlace).

---

### US-07 — Ver mi progreso a través del roadmap

**Como** Daniela (desarrolladora en transición a IA),
**quiero** ver qué proyectos y niveles ya completé y cuáles tengo pendientes,
**para** mantener motivación y planificar mi tiempo de estudio semanal.

**Criterios de aceptación:**

- Existe una vista de progreso por nivel y por proyecto.
- El estado de cada proyecto refleja si está: no iniciado, en progreso o completado.

---

## Trazabilidad con el Backlog

Estas historias son candidatas de diseño. Su incorporación formal a `BACKLOG.md` (con estado `Pendiente` → `En diseño` → `Aprobado`) ocurrirá cuando se aborde la Fase 1 del roadmap ("Diseño del roadmap educativo"), y su implementación en código requerirá, en cada caso, diseño técnico aprobado según `CLAUDE.md`.

| ID | Épica | Persona principal | Fase de roadmap relacionada |
|---|---|---|---|
| US-01 | Ruta de aprendizaje | Daniela | Fase 1 |
| US-02 | Ruta de aprendizaje | Sofía | Fase 1 |
| US-03 | Proceso de ingeniería | Marco | Fase 1 / Fase 2 |
| US-04 | Proceso de ingeniería | Daniela | Fase 2 |
| US-05 | Contenido confiable | Marco | Fase 1 / Fase 3 |
| US-06 | Evidencia de progreso | Sofía | Fase 2 / Fase 3 |
| US-07 | Evidencia de progreso | Daniela | Fase 2 |
