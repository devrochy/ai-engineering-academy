# Changelog

Todos los cambios relevantes de este proyecto se documentan en este archivo.

El formato sigue las convenciones de [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/).

## [No publicado]

### Añadido

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
