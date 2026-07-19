# ROADMAP_DEVELOPMENT.md — Roadmap de Desarrollo por Sprints

Este documento traduce `BACKLOG.md` (Epics/Features/Stories/Tasks) en una secuencia de sprints ejecutables. Es un plan de trabajo, no un compromiso de fechas — la duración de cada sprint es una unidad lógica de esfuerzo, no un calendario fijo.

Relación con otros documentos:

- **[ROADMAP.md](./ROADMAP.md)** define las *fases* de alto nivel del producto (qué se construye, en qué orden general).
- **Este documento** define los *sprints* dentro de esas fases (en qué orden concreto se ejecutan las Features/Stories del backlog).
- **[BACKLOG.md](./BACKLOG.md)** es la fuente de verdad de cada Epic/Feature/Story/Task referenciada aquí.

**Regla de avance:** un sprint no inicia hasta que el anterior esté completo, conforme al principio de `CLAUDE.md` de "no avanzar a la siguiente iteración sin completar la actual". Ningún sprint que incluya Tasks de implementación de código puede ejecutarse sin que las Stories correspondientes tengan diseño técnico `Aprobado`.

---

## Fase 0 — Fundación *(completada)*

| Sprint | Contenido | Estado |
|---|---|---|
| Sprint 0.1 | Documentación fundacional (README, VISION, ROADMAP, BACKLOG, CHANGELOG) | Hecho |
| Sprint 0.2 | Diseño de producto (PRODUCT, PERSONAS, USER_STORIES, GLOSSARY) | Hecho |
| Sprint 0.3 | Flujo Gitflow y CI/CD (convenciones, pipeline, plantillas, repo remoto) | Hecho |
| Sprint 0.4 | Arquitectura inicial (ADR-0001) | Hecho |
| Sprint 0.5 | Product Backlog jerárquico (Epic/Feature/Story/Task) + este roadmap de desarrollo | En progreso |

---

## Fase 1 — Diseño del roadmap educativo

Corresponde a `EPIC-01` (Ruta de aprendizaje estructurada) y `EPIC-02` (Proceso de ingeniería aplicado). Es trabajo de **diseño y especificación**, no de implementación — no requiere aprobación técnica previa porque no toca código.

### Sprint 1.1 — Taxonomía curricular

**Objetivo del sprint:** que exista una estructura de niveles clara y aprobable.

- TASK-01.1.1 — Definir la taxonomía de niveles (fundamentos → agentes/MCP → producción).
- TASK-01.1.2 — Diseñar la vista/documento que expone la ruta al estudiante.

**Criterio de salida del sprint:** US-01 pasa de `En diseño` a `Aprobado` en `BACKLOG.md`.

### Sprint 1.2 — Especificación de proyectos prácticos

**Objetivo del sprint:** que exista una plantilla validada para especificar cualquier proyecto práctico, probada con un caso real.

- TASK-01.2.1 — Diseñar la plantilla de especificación de proyecto práctico.
- TASK-01.2.2 — Especificar el primer proyecto práctico como caso piloto.

**Criterio de salida del sprint:** US-02 pasa a `Aprobado`; existe una especificación completa del proyecto piloto que servirá de entrada al Sprint 2.2.

### Sprint 1.3 — Proceso de ingeniería y ADR educativos

**Objetivo del sprint:** que cada proyecto práctico tenga definido su ciclo de ingeniería exigido (historia → diseño → implementación → pruebas → documentación) y su requisito de ADR cuando aplique.

- TASK-02.1.1 — Diseñar la plantilla de historia de usuario para proyectos de estudiantes.
- TASK-02.1.2 — Definir criterios mínimos de pruebas automatizadas por nivel.
- TASK-02.2.1 — Adaptar `docs/adr/template.md` para uso educativo por estudiantes.
- TASK-02.2.2 — Seleccionar el proyecto de nivel "producción" que exigirá ADR como entregable.

**Criterio de salida del sprint:** US-03 y US-04 pasan a `Aprobado`.

### Sprint 1.4 — Trazabilidad de contenido Claude/MCP

**Objetivo del sprint:** definir cómo se garantiza que el contenido sobre Claude y MCP permanece fiel a la documentación oficial de Anthropic.

- TASK-03.1.1 — Definir el proceso de referencia y actualización de contenido Claude/MCP.

**Criterio de salida del sprint:** US-05 pasa a `Aprobado`. Cierra la Fase 1 — todas las Stories de EPIC-01, EPIC-02 y EPIC-03 (en su alcance de Fase 1) quedan con diseño aprobado, habilitando el diseño técnico del MVP.

