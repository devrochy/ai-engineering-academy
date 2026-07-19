# ROADMAP — AI Engineering Academy

Roadmap de alto nivel. No implica compromiso de fechas; cada fase se detalla en historias de usuario y ADRs propios antes de iniciarse, conforme a las reglas del proyecto.

## Fase 0 — Fundación (actual)

- [x] Definir misión, visión y propuesta de valor (`VISION.md`).
- [x] Definir README del proyecto.
- [ ] Definir estructura inicial de BACKLOG.md y CHANGELOG.md.
- [ ] Primer ADR: decisiones de arquitectura para la plataforma (stack, hosting, modelo de datos educativo).

## Fase 1 — Diseño del roadmap educativo

- [ ] Definir la estructura curricular por niveles (fundamentos → agentes/MCP → producción).
- [ ] Especificar el primer proyecto práctico como historia de usuario.
- [ ] Diseño aprobado del flujo de aprendizaje (sin implementación de plataforma todavía).

## Fase 2 — MVP de plataforma

- [ ] Diseño técnico aprobado (arquitectura, autenticación, persistencia).
- [ ] Implementación incremental del primer módulo educativo, con pruebas automatizadas.
- [ ] Observabilidad y seguridad básicas desde el primer despliegue.

## Fase 3 — Expansión de contenido práctico

- [ ] Módulos avanzados basados en MCP y agentes con Claude Code.
- [ ] Proyectos reales adicionales alineados con el público objetivo.
- [ ] Mecanismos de seguimiento de progreso del estudiante.

## Fase 4 — Madurez y comunidad

- [ ] Flujo de contribución externa definido.
- [ ] Evaluación de necesidades de escalabilidad e infraestructura, justificadas y documentadas vía ADR.
- [ ] Revisión de accesibilidad y observabilidad en producción.

---

Cada fase se activa solo cuando la anterior está completa, según la regla de "no avanzar a la siguiente iteración sin completar la actual" definida en `CLAUDE.md`.
