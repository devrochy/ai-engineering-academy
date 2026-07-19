# Backlog — AI Engineering Academy

Registro de historias de usuario y tareas pendientes. Ninguna tarea de esta lista se implementa en código sin una historia de usuario desarrollada y un diseño aprobado, conforme a `CLAUDE.md`.

Estados: `Pendiente` · `En diseño` · `Aprobado` · `En progreso` · `Hecho`

## Fase 0 — Fundación

| # | Historia / Tarea | Estado |
|---|---|---|
| 1 | Definir misión, visión y propuesta de valor (`VISION.md`) | Hecho |
| 2 | Definir README del proyecto | Hecho |
| 3 | Definir roadmap de alto nivel (`ROADMAP.md`) | Hecho |
| 4 | Inicializar `BACKLOG.md` y `CHANGELOG.md` | Hecho |
| 5 | Como Tech Lead, quiero un primer ADR que documente las decisiones de arquitectura de la plataforma (stack, hosting, modelo de datos educativo), para tener una base técnica aprobada antes de diseñar el MVP | Pendiente |

### Sprint 0.2 — Diseño de producto

| # | Historia / Tarea | Estado |
|---|---|---|
| 18 | Definir problema, propuesta de producto, alcance funcional y métricas de éxito (`PRODUCT.md`) | Hecho |
| 19 | Definir personas de usuario objetivo (`PERSONAS.md`) | Hecho |
| 20 | Redactar historias de usuario iniciales derivadas de las personas (`USER_STORIES.md`) | Hecho |
| 21 | Inicializar glosario de términos del proyecto (`GLOSSARY.md`) | Hecho |

### Sprint 0.3 — Flujo de trabajo Git y CI/CD

| # | Historia / Tarea | Estado |
|---|---|---|
| 22 | Documentar convenciones de Gitflow (ramas, commits, PRs) en `CLAUDE.md` | Hecho |
| 23 | Configurar pipeline de CI en GitHub Actions (lint de Markdown y verificación de documentación obligatoria) | Hecho |
| 24 | Crear plantilla de Pull Request y plantilla de ADR | Hecho |
| 25 | Inicializar repositorio remoto en GitHub y ramas `main`/`develop` | Hecho |

## Fase 1 — Diseño del roadmap educativo

| # | Historia / Tarea | Estado |
|---|---|---|
| 6 | Como estudiante objetivo, quiero una estructura curricular por niveles (fundamentos → agentes/MCP → producción), para saber qué ruta de aprendizaje seguir | Pendiente |
| 7 | Como Tech Lead, quiero especificar el primer proyecto práctico como historia de usuario completa, para que sirva de plantilla a los siguientes módulos | Pendiente |
| 8 | Como equipo, queremos un diseño aprobado del flujo de aprendizaje, para iniciar el MVP con una base validada | Pendiente |
| US-01 | Explorar la ruta de aprendizaje por niveles (Daniela) — ver `USER_STORIES.md` | En diseño |
| US-02 | Entender el objetivo de un proyecto antes de empezarlo (Sofía) — ver `USER_STORIES.md` | En diseño |
| US-05 | Aprender MCP con contenido trazable a la fuente oficial (Marco) — ver `USER_STORIES.md` | En diseño |

## Fase 2 — MVP de plataforma

| # | Historia / Tarea | Estado |
|---|---|---|
| 9 | Diseño técnico aprobado (arquitectura, autenticación, persistencia) | Pendiente |
| 10 | Implementación incremental del primer módulo educativo, con pruebas automatizadas | Pendiente |
| 11 | Observabilidad y seguridad básicas desde el primer despliegue | Pendiente |
| US-03 | Practicar el ciclo completo de ingeniería en un proyecto (Marco) — ver `USER_STORIES.md` | En diseño |
| US-04 | Registrar decisiones de diseño en formato ADR (Daniela) — ver `USER_STORIES.md` | En diseño |
| US-06 | Mostrar evidencia de un proyecto completado (Sofía) — ver `USER_STORIES.md` | En diseño |
| US-07 | Ver mi progreso a través del roadmap (Daniela) — ver `USER_STORIES.md` | En diseño |

## Fase 3 — Expansión de contenido práctico

| # | Historia / Tarea | Estado |
|---|---|---|
| 12 | Módulos avanzados basados en MCP y agentes con Claude Code | Pendiente |
| 13 | Proyectos reales adicionales alineados con el público objetivo | Pendiente |
| 14 | Mecanismos de seguimiento de progreso del estudiante | Pendiente |
| US-05 | Aprender MCP con contenido trazable a la fuente oficial (Marco) — profundización, ver `USER_STORIES.md` | En diseño |
| US-06 | Mostrar evidencia de un proyecto completado (Sofía) — extensión de portafolio, ver `USER_STORIES.md` | En diseño |

## Fase 4 — Madurez y comunidad

| # | Historia / Tarea | Estado |
|---|---|---|
| 15 | Flujo de contribución externa definido | Pendiente |
| 16 | Evaluación de necesidades de escalabilidad e infraestructura, justificadas vía ADR | Pendiente |
| 17 | Revisión de accesibilidad y observabilidad en producción | Pendiente |

---

**Nota sobre las historias US-01 a US-07:** provienen de `USER_STORIES.md` (Sprint 0.2, diseño de producto) y se listan aquí como `En diseño` para trazabilidad. Ninguna pasa a `Aprobado` sin diseño técnico revisado, y ninguna se implementa en código sin ese diseño aprobado, conforme a `CLAUDE.md`.

Este backlog se mantiene sincronizado con `ROADMAP.md`, `USER_STORIES.md` y `CHANGELOG.md` en cada cambio, conforme a las reglas del proyecto.
