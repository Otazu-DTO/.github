## Resumen

<!-- Qué hace este cambio y por qué. -->

## Ticket / historia

- Ticket: <!-- enlace a Linear, p. ej. OTA-123 -->
- Historia: <!-- US-000 o enlace -->
- Riesgo relacionado: <!-- ID, si aplica -->

## Tipo de cambio

- [ ] Nueva funcionalidad (`feat`)
- [ ] Corrección (`fix`)
- [ ] Refactor (`refactor`)
- [ ] Documentación (`docs`)
- [ ] Mantenimiento / dependencias (`chore`)
- [ ] Cambio con implicación de seguridad

## Cómo se ha probado

- [ ] Tests unitarios
- [ ] Tests de integración
- [ ] Tests E2E (si aplica)
- [ ] Prueba manual (describe el escenario)
- [ ] DAST / pruebas de seguridad

<!-- Describe el escenario de prueba y el resultado. -->

## Checklist de seguridad

- [ ] Entradas validadas en el servidor.
- [ ] Autorización comprobada por endpoint y por recurso.
- [ ] Sin secretos ni credenciales en el código ni en el historial.
- [ ] Sin datos sensibles en logs.
- [ ] Manejo de errores que no filtra información interna.
- [ ] Dependencias nuevas revisadas (SCA) y justificadas.
- [ ] Consultas parametrizadas / construcciones seguras.
- [ ] Cifrado en tránsito (y en reposo si aplica).

## Checklist general

- [ ] Criterios de aceptación del ticket cumplidos.
- [ ] Cobertura de tests suficiente.
- [ ] Documentación actualizada (README, ADR, guía).
- [ ] Sin cambios innecesarios ni código muerto.
- [ ] Migraciones/backfill incluidos y reversibles, si aplica.

## Impacto

- **Despliegue**: <!-- requiere migración / feature flag / ventana -->
- **Rollback**: <!-- cómo revertir -->
- **Otros equipos / servicios afectados**: <!-- ... -->

## Capturas / evidencia

<!-- Si aplica. -->
