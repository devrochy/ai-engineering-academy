# ADR-0001: Arquitectura inicial de la plataforma

**Estado:** Aceptado

**Fecha:** 2026-07-19

## Contexto

`BACKLOG.md` (ítem 5) y `PRODUCT.md` (§4.2) dejan explícitamente pendiente cualquier decisión de stack técnico, hosting o modelo de datos hasta que exista un ADR aprobado. Antes de poder diseñar el MVP (Fase 2 de `ROADMAP.md`) o cualquier historia de usuario que implique código, se necesita una base arquitectónica mínima y justificada.

Restricciones que gobiernan esta decisión, tomadas de `CLAUDE.md`:

- Simplicidad, seguridad, accesibilidad y observabilidad desde el inicio.
- No incorporar dependencias o servicios externos sin justificar su necesidad.
- Cambios pequeños e incrementales — esta arquitectura debe soportar el MVP de Fase 2, no anticipar todas las fases futuras.
- No se escribe código sin historia de usuario y diseño aprobado — este ADR es una decisión de arquitectura, no una implementación.

Alcance de esta decisión: stack tecnológico de la aplicación, estrategia de hosting/despliegue, y forma general del modelo de datos educativo (entidades, no esquema completo). No incluye: proveedor de autenticación específico más allá de la estrategia, diseño visual, ni infraestructura de CI/CD adicional a la ya definida en `.github/workflows/ci.yml`.

## Opciones consideradas

### Stack de aplicación

| Opción | Pros | Contras |
|---|---|---|
| **Next.js (React) full-stack, monolito** | Un único proyecto (frontend + API routes); comunidad y documentación amplias; despliegue simple; TypeScript de punta a punta | Acopla frontend y backend; menos flexible si el backend crece mucho |
| Frontend SPA (React/Vue) + backend API separado (Node/Python) | Separación de responsabilidades clara; backend reutilizable por otros clientes | Dos proyectos, dos pipelines, más superficie operativa — contradice "simplicidad" para un MVP |
| Framework full-stack alternativo (Django, Rails) | Baterías incluidas (auth, admin, ORM) | Introduce un segundo lenguaje/ecosistema sin necesidad clara; menor alineación con el tipo de proyectos prácticos que la Academia enseña (TypeScript/JS es más común en el público objetivo definido en `PERSONAS.md`) |

### Base de datos

| Opción | Pros | Contras |
|---|---|---|
| **PostgreSQL (gestionado)** | Relacional, encaja con el modelo de datos educativo (entidades con relaciones claras); estándar de la industria; soporta crecimiento futuro (Fase 3-4) | Requiere un proveedor gestionado (servicio externo) |
| Base de datos NoSQL (ej. MongoDB) | Flexible para contenido no estructurado | El dominio (usuarios, niveles, proyectos, progreso) es fundamentalmente relacional; NoSQL añadiría complejidad sin beneficio claro |
| SQLite embebido | Cero infraestructura externa | No apto para una plataforma multiusuario con necesidad de concurrencia y backups gestionados |

### Autenticación

| Opción | Pros | Contras |
|---|---|---|
| **Librería de autenticación integrada al framework (ej. Auth.js) sobre proveedores OAuth estándar** | Evita construir manejo de contraseñas/sesiones desde cero (principio de seguridad de `CLAUDE.md`); reduce superficie de ataque | Introduce una dependencia externa — justificada explícitamente abajo |
| Autenticación propia (usuario/contraseña gestionado a mano) | Cero dependencias | Alto riesgo de seguridad para un equipo pequeño; contradice "priorizar seguridad desde el inicio" |

### Hosting

| Opción | Pros | Contras |
|---|---|---|
| **Plataforma gestionada compatible con el framework elegido (ej. Vercel para Next.js) + base de datos gestionada** | Despliegue simple, HTTPS y CI/CD de despliegue incluidos, encaja con el pipeline de GitHub Actions ya definido | Dependencia de un proveedor externo — justificada abajo |
| Infraestructura propia (VPS, contenedores autogestionados) | Control total | Añade carga operativa (observabilidad, parches, escalado) desproporcionada para la Fase 2 (MVP) |

## Decisión

