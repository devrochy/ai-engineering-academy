# GLOSSARY.md — Glosario del Proyecto

Definiciones de términos usados en la documentación de AI Engineering Academy, para mantener un lenguaje consistente entre `PRODUCT.md`, `PERSONAS.md`, `USER_STORIES.md`, `ROADMAP.md`, `BACKLOG.md` y los ADRs futuros.

---

## Términos de producto y proceso

**ADR (Architecture Decision Record)**
Documento breve que registra una decisión arquitectónica relevante: contexto, opciones consideradas, decisión tomada y consecuencias. Se usa para toda decisión de arquitectura significativa, según `CLAUDE.md`.

**Backlog**
Registro vivo de historias de usuario y tareas pendientes, organizado por fase, con su estado actual. Ver `BACKLOG.md`.

**Changelog**
Registro cronológico de cambios relevantes del proyecto, siguiendo la convención Keep a Changelog. Ver `CHANGELOG.md`.

**Criterio de aceptación**
Condición verificable que debe cumplirse para considerar una historia de usuario como completada.

**Historia de usuario**
Descripción breve de una funcionalidad desde la perspectiva de quien la usa, con el formato "Como [persona], quiero [objetivo], para [beneficio]". Ninguna historia se implementa en código sin diseño aprobado.

**Persona**
Perfil arquetípico de un tipo de usuario objetivo del producto, con sus objetivos, contexto y frustraciones. Ver `PERSONAS.md`.

**Roadmap**
Plan de alto nivel que secuencia las fases del proyecto en el tiempo, sin comprometer fechas exactas. Ver `ROADMAP.md`.

**Sprint**
Ciclo de trabajo incremental y acotado, enfocado en completar un conjunto pequeño de historias antes de iniciar el siguiente, según el principio de `CLAUDE.md` de "no avanzar a la siguiente iteración sin completar la actual".

---

## Términos de dominio (IA / Claude / MCP)

**Agente (AI Agent)**
Sistema que usa un modelo de lenguaje para decidir y ejecutar acciones de forma autónoma o semiautónoma, típicamente invocando herramientas o servicios externos para lograr un objetivo.

**Claude**
Familia de modelos de lenguaje desarrollados por Anthropic, usados como motor de razonamiento en los proyectos prácticos de la Academia.

**Claude Code**
Herramienta de línea de comandos y agente de ingeniería de software de Anthropic, que permite a Claude leer, escribir y ejecutar código, e interactuar con herramientas del entorno de desarrollo. Es la herramienta de trabajo central del roadmap práctico de este proyecto.

**LLM (Large Language Model)**
Modelo de lenguaje de gran escala, entrenado para generar y comprender texto (y en algunos casos otras modalidades), base técnica de Claude y de los agentes construidos sobre él.

**MCP (Model Context Protocol)**
Protocolo abierto, definido por Anthropic, que estandariza cómo las aplicaciones proporcionan contexto y herramientas a los modelos de lenguaje, permitiendo que agentes como Claude se conecten de forma uniforme a fuentes de datos y servicios externos.

**Prompt / Prompting**
Instrucción o entrada de texto (y contexto asociado) que se proporciona a un LLM para obtener una respuesta o acción. La Academia trata el prompting como una herramienta dentro de un proceso de ingeniería mayor, no como el objetivo final del aprendizaje.

**RAG (Retrieval-Augmented Generation)**
Técnica que combina la recuperación de información desde una fuente externa (por ejemplo, una base de conocimiento) con la generación de texto de un LLM, para producir respuestas fundamentadas en datos concretos.

---

## Términos de ingeniería de software aplicados en este proyecto

**CI/CD (Integración Continua / Entrega Continua)**
Prácticas de automatización para integrar, probar y desplegar cambios de software de forma frecuente y confiable. Mencionado como competencia a desarrollar en el público objetivo; su implementación concreta está fuera del alcance de este sprint.

**Observabilidad**
Capacidad de entender el estado interno de un sistema a partir de sus salidas (logs, métricas, trazas). Principio rector del proyecto desde las fases iniciales, según `CLAUDE.md`.

**Pruebas automatizadas**
Código que verifica automáticamente el comportamiento esperado de una funcionalidad. Requisito obligatorio para toda funcionalidad nueva o modificada, según `CLAUDE.md`.

---

*Este glosario se actualiza cada vez que se introduce un término nuevo y relevante en la documentación del proyecto.*
