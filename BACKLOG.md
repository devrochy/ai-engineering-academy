# Backlog — AI Engineering Academy

Product Backlog organizado jerárquicamente: **Epic → Feature → Story → Task → Subtask**. Ninguna Task o Subtask de código se ejecuta sin que su Story tenga diseño técnico aprobado, conforme a `CLAUDE.md`.

## Convenciones

**Jerarquía y prefijos de ID:**

| Nivel | Prefijo | Qué representa |
|---|---|---|
| Epic | `EPIC-XX` | Objetivo grande de producto, agrupa varias Features |
| Feature | `FEAT-XX.Y` | Capacidad concreta dentro de un Epic |
| Story | `US-XX` | Historia de usuario verificable (formato Como/Quiero/Para), ver [USER_STORIES.md](./USER_STORIES.md) |
| Task | `TASK-XX.Y.Z` | Unidad de trabajo de ingeniería o diseño necesaria para cumplir una Story |
| Subtask | checklist bajo cada Task | Paso concreto y verificable de una Task |

**Estados:** `Pendiente` · `En diseño` · `Aprobado` · `En progreso` · `Hecho`

**Regla de bloqueo:** ninguna Task marcada como implementación de código puede pasar a `En progreso` mientras su Story esté en estado distinto de `Aprobado` (diseño técnico revisado), conforme a `CLAUDE.md`. Las Tasks de diseño/especificación sí pueden avanzar libremente — son las que producen ese diseño aprobado.

**Trazabilidad:** este backlog se mantiene sincronizado con `ROADMAP.md` (fases de alto nivel), `ROADMAP_DEVELOPMENT.md` (sprints), `USER_STORIES.md`, `docs/adr/` y `CHANGELOG.md` en cada cambio.

---

## EPIC-00 — Fundación del proyecto

**Estado:** Hecho · **Fase:** Fase 0 (`ROADMAP.md`)

Trabajo fundacional ya completado: documentación base, diseño de producto, flujo Gitflow/CI, primer ADR de arquitectura. Se conserva aquí como resumen histórico, sin desglosar a nivel Task/Subtask por estar cerrado.

| Feature | Contenido | Estado |
|---|---|---|
| FEAT-00.1 — Documentación fundacional | `README.md`, `VISION.md`, `ROADMAP.md`, `BACKLOG.md`, `CHANGELOG.md` iniciales | Hecho |
| FEAT-00.2 — Diseño de producto | `PRODUCT.md`, `PERSONAS.md`, `USER_STORIES.md`, `GLOSSARY.md` | Hecho |
| FEAT-00.3 — Flujo Git y CI/CD | Convenciones Gitflow en `CLAUDE.md`, `.github/workflows/ci.yml`, plantillas de PR/ADR, repositorio remoto | Hecho |
| FEAT-00.4 — Arquitectura inicial | `ADR-0001: Arquitectura inicial de la plataforma` (Aceptado) | Hecho |

---

## EPIC-01 — Ruta de aprendizaje estructurada

**Objetivo:** que el estudiante pueda entender y navegar la ruta de aprendizaje por niveles y proyectos. **Fase:** Fase 1 (`ROADMAP.md`).

### FEAT-01.1 — Estructura curricular por niveles

