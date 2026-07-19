# Changelog

Todos los cambios relevantes de este proyecto se documentan en este archivo.

El formato sigue las convenciones de [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/).

## [No publicado]

### Añadido

- `PROJECT_BIBLE.md`: **Single Source of Truth del proyecto (Aprobado)**, 38 capítulos que consolidan y resumen —sin duplicar— la estrategia, el producto y la arquitectura ya definidos en `CLAUDE.md`, `README.md`, `VISION.md`, `PRODUCT.md`, `PERSONAS.md`, `USER_STORIES.md`, `GLOSSARY.md`, `ROADMAP.md`, `ROADMAP_DEVELOPMENT.md`, `BACKLOG.md`, `ADR-0001` y los 9 documentos de arquitectura. Incluye diagrama de contexto Mermaid, Definition of Done, reglas para crear/modificar funcionalidades y próximos pasos concretos. *(Sprint 0.7)*
- **Arquitectura del sistema (Aprobada), 9 documentos con diagramas Mermaid (14 en total)** *(Sprint 0.6)*:
  - `ARCHITECTURE.md`: vista de contexto y de contenedores, principios arquitectónicos, límites explícitos del MVP.
  - `TECH_STACK.md`: selección concreta de tecnologías (Next.js/TypeScript, Prisma, Zod, Tailwind, Vitest, Playwright) dentro de los límites de `ADR-0001`, con justificación de cada dependencia nueva.
  - `DATABASE.md`: modelo entidad-relación detallado (Student, Level, Project, Enrollment, Evidence) y diagrama de estados de `Enrollment`.
  - `API.md`: inventario de endpoints REST del MVP, convenciones, formatos de petición/respuesta y manejo de errores.
  - `BACKEND.md`: arquitectura en capas (routes → middleware → validación → servicios → datos), servicios de dominio previstos.
  - `FRONTEND.md`: mapa de rutas, composición de componentes, estrategia de manejo de estado (sin librería global en el MVP), requisitos de accesibilidad.
  - `SECURITY.md`: modelo de amenazas simplificado, flujo de autenticación OAuth, autorización, gestión de secretos, observabilidad de seguridad.
  - `MCP.md`: distingue el rol vigente de MCP como contenido educativo del rol futuro (no decidido) como componente técnico de la plataforma.
  - `AI_ARCHITECTURE.md`: distingue el rol vigente de la IA como materia de enseñanza del rol futuro (no decidido) como componente del producto; el runtime del MVP no realiza llamadas a modelos de lenguaje.
- `ROADMAP_DEVELOPMENT.md`: roadmap de desarrollo dividido en sprints (1.1–1.4 para la Fase 1 de diseño educativo; 2.1–2.4 para la Fase 2 de MVP), con criterios de salida por sprint y bloqueo explícito de Tasks de código hasta diseño técnico aprobado. *(Sprint 0.5)*
- `docs/adr/0001-arquitectura-inicial-de-la-plataforma.md`: **ADR-0001 (Aceptado)** — stack full-stack en Next.js (TypeScript), PostgreSQL gestionado, autenticación delegada (OAuth) y hosting gestionado; incluye modelo de datos educativo de alto nivel (Estudiante, Nivel, Proyecto, Inscripción/Progreso, Evidencia). *(Sprint 0.4)*
- `.github/workflows/ci.yml`: pipeline de CI en GitHub Actions (lint de Markdown y verificación de documentación obligatoria) en cada PR/push a `main` o `develop`. *(Sprint 0.3)*
- `.github/pull_request_template.md`: plantilla de Pull Request con checklist alineado a `CLAUDE.md`. *(Sprint 0.3)*
- `docs/adr/template.md`: plantilla de Architecture Decision Record. *(Sprint 0.3)*
- `.markdownlint.yaml`: configuración de reglas de lint de Markdown usada por el CI. *(Sprint 0.3)*
- `PRODUCT.md`: problema, propuesta de producto, objetivos, alcance funcional (dentro y fuera de alcance) y métricas de éxito hipotéticas. *(Sprint 0.2)*
- `PERSONAS.md`: tres personas de usuario objetivo (Daniela, Marco, Sofía) con objetivos, frustraciones y necesidades. *(Sprint 0.2)*
- `USER_STORIES.md`: siete historias de usuario (US-01 a US-07) agrupadas en cuatro épicas, con criterios de aceptación, derivadas de `PERSONAS.md`. *(Sprint 0.2)*
- `GLOSSARY.md`: glosario de términos de producto, dominio (Claude, MCP, LLM, RAG, agente) e ingeniería de software. *(Sprint 0.2)*
- `VISION.md`: misión, visión, público objetivo, propuesta de valor, alcance inicial y principios rectores. *(Sprint 0.1)*
- `README.md`: portada del proyecto, estado actual y guía de cómo se trabaja en el repositorio. *(Sprint 0.1)*
- `ROADMAP.md`: plan de alto nivel por fases (Fundación, Diseño curricular, MVP, Expansión, Madurez). *(Sprint 0.1)*
- `BACKLOG.md`: registro inicial de historias de usuario y tareas pendientes por fase. *(Sprint 0.1)*
- `CHANGELOG.md`: este archivo. *(Sprint 0.1)*

