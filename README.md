# .github

Repositorio de **ficheros de comunidad por defecto** de la organización
[OTAZU](https://github.com/Otazu-DTO).

GitHub usa estos ficheros en cualquier repositorio de la organización que no
tenga el suyo propio, **incluidos los privados**. Cambiar una plantilla aquí la
cambia en todos los proyectos de golpe.

## Contenido

| Ruta | Para qué sirve |
| ---- | -------------- |
| `profile/README.md` | Portada pública de la organización. |
| `SECURITY.md` | Canal y procedimiento para reportar vulnerabilidades. |
| `CONTRIBUTING.md` | Modelo de ramas, commits y pull requests. |
| `.github/PULL_REQUEST_TEMPLATE.md` | Checklist por defecto de los PR. |
| `.github/ISSUE_TEMPLATE/` | Plantillas de issue (bug, funcionalidad, seguridad). |

## Reglas

- El repositorio debe seguir siendo **público**: GitHub solo hereda los
  ficheros de comunidad desde un `.github` público.
- Si un proyecto necesita una plantilla distinta, la define en su propio
  repositorio y esta se ignora para ese proyecto.
- Los cambios se hacen por pull request, como en el resto de repositorios.
- `CODEOWNERS` **no** se hereda: cada repositorio debe tener el suyo.
