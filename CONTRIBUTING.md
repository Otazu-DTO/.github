# Cómo contribuir

Convenciones de trabajo del equipo de tecnología de OTAZU. Se aplican a todos
los repositorios de la organización salvo que un proyecto defina lo contrario.

## Modelo de ramas

| Rama | Propósito | Sale de | Despliegue |
| ---- | --------- | ------- | ---------- |
| `main` | Producción. Siempre estable. | — | Producción |
| `develop` | Integración del trabajo en curso. | `main` | Desarrollo / pruebas |
| `feat/<ticket>-<desc>` | Nueva funcionalidad. | `develop` | — |
| `fix/<ticket>-<desc>` | Corrección no urgente. | `develop` | — |
| `release/x.y.z` | Release candidate en estabilización. | `develop` | Staging |
| `hotfix/<ticket>-<desc>` | Corrección urgente en producción. | `main` | Producción |

Nada se sube directamente a `main` ni a `develop`: todo entra por pull request
revisada.

## Commits

Formato [Conventional Commits](https://www.conventionalcommits.org/es/v1.0.0/):

```text
<tipo>(<alcance>): <descripción en imperativo>

<cuerpo opcional>

refs OTA-123
```

Tipos habituales: `feat`, `fix`, `refactor`, `docs`, `test`, `chore`, `ci`,
`perf`, `build`.

- Un commit = un cambio lógico, atómico y que compila.
- Mensaje en imperativo: describe el qué y el por qué.
- Referencia siempre el ticket de Linear.
- Nunca incluyas secretos, credenciales, tokens ni datos reales.

## Pull requests

- PRs pequeños y enfocados (idealmente menos de 400 líneas efectivas).
- Rellena la plantilla: resumen, ticket, tipo de cambio, pruebas y checklist de
  seguridad.
- Al menos **una aprobación** de otra persona; **dos** si el cambio toca
  autenticación, criptografía, datos personales o infraestructura.
- Nadie aprueba su propio código.
- Pipeline en verde antes del merge.
- Merge con *squash* e historial lineal; la rama de trabajo se borra al integrar.

## Seguridad

- Sin secretos en el repositorio ni en el historial. Si uno se filtra, se
  considera comprometido: **rótalo**, no basta con borrar el commit.
- Escaneo de dependencias y de secretos en cada PR; los hallazgos críticos y
  altos bloquean el merge salvo excepción aprobada.
- Dependencias nuevas justificadas y con licencia compatible.
- `.env` fuera del control de versiones; se versiona `.env.example` sin valores.

## Reportar vulnerabilidades

No abras una issue pública. Sigue [SECURITY.md](SECURITY.md).

## Documentación

Cada tema tiene **una sola** página canónica; si algo cambia, se actualiza la
existente en lugar de duplicarla.