**Story:** [US-01](./USER_STORIES.md#us-01--explorar-la-ruta-de-aprendizaje-por-niveles) — Explorar la ruta de aprendizaje por niveles (Daniela) · Estado: `En diseño`

- **TASK-01.1.1** — Definir la taxonomía de niveles (fundamentos → agentes/MCP → producción) · `Pendiente`
  - [ ] Listar los niveles y el objetivo de aprendizaje de cada uno.
  - [ ] Definir los criterios de progresión y prerrequisitos entre niveles.
  - [ ] Documentar la taxonomía como parte del diseño curricular (sucesor de `BACKLOG.md` #6 original).
- **TASK-01.1.2** — Diseñar la vista/documento que expone la ruta al estudiante · `Pendiente`
  - [ ] Especificar qué información se muestra por nivel (objetivo, proyectos incluidos, prerrequisito).
  - [ ] Validar el diseño contra el criterio de aceptación de US-01.

### FEAT-01.2 — Especificación de proyectos prácticos

**Story:** [US-02](./USER_STORIES.md#us-02--entender-el-objetivo-de-un-proyecto-antes-de-empezarlo) — Entender el objetivo de un proyecto antes de empezarlo (Sofía) · Estado: `En diseño`

- **TASK-01.2.1** — Diseñar la plantilla de especificación de proyecto práctico · `Pendiente`
  - [ ] Definir campos obligatorios: objetivo, nivel, prerrequisitos, resultado esperado.
  - [ ] Definir cómo se referencian los conceptos de Claude Code/MCP practicados en cada proyecto.
- **TASK-01.2.2** — Especificar el primer proyecto práctico como caso piloto · `Pendiente`
  - [ ] Redactar la historia de usuario completa del proyecto piloto (sucesor de `BACKLOG.md` #7 original).
  - [ ] Validar la plantilla de FEAT-01.2 usando el proyecto piloto como prueba.

---

## EPIC-02 — Proceso de ingeniería aplicado al aprendizaje

**Objetivo:** que cada proyecto práctico enseñe el ciclo de ingeniería completo, no solo el resultado técnico. **Fase:** Fase 1 / Fase 2 (`ROADMAP.md`).

### FEAT-02.1 — Ciclo de ingeniería exigido por proyecto

**Story:** [US-03](./USER_STORIES.md#us-03--practicar-el-ciclo-completo-de-ingeniería-en-un-proyecto) — Practicar el ciclo completo de ingeniería en un proyecto (Marco) · Estado: `En diseño`

- **TASK-02.1.1** — Diseñar la plantilla de historia de usuario para proyectos de estudiantes · `Pendiente`
  - [ ] Definir la estructura mínima (Como/Quiero/Para + criterios de aceptación).
  - [ ] Incluir referencia explícita al proceso historia → diseño → implementación → pruebas → documentación de `CLAUDE.md`.
- **TASK-02.1.2** — Definir criterios mínimos de pruebas automatizadas por nivel · `Pendiente`
  - [ ] Establecer qué tipo de pruebas se exige como criterio de "hecho" en cada nivel.

### FEAT-02.2 — Registro de decisiones arquitectónicas

**Story:** [US-04](./USER_STORIES.md#us-04--registrar-decisiones-de-diseño-como-lo-haría-un-equipo-real) — Registrar decisiones de diseño en formato ADR (Daniela) · Estado: `En diseño`

- **TASK-02.2.1** — Adaptar `docs/adr/template.md` para uso educativo por estudiantes · `Pendiente`
  - [ ] Simplificar/anotar la plantilla existente con ejemplos pedagógicos.
- **TASK-02.2.2** — Seleccionar el proyecto de nivel "producción" que exigirá ADR como entregable · `Pendiente`
  - [ ] Confirmar con FEAT-01.2 (especificación de proyectos) que el requisito de ADR queda reflejado.

---

## EPIC-03 — Contenido confiable sobre Claude y MCP

**Objetivo:** que todo el contenido educativo sobre Claude y MCP sea trazable a la documentación oficial de Anthropic. **Fase:** Fase 1 / Fase 3 (`ROADMAP.md`).

### FEAT-03.1 — Trazabilidad a documentación oficial

**Story:** [US-05](./USER_STORIES.md#us-05--aprender-mcp-con-contenido-trazable-a-la-fuente-oficial) — Aprender MCP con contenido trazable a la fuente oficial (Marco) · Estado: `En diseño`

- **TASK-03.1.1** — Definir el proceso de referencia y actualización de contenido Claude/MCP · `Pendiente`
  - [ ] Definir el formato de citación de la fuente oficial en cada pieza de contenido.
  - [ ] Definir una cadencia de revisión de vigencia del contenido frente a la documentación oficial de Anthropic.

---

## EPIC-04 — Evidencia de progreso y portafolio

**Objetivo:** que el estudiante pueda ver su progreso y exportar evidencia verificable de lo construido. **Fase:** Fase 2 / Fase 3 (`ROADMAP.md`).

### FEAT-04.1 — Seguimiento de progreso del estudiante

**Story:** [US-07](./USER_STORIES.md#us-07--ver-mi-progreso-a-través-del-roadmap) — Ver mi progreso a través del roadmap (Daniela) · Estado: `En diseño`

- **TASK-04.1.1** — Diseñar el modelo de estados de progreso · `Pendiente`
  - [ ] Definir transiciones válidas entre estados (no iniciado / en progreso / completado), sobre la entidad Inscripción/Progreso de `ADR-0001`.
  - [ ] Diseñar (a nivel conceptual, sin código) la vista de progreso por nivel y por proyecto.

### FEAT-04.2 — Evidencia exportable de proyecto completado

**Story:** [US-06](./USER_STORIES.md#us-06--mostrar-evidencia-de-un-proyecto-completado) — Mostrar evidencia de un proyecto completado (Sofía) · Estado: `En diseño`

- **TASK-04.2.1** — Diseñar el formato del resumen de evidencia · `Pendiente`
  - [ ] Definir la estructura del documento de evidencia (objetivo, decisiones de diseño clave, evidencia de pruebas).
  - [ ] Definir el mecanismo de exportación/enlace compartible fuera de la plataforma.

---

## EPIC-05 — Plataforma base (MVP técnico)

**Objetivo:** tener una plataforma funcional mínima que soporte autenticación, persistencia, el primer módulo educativo y observabilidad básica, sobre la base decidida en `ADR-0001`. **Fase:** Fase 2 (`ROADMAP.md`).

> Ninguna Task de implementación de este Epic puede iniciar sin que su Story tenga diseño técnico `Aprobado`, conforme a `CLAUDE.md`.

### FEAT-05.1 — Autenticación y persistencia

**Story:** **US-08** (nueva) — *Como estudiante, quiero crear una cuenta y autenticarme de forma segura, para acceder a mi progreso personal.* · Estado: `Pendiente`

- **TASK-05.1.1** — Diseño técnico detallado del MVP (sucesor de `ADR-0001`, `BACKLOG.md` #9) · `Pendiente`
  - [ ] Definir el esquema de tablas a partir del modelo de datos de `ADR-0001` (Estudiante, Nivel, Proyecto, Inscripción/Progreso, Evidencia).
  - [ ] Seleccionar el proveedor concreto de hosting y de PostgreSQL gestionado.
  - [ ] Definir el modelo de autorización (roles: estudiante; evaluar necesidad de rol de administrador de contenido).
  - [ ] Someter el diseño a aprobación antes de habilitar cualquier Task de implementación.
- **TASK-05.1.2** — Implementación de autenticación y persistencia *(bloqueada hasta que TASK-05.1.1 esté Aprobada)* · `Pendiente`
  - [ ] Implementar registro/login delegado vía OAuth (según `ADR-0001`).
  - [ ] Implementar el esquema de base de datos aprobado.
  - [ ] Añadir pruebas automatizadas del flujo de autenticación.

### FEAT-05.2 — Primer módulo educativo implementado

**Story:** **US-09** (nueva) — *Como estudiante, quiero completar el primer proyecto práctico dentro de la plataforma, para experimentar el flujo completo de aprendizaje.* · Estado: `Pendiente`

- **TASK-05.2.1** — Implementación incremental del primer módulo educativo (sucesor de `BACKLOG.md` #10) *(bloqueada hasta que EPIC-01 y FEAT-05.1 estén Aprobados/Hechos)* · `Pendiente`
  - [ ] Implementar la vista de catálogo de proyectos del primer nivel.
  - [ ] Implementar el registro de progreso por proyecto (usa el modelo de FEAT-04.1).
  - [ ] Añadir pruebas automatizadas del flujo completo.

### FEAT-05.3 — Observabilidad y seguridad básicas

**Story:** **US-10** (nueva) — *Como Tech Lead, quiero observabilidad y seguridad básicas desde el primer despliegue, para detectar y responder a incidentes tempranamente.* · Estado: `Pendiente`

- **TASK-05.3.1** — Definir logging y métricas mínimas del despliegue (sucesor de `BACKLOG.md` #11) · `Pendiente`
  - [ ] Definir qué eventos se registran (autenticación, errores, cambios de progreso).
  - [ ] Definir alertas básicas de disponibilidad sobre la plataforma de hosting elegida.

---

## Epics futuros (no desglosados aún)

Conforme al principio de `CLAUDE.md` de completar la iteración actual antes de avanzar, los siguientes Epics de `ROADMAP.md` (Fase 3 — Expansión, Fase 4 — Madurez y comunidad) **no se desglosan en Features/Stories/Tasks todavía**. Se abordarán cuando EPIC-01 a EPIC-05 estén completos.

---

Este backlog se mantiene sincronizado con `ROADMAP.md`, `ROADMAP_DEVELOPMENT.md`, `USER_STORIES.md`, `docs/adr/` y `CHANGELOG.md` en cada cambio, conforme a las reglas del proyecto.
