# TECH_STACK.md — Stack Tecnológico

**Estado:** Aprobado

**Fecha:** 2026-07-19

Este documento concreta, dentro de los límites ya decididos por `docs/adr/0001-arquitectura-inicial-de-la-plataforma.md` (**Aceptado**), qué tecnologías específicas componen cada capa. No reabre las decisiones de fondo del ADR (Next.js, PostgreSQL, autenticación delegada, hosting gestionado); selecciona las herramientas concretas dentro de esas decisiones, tal como el propio ADR preveía en su sección de Consecuencias.

Cada elección sigue la regla de `CLAUDE.md`: **no incorporar dependencias sin justificar su necesidad**.

## Resumen por capa

| Capa | Tecnología | Justificación breve |
|---|---|---|
| Framework de aplicación | Next.js (App Router), TypeScript | Decidido en `ADR-0001`; App Router es el modelo de enrutamiento vigente del framework, con Route Handlers como capa de API |
| UI / Componentes | React (incluido en Next.js) | Parte del mismo framework; no es una dependencia adicional |
| Estilos | CSS con un sistema de utilidades (ej. Tailwind CSS) | Reduce la necesidad de escribir y mantener hojas de estilo propias; amplia adopción en el ecosistema Next.js |
| ORM / acceso a datos | Un ORM tipado para TypeScript (ej. Prisma) | Evita SQL manual disperso, genera tipos a partir del esquema, incluye sistema de migraciones — reduce errores de persistencia |
| Base de datos | PostgreSQL gestionado (proveedor a confirmar en el diseño de despliegue) | Decidido en `ADR-0001` |
| Autenticación | Librería de autenticación para Next.js sobre OAuth (ej. Auth.js) | Decidido en `ADR-0001`; evita manejo propio de credenciales |
| Validación de datos | Librería de validación de esquemas en el borde de la API (ej. Zod) | Necesaria para no confiar en datos de entrada sin validar (ver `SECURITY.md`) |
| Pruebas automatizadas | Framework de pruebas unitarias/integración para TypeScript (ej. Vitest) + herramienta de pruebas end-to-end (ej. Playwright) | Requisito de `CLAUDE.md`: toda funcionalidad nueva necesita pruebas automatizadas |
| CI | GitHub Actions | Ya en uso (`.github/workflows/ci.yml`); se extiende con jobs de tipado, pruebas y build cuando exista código |
| Hosting / despliegue | Plataforma gestionada compatible con Next.js (proveedor a confirmar) | Decidido en `ADR-0001` |
| Observabilidad | Logs y métricas nativos de la plataforma de hosting elegida | Ver `SECURITY.md` y `BACKEND.md` para el detalle de qué se registra |

## Justificación detallada de dependencias nuevas

Siguiendo el formato ya usado en `ADR-0001`:

- **ORM tipado (ej. Prisma):** sin él, el acceso a datos requeriría SQL escrito y mantenido a mano en cada Route Handler, sin verificación de tipos entre el esquema de base de datos y el código. Un ORM tipado reduce una clase entera de errores (columnas inexistentes, tipos incompatibles) detectándolos en tiempo de compilación, y provee un sistema de migraciones versionadas — necesario para evolucionar el esquema de `DATABASE.md` de forma controlada.
- **Librería de validación de esquemas (ej. Zod):** la API recibe datos de un cliente no confiable (el navegador). Sin validación explícita en el borde, cualquier endpoint queda expuesto a datos malformados o maliciosos. Es la implementación concreta del principio de seguridad "no confiar en la entrada" descrito en `SECURITY.md`.
- **Sistema de utilidades CSS (ej. Tailwind):** alternativa a escribir y mantener CSS propio disperso en múltiples archivos; reduce el tiempo de construcción de UI y mantiene consistencia visual sin introducir un sistema de diseño propio a medida, que sería un esfuerzo desproporcionado para el MVP.
- **Framework de pruebas end-to-end (ej. Playwright):** las pruebas unitarias no verifican que el flujo completo (login → ver catálogo → inscribirse → ver progreso) funcione integrado. Es la forma concreta de cumplir el requisito de `CLAUDE.md` de pruebas automatizadas para funcionalidad de usuario final.

## Selección de proveedores concretos (pendiente)

`ADR-0001` deja explícitamente la selección de proveedor concreto (hosting, PostgreSQL gestionado) fuera de su alcance. Este documento tampoco la fija: se resolverá como parte de la Task de despliegue dentro de `BACKLOG.md` (FEAT-05.1), evaluando criterios de costo, límites del plan gratuito/inicial y compatibilidad con Next.js — sin que esa selección requiera un nuevo ADR, salvo que implique cambiar la decisión de fondo (por ejemplo, abandonar PostgreSQL).

## Fuera de alcance de este documento

- Versión exacta (pin) de cada librería — se fija en el archivo de dependencias del proyecto cuando exista código, no en este documento de arquitectura.
- Configuración de infraestructura como código — no evaluada aún; requeriría su propia justificación si se propone.

## Trazabilidad

- Decisión de base: `docs/adr/0001-arquitectura-inicial-de-la-plataforma.md`.
- Vista general: `ARCHITECTURE.md`.
- Backlog: `BACKLOG.md`, TASK-05.1.1.
