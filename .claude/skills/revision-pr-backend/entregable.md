# Entregable · Sesión 3 — Copilotos IA

- **Usuario: Eliana Rodriguez**
- **Fecha de entrega: 22 Jun 2026**
- **Repo auditado en la Parte A: proyecto backend NestJS, 3 años**

---

## 1. Hallazgos de la auditoría (Parte A)

> 3-5 cosas que el agente **no pudo inferir** del código y que tendrías que decirle explícitamente.
> Redáctalas para que otra persona las entienda sin contexto adicional. **Sin código propietario ni secretos.**

1. Claude vio que el proyecto tiene Jest configurado, pero asumió que existía una estrategia de pruebas cuando en realidad la cobertura actual es muy limitada.
2. Claude detectó las integraciones externas del proyecto, pero no tenía forma de saber cuáles usamos realmente en desarrollo y cuáles solemos simular con mocks.
3. Claude entendió cómo está organizado el repositorio, pero no pudo inferir las reglas no escritas que sigue el equipo para agregar nuevas funcionalidades.

---

## 2. SKILL.md de la skill creada (Parte B)

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
---

## 3. Diario de decisiones

*Skill creada: revision-pr-backend — Skill para revisar cambios backend en proyectos TypeScript/NestJS antes de subir o aprobar un Pull Request.*

*Decisiones de diseño tomadas:*
- Decidí hacer una skill de revisión de Pull Request porque es algo que se acerca bastante a mi día a día como desarrolladora backend.
- Decidí enfocarla en TypeScript, NestJS, DTOs, services, queries e integraciones externas, porque son partes comunes en los proyectos donde trabajo.
- Decidí que la respuesta tuviera una estructura fija con resumen, hallazgos, pruebas sugeridas y recomendación final, para que el resultado sea fácil de leer.
- Decidí incluir límites claros, como no modificar archivos si no se pide, porque quería que la skill sirviera principalmente para análisis.

*Qué me resultó fácil:*
- Elegir el tipo de skill, porque revisar código es una tarea común en mi trabajo.
- Pensar en puntos que normalmente revisaría en un Pull Request.

*Qué me resultó ambiguo o difícil de decidir:*
- Me costó decidir qué tan detallado debía ser el description para que Claude active la skill cuando corresponde.
- Dudé si incluir ejemplos completos o dejar la skill más corta y general.
- Dudé si alguna parte de la skill debia ser estrictamente en ingles.

*Tiempo real invertido:*
- Total aproximado: 1 hr y media.

*Qué probarías si tuvieras más tiempo:*
- Probar la skill con distintos tipos de cambios: un cambio de controller, uno de service y uno de query.

*¿Usaste IA para crear la skill?* (qué partes generaste con IA y qué partes decidiste tú)
- Si, por ser un nuevo tema para mi, use la IA para ayudarme a manejar su estructura y mejoras en redaccion.
- Lo que hice yo fue manejar los limites, el formato de lo que debe hacer la skill y lo que queria observar al ejecutar la skill

### Resultado de la prueba (Paso 8)

- ¿Se activó cuando lo esperabas?
Probé la skill desde Claude Code usando el prompt: “Usa la skill revision-pr-backend para revisar los cambios actuales del repositorio”, la skill se activó cuando la mencioné explícitamente por nombre.
- ¿El resultado fue el que querías?
El resultado fue útil porque respondió con una estructura de revisión: resumen del cambio, hallazgos importantes (criticos, altos, medios, bajos) y recomendación. Falto que en la recomendacion sea un poco mas detallista.

Para ser mi primera skill, me gusto mucho el resultado, se puede mejorar mas en el detalle y especificacion de lo que se debe cambiar para ayudar mas en un futuro, pero me sorprendio gratamente el resultado.
