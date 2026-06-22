---
name: revision-pr-backend
description: Usa esta skill cuando necesites revisar cambios de código o Pull Requests en proyectos backend con TypeScript, NestJS, APIs, DTOs, servicios, consultas a base de datos o integraciones externas.
---

# Backend PR Review Skill

Esta skill ayuda a revisar cambios de código backend como si fueran parte de un Pull Request.

## Objetivo

Revisar cambios en proyectos backend TypeScript/NestJS, detectando posibles errores, riesgos o mejoras antes de aprobar o subir un Pull Request.

## Qué debe revisar

Cuando se use esta skill, revisa:

1. Si el cambio se entiende claramente.
2. Si la lógica implementada parece correcta.
3. Si los DTOs, services, controllers y modules están bien ubicados.
4. Si hay validaciones necesarias que faltan.
5. Si las queries, inserts, updates o upserts pueden generar errores.
6. Si las integraciones externas están bien manejadas.
7. Si hay manejo adecuado de errores.
8. Si los logs son útiles para monitoreo o debugging.
9. Si se deberían agregar o actualizar tests.
10. Si existe algún riesgo de seguridad, como datos sensibles, URLs mal construidas o falta de validación.

## Formato de respuesta

Responder siempre con esta estructura:

### Resumen del cambio
Explicar brevemente qué parece hacer el cambio.

### Hallazgos
Separar los hallazgos por importancia:

- Crítico
- Alto
- Medio
- Bajo

Para cada hallazgo indicar:

- Qué problema hay
- Por qué podría afectar
- Cómo se podría corregir

### Recomendación
Indicar una de estas opciones:

- Aprobar
- Aprobar con comentarios
- Solicitar cambios

## Límites

No modificar archivos si no se solicita explícitamente.

No inventar reglas internas del proyecto.

Si algo depende de una convención del equipo, indicarlo como duda o supuesto.

No exponer secretos, credenciales ni información sensible.
