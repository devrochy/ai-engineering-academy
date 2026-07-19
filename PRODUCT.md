# PRODUCT.md — Definición de Producto

## 1. Problema

Existe una brecha entre "saber usar un modelo de lenguaje" y "ser capaz de construir, probar, documentar y operar un sistema de IA en producción". La mayoría de los recursos educativos disponibles se centran en prompting o en demos de un solo archivo, sin cubrir el oficio completo de ingeniería de software (historias de usuario, diseño, pruebas, control de cambios, observabilidad) aplicado a proyectos de IA.

## 2. Propuesta de producto

**AI Engineering Academy** es una plataforma de formación práctica donde cada unidad de aprendizaje es un proyecto real, guiado por un roadmap incremental, construido con Claude Code y el Model Context Protocol (MCP) como herramientas de trabajo, no como simple tema de estudio.

La propuesta de valor completa está definida en [VISION.md](./VISION.md); este documento la traduce a decisiones de producto: qué se construye, para quién, y qué queda explícitamente fuera de alcance.

## 3. Objetivos de producto

1. Ofrecer una ruta de aprendizaje estructurada por niveles, ancorada en proyectos verificables (no ejercicios aislados).
2. Enseñar el ciclo de ingeniería completo: historia de usuario → diseño → implementación incremental → pruebas → documentación.
3. Mantener el contenido sobre Claude y MCP alineado con la documentación oficial de Anthropic en todo momento.
4. Permitir que el estudiante demuestre progreso con evidencia tangible (proyectos funcionales, no solo insignias).

## 4. Alcance funcional (alto nivel)

> Nota: esta sección describe **qué debería existir conceptualmente** en el producto. Ninguna de estas funcionalidades se implementa sin su propia historia de usuario, diseño técnico aprobado y ADR cuando corresponda, según `CLAUDE.md`.

### 4.1 Dentro de alcance (visión de producto a mediano plazo)

- Catálogo de proyectos prácticos organizados por nivel (fundamentos, agentes/MCP, producción).
- Seguimiento de progreso del estudiante a través de los proyectos.
- Contenido de referencia sobre Claude Code y MCP, trazable a documentación oficial de Anthropic.
- Mecanismo para que el estudiante entregue evidencia de un proyecto completado (portafolio).

### 4.2 Fuera de alcance (explícitamente, por ahora)

- Certificaciones oficiales o acreditación externa.
- Mentoría en vivo o soporte humano 1:1.
- Marketplace de contenido de terceros.
- Cualquier funcionalidad de monetización, pagos o suscripciones — no evaluada aún; requerirá su propia justificación y ADR si se propone en el futuro.
- Infraestructura, autenticación, base de datos o cualquier decisión de stack técnico: pertenecen a un ADR de arquitectura pendiente (ver `BACKLOG.md`, ítem 5), no a este documento.

## 5. Principios de producto

- **Proyecto real por encima de ejercicio de juguete**: si no se puede construir y ejecutar, no es un módulo válido.
- **Rigor documental**: toda decisión de producto relevante se refleja en `BACKLOG.md`, `CHANGELOG.md` y, si es arquitectónica, en un ADR.
- **Fidelidad a la fuente**: el contenido sobre Claude y MCP no se improvisa; se basa en documentación oficial de Anthropic.
- **Incremental por diseño**: se prioriza completar y validar una fase antes de expandir el alcance (ver `ROADMAP.md`).

## 6. Métricas de éxito (a validar)

> Estas métricas son hipótesis de producto, no compromisos. Se refinarán cuando exista una primera versión del roadmap educativo (Fase 1) y, más adelante, un MVP medible (Fase 2).

- Porcentaje de estudiantes que completan al menos un proyecto real end-to-end.
- Tiempo medio hasta la primera entrega funcional por estudiante.
- Calidad percibida del contenido técnico sobre Claude/MCP (revisión frente a documentación oficial).
- Consistencia entre roadmap, backlog y estado real del producto (métrica interna de proceso, no de usuario).

## 7. Relación con otros documentos

| Documento | Rol respecto a `PRODUCT.md` |
|---|---|
| [VISION.md](./VISION.md) | Define el "por qué" (misión, visión, propuesta de valor) |
| [PERSONAS.md](./PERSONAS.md) | Detalla a quién sirve el producto |
| [USER_STORIES.md](./USER_STORIES.md) | Traduce el alcance funcional en historias verificables |
| [GLOSSARY.md](./GLOSSARY.md) | Fija el lenguaje común usado en este documento y en los demás |
| [ROADMAP.md](./ROADMAP.md) | Secuencia temporal de cuándo se aborda cada parte del alcance |
| [BACKLOG.md](./BACKLOG.md) | Estado operativo de cada historia derivada de este documento |
