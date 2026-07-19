Construir una plataforma web moderna donde un estudiante pueda convertirse en AI Engineer Senior siguiendo un roadmap práctico basado en proyectos reales.

Reglas:
No escribir código sin que exista una historia de usuario y un diseño aprobado.
Mantener actualizados README.md, CHANGELOG.md, BACKLOG.md y la documentación técnica en cada cambio.
Registrar las decisiones arquitectónicas importantes mediante ADR.
Añadir pruebas automatizadas para toda funcionalidad nueva o modificada.
Seguir las convenciones de estilo, nomenclatura y estructura del repositorio.
No incorporar dependencias o servicios externos sin justificar su necesidad.
Priorizar simplicidad, seguridad, accesibilidad y observabilidad desde el inicio.
Basar el contenido educativo relacionado con Claude y MCP en la documentación oficial de Anthropic.
Realizar cambios pequeños e incrementales, completando un sprint antes de iniciar el siguiente.
Mantener el código, la documentación y el backlog sincronizados en todo momento.

Convenciones de Git (Gitflow simplificado):

- `main`: rama estable, siempre desplegable. No se commitea directamente sobre ella.
- `develop`: rama de integración de trabajo en curso, base de las ramas de feature.
- Ramas de trabajo, creadas desde `develop`:
  - `feature/<descripcion-corta>`: nueva funcionalidad o documentación (ej. `feature/product-design-docs`).
  - `fix/<descripcion-corta>`: corrección de errores.
  - `docs/<descripcion-corta>`: cambios exclusivos de documentación.
  - `chore/<descripcion-corta>`: mantenimiento, configuración, tooling.
- `release/<version>`: preparación de una versión antes de fusionar a `main` (cuando exista versionado formal).
- `hotfix/<descripcion-corta>`: corrección urgente sobre `main`, fusionada de vuelta a `main` y `develop`.
- Todo cambio llega a `develop` o `main` mediante Pull Request, nunca por push directo.
- Cada PR debe pasar el pipeline de CI/CD (GitHub Actions) antes de poder fusionarse.
- Commits siguen [Conventional Commits](https://www.conventionalcommits.org/) (`feat:`, `fix:`, `docs:`, `chore:`, `refactor:`, `test:`), para mantener `CHANGELOG.md` y el historial trazables.
- Cada PR referencia el ítem correspondiente de `BACKLOG.md` y, si aplica, el ADR relacionado.
