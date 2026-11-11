# Productos y repositorios

Índice de los productos de OTAZU y de los repositorios que los componen.

- **Fuente de verdad para agrupar repos:** las *custom properties* de la
  organización (`producto`, `tipo`, `estado`, `criticidad`). Se pueden consultar
  por API y usar para filtrar y para políticas de seguridad.
- **Fuente de verdad para la ejecución:** [Linear](https://linear.app/otazu),
  proyecto por producto. Este fichero no duplica el tablero.
- Este documento es el índice humano: qué repos forman cada producto y quién
  responde de ellos.

## Productos

| Producto | Repositorios | Qué es | Linear |
| -------- | ------------ | ------ | ------ |
| **LAVOS** | `lavos`, `lavos-platform` | Nueva plataforma Go + React que sustituye la intranet. `lavos` es la documentación (arquitectura, ADRs, migración); `lavos-platform` es el código. | LAVOS |
| **OTAZU Web** | `web-otazu`*, `bruno_collections`* | Web pública, motor de reservas y backoffice (Next.js + Express + Prisma). `bruno_collections` son las colecciones de API del equipo. | Página web de Otazu |
| **Otazu Rewards** | `otazu-rewards` | Portal de agencias, comisiones y ficha CRM. | Otazu Rewards |
| **Intranet** | `otazuapp`* | Intranet corporativa (Laravel + SQL Server), en migración a LAVOS. | Intranet de Otazu |
| **Fundamentos** | `dto-template`, `docs-hub`, `linear-cli`, `.github` | Estándar técnico, plantilla full-stack, documentación canónica y utilidades del equipo. | Fundamentos |
| **Ciberseguridad** | `otazu-security` | SGSI, diagnóstico, evidencias y plan de trabajo de seguridad. | Ciberseguridad |
| **Maploca** | — | Web de Maploca y las siderúrgicas del grupo. | Maploca |
| **Marketing** | — | CRM, analítica de RRSS y campañas. | Marketing |
| **Inteligencia comercial** | `inteligencia_comercial`* | Datos y análisis comercial. | Por definir |

\* Repositorio pendiente de migrar a `Otazu-DTO` (ver más abajo).

## Repositorios actuales

| Repositorio | Producto | Tipo | Estado | Criticidad |
| ----------- | -------- | ---- | ------ | ---------- |
| `lavos` | LAVOS | docs | activo | alta |
| `lavos-platform` | LAVOS | platform | activo | alta |
| `otazu-rewards` | Otazu Rewards | app | activo | alta |
| `dto-template` | Fundamentos | template | activo | alta |
| `docs-hub` | Fundamentos | docs | activo | media |
| `otazu-security` | Ciberseguridad | docs | activo | alta |
| `linear-cli` | Fundamentos | tooling | mantenimiento | baja |
| `.github` | Fundamentos | org | activo | media |

## Migraciones pendientes

| Repositorio | Origen | Producto destino | Notas |
| ----------- | ------ | ---------------- | ----- |
| `web-otazu` | org `web-otazu` | OTAZU Web | Esperar al release 2.0. Conserva PRs, issues, secrets y deploy keys con una transferencia. Requiere deploy keys habilitadas en la org (ya hecho). |
| `bruno_collections` | org `web-otazu` | OTAZU Web | Sin workflows ni secrets; transferencia directa. |
| `otazuapp` | cuenta personal `moisesz01` | Intranet | Migrar antes de empezar el *strangler* de LAVOS. |
| `inteligencia_comercial` | cuenta personal | Inteligencia comercial | Evaluar si se archiva o se mantiene. |

## Convenciones

- **Un producto puede tener varios repos.** El producto se marca con la
  propiedad `producto`, no con el nombre del repositorio.
- **No se renombran repos para agruparlos.** `lavos` (docs) y
  `lavos-platform` (código) se quedan como están: renombrar rompe remotos,
  enlaces y documentación.
- **Topics:** además de las propiedades, cada repo lleva topics de producto y
  stack (`lavos`, `otazu`, `go`, `react`…). Las propiedades mandan; los topics
  son para descubrimiento.
- **Producto nuevo:** se añade a la tabla, se crea el proyecto en Linear y se
  asigna `producto` a sus repos. No se crea un GitHub Project por producto: el
  tablero de ejecución es Linear.

## Consultar por API

```bash
# Repos de un producto
gh api orgs/Otazu-DTO/properties/values \
  --jq '.[] | select(any(.properties[]; .property_name=="producto" and .value=="lavos")) | .repository_name'

# Propiedades de un repo
gh api repos/Otazu-DTO/lavos-platform/properties/values
```