### Cambiado

- `BACKLOG.md`: incorporadas las historias US-01 a US-07 (estado `En diseño`) distribuidas en las fases 0, 2 y 3, y añadida la sección "Sprint 0.2 — Diseño de producto" en la Fase 0. *(Sprint 0.2)*
- `BACKLOG.md`: añadida la sección "Sprint 0.3 — Flujo de trabajo Git y CI/CD" en la Fase 0. *(Sprint 0.3)*
- `CLAUDE.md`: añadidas las convenciones de Gitflow (ramas `main`/`develop`, `feature/`, `fix/`, `docs/`, `chore/`, `release/`, `hotfix/`, Conventional Commits, PR obligatorio con CI en verde). *(Sprint 0.3)*
- `BACKLOG.md`: marcado como `Hecho` el ítem 25 (repositorio remoto en GitHub y ramas `main`/`develop` publicadas). *(Sprint 0.3)*

### Infraestructura de repositorio

- Creado el repositorio remoto público [`devrochy/ai-engineering-academy`](https://github.com/devrochy/ai-engineering-academy) en GitHub. *(Sprint 0.3)*
- Publicadas las ramas `main` y `develop`; `main` configurada como rama por defecto. *(Sprint 0.3)*
- Aplicada protección de rama en `main`: requiere que los checks de CI (`Lint Markdown`, `Verificar documentación obligatoria`) pasen antes de mergear, y prohíbe force-push y borrado directo. *(Sprint 0.3)*

### Cambiado (Sprint 0.4)

- `BACKLOG.md`: ítem 5 marcado como `Hecho`; ítem 9 redefinido como sucesor de `ADR-0001` (diseño técnico detallado del MVP); añadida la sección "Sprint 0.4 — Arquitectura inicial".

### Cambiado (Sprint 0.5)

- `BACKLOG.md`: reestructurado por completo a jerarquía **Epic → Feature → Story → Task → Subtask** (EPIC-00 a EPIC-05), reemplazando el listado plano por fases. Todas las historias US-01 a US-07 y los ítems de trabajo previos quedan mapeados a Features/Tasks concretas; se añaden las Stories US-08, US-09 y US-10 para el MVP técnico (EPIC-05).
- `README.md`: ampliada la tabla de documentación con enlaces a `PRODUCT.md`, `PERSONAS.md`, `USER_STORIES.md`, `BACKLOG.md`, `ROADMAP_DEVELOPMENT.md` y `GLOSSARY.md`.

### Cambiado (Sprint 0.6)

- `BACKLOG.md`: añadida `FEAT-00.5 — Arquitectura detallada del sistema` (Hecho) en EPIC-00. `TASK-05.1.1` y `TASK-05.3.1` pasan de `Pendiente` a `En progreso`: sus Subtasks de diseño quedan resueltas por los nuevos documentos de arquitectura; la selección de proveedor concreto de hosting/PostgreSQL sigue explícitamente pendiente, según lo diferido en `TECH_STACK.md`.

### Cambiado (Sprint 0.7)

- `BACKLOG.md`: añadida `FEAT-00.6 — Project Bible (SSOT)` (Hecho) en EPIC-00.
- `README.md`: añadido enlace destacado a `PROJECT_BIBLE.md` como punto de entrada recomendado para cualquier persona nueva en el proyecto.