1. **Stack**: aplicación full-stack en **Next.js (TypeScript)**, como monolito único (frontend + API routes) durante el MVP, para minimizar superficie operativa.
2. **Base de datos**: **PostgreSQL gestionado**, por ser la opción que mejor representa el modelo de datos educativo relacional.
3. **Autenticación**: librería de autenticación integrada al framework sobre proveedores OAuth estándar, en vez de una implementación propia de credenciales.
4. **Hosting**: plataforma gestionada compatible con Next.js, con despliegue automático desde `main` tras CI en verde, coherente con la protección de rama ya configurada en el repositorio.

### Justificación de dependencias externas (según regla de `CLAUDE.md`)

- **Next.js**: necesario para tener una aplicación web real; se elige por ser la opción que unifica frontend/backend con menor complejidad operativa para un equipo pequeño.
- **PostgreSQL gestionado**: necesario porque el producto requiere persistencia multiusuario (progreso de estudiantes, catálogo de proyectos); un proveedor gestionado evita que el equipo deba operar backups, parches de seguridad y alta disponibilidad manualmente.
- **Librería de autenticación**: necesaria porque construir manejo de contraseñas/sesiones a mano es un riesgo de seguridad injustificable para un equipo pequeño; delegar a una librería madura reduce la superficie de vulnerabilidades.
- **Plataforma de hosting gestionada**: necesaria para tener el sitio accesible con HTTPS y observabilidad básica (logs, métricas de despliegue) sin operar servidores propios, en línea con el principio de simplicidad y observabilidad desde el inicio.

Ningún proveedor específico (ej. Vercel vs. otra plataforma equivalente, o el proveedor concreto de PostgreSQL) se fija en este ADR — esa selección de proveedor concreto se hará en la historia de diseño técnico del MVP (`BACKLOG.md` #9), pudiendo optar por alternativas equivalentes sin requerir un nuevo ADR, salvo que cambie la decisión de fondo aquí registrada.

## Modelo de datos educativo (alto nivel)

Entidades conceptuales que se derivan de `PRODUCT.md`, `PERSONAS.md` y `USER_STORIES.md` (no es un esquema de base de datos, sino la forma general del dominio):

- **Estudiante**: usuario autenticado de la plataforma.
- **Nivel**: agrupación de proyectos por etapa del roadmap educativo (ver `ROADMAP.md`, Fase 1).
- **Proyecto**: unidad de aprendizaje práctica, con objetivo, prerrequisitos y resultado esperado (US-02).
- **Inscripción / Progreso**: relación entre Estudiante y Proyecto, con estado (no iniciado / en progreso / completado — US-07).
- **Evidencia**: artefacto entregado por el estudiante al completar un proyecto, usado como portafolio (US-06).

El esquema detallado (columnas, claves, migraciones) se define en la historia de diseño técnico del MVP (`BACKLOG.md` #9), no en este ADR.

## Consecuencias

**Se gana:**

- Una base técnica única y coherente para empezar a diseñar el MVP (Fase 2), sin bloquear el roadmap educativo (Fase 1), que puede avanzar en paralelo por ser independiente del stack.
- Superficie operativa mínima: un solo proyecto de código, una base de datos, un proveedor de hosting.
- Alineación directa con los principios de seguridad (autenticación delegada) y observabilidad (hosting gestionado) de `CLAUDE.md`.

**Se sacrifica / queda pendiente:**

- Dependencia de servicios externos gestionados (hosting, base de datos, proveedor OAuth) en vez de infraestructura propia — aceptado conscientemente por ser desproporcionado operar infraestructura propia en esta etapa.
- La selección de proveedores concretos, el esquema de base de datos detallado y la arquitectura de autorización (roles, permisos) quedan para la historia de diseño técnico del MVP (`BACKLOG.md` #9).
- Si el producto evoluciona hacia necesidades que el monolito no pueda sostener (por ejemplo, separar backend por escalabilidad), esa evolución requerirá un nuevo ADR que reemplace o extienda este.

## Trazabilidad

- Backlog: `BACKLOG.md` #5 (este ADR) y #9 (diseño técnico detallado del MVP, sucesor de esta decisión).
- Producto: `PRODUCT.md` §4.2, que remite explícitamente esta decisión a un ADR.
- Roadmap: `ROADMAP.md`, Fase 0 (este ADR) y Fase 2 (MVP de plataforma, que consume esta decisión).