---

## Fase 2 — MVP de plataforma

Corresponde a `EPIC-05` (Plataforma base) y las Stories de EPIC-04 relativas a progreso/evidencia. **A partir de aquí los sprints incluyen implementación de código**, bloqueada hasta que cada Story tenga diseño técnico `Aprobado`, conforme a `CLAUDE.md`.

### Sprint 2.1 — Diseño técnico detallado del MVP

**Objetivo del sprint:** producir el diseño técnico aprobado que habilita todo el desarrollo de la Fase 2. Es un sprint de diseño, no de código.

- TASK-05.1.1 — Diseño técnico detallado del MVP: esquema de base de datos (a partir de `ADR-0001`), proveedores concretos de hosting/PostgreSQL, modelo de autorización.
- TASK-04.1.1 — Diseñar el modelo de estados de progreso (entidad Inscripción/Progreso).
- TASK-04.2.1 — Diseñar el formato del resumen de evidencia exportable.
- TASK-05.3.1 — Definir logging, métricas y alertas mínimas del despliegue.

**Criterio de salida del sprint:** US-08, US-09 y US-10 (definidas en `BACKLOG.md`, EPIC-05) cuentan con diseño técnico `Aprobado`. Solo entonces se habilitan las Tasks de implementación de los sprints siguientes.

### Sprint 2.2 — Autenticación y persistencia (implementación)

**Objetivo del sprint:** plataforma con registro/login funcional y esquema de datos desplegado.

- TASK-05.1.2 — Implementación de autenticación (OAuth delegado) y persistencia (esquema aprobado en Sprint 2.1), con pruebas automatizadas.

**Criterio de salida del sprint:** un estudiante puede crear cuenta y autenticarse; CI en verde con pruebas automatizadas del flujo.

### Sprint 2.3 — Primer módulo educativo (implementación)

**Objetivo del sprint:** el proyecto piloto especificado en Sprint 1.2 es completable dentro de la plataforma.

- TASK-05.2.1 — Implementación incremental del primer módulo educativo: catálogo del primer nivel, registro de progreso, pruebas automatizadas.

**Criterio de salida del sprint:** un estudiante puede ver el catálogo, inscribirse en el proyecto piloto y su progreso queda registrado.

### Sprint 2.4 — Observabilidad, seguridad y evidencia básicas

**Objetivo del sprint:** cerrar el MVP con las capacidades no funcionales mínimas y la primera versión de evidencia exportable.

- Implementación de logging/métricas/alertas definidos en Sprint 2.1 (TASK-05.3.1).
- Implementación del resumen de evidencia exportable (FEAT-04.2, según diseño de Sprint 2.1).

**Criterio de salida del sprint:** cierra la Fase 2 — MVP desplegado, con autenticación, un módulo educativo completo end-to-end, observabilidad básica y evidencia exportable.

---

## Fase 3 — Expansión de contenido práctico *(no desglosada aún)*

Corresponde a Epics futuros no desglosados en `BACKLOG.md` (módulos avanzados de MCP/agentes, proyectos adicionales, mecanismos de seguimiento extendidos). Se desglosará en sprints concretos solo cuando la Fase 2 esté completa, conforme al principio de `CLAUDE.md` de completar la iteración actual antes de iniciar la siguiente.

## Fase 4 — Madurez y comunidad *(no desglosada aún)*

Corresponde a Epics futuros no desglosados en `BACKLOG.md` (contribución externa, escalabilidad justificada vía ADR, accesibilidad/observabilidad en producción). Mismo criterio que la Fase 3: se planifica en sprints cuando le toque el turno.

---

## Resumen de secuencia

```text
Fase 0 (Hecho)
  └─ Sprints 0.1–0.5

Fase 1 (Diseño educativo — sin código)
  └─ Sprint 1.1 → Sprint 1.2 → Sprint 1.3 → Sprint 1.4

Fase 2 (MVP — con código, bloqueada por diseño aprobado)
  └─ Sprint 2.1 (diseño técnico, obligatorio primero)
       → Sprint 2.2 (auth + persistencia)
       → Sprint 2.3 (primer módulo educativo)
       → Sprint 2.4 (observabilidad + evidencia)

Fase 3 (Expansión — pendiente de desglose)
Fase 4 (Madurez — pendiente de desglose)
```

Este documento se actualiza cada vez que se cierra un sprint o se re-prioriza el backlog, manteniéndose sincronizado con `BACKLOG.md` y `CHANGELOG.md`.
