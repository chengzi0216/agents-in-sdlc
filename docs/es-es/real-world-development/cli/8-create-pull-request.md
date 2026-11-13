---
title: "Ejercicio 8 - Crea y combina la PR de la funcionalidad"
description: "Revisa el filtrado, las instrucciones, la habilidad, el perfil de QA y las pruebas; después, crea una PR y usa Agent Merge."
authors:
  - geektrainer
lastUpdated: 2026-09-18
---

La implementación del filtrado, las actualizaciones de instrucciones y habilidades, el perfil de control de calidad (QA) y las pruebas están guardados en una sola rama. Ahora toca revisarlos en conjunto y abrir una solicitud de cambios. Combinaste personalmente la PR de las valoraciones con estrellas; esta vez dejarás que **Agent Merge** gestione el proceso.

> [!NOTE]
> En condiciones normales, dividiríamos la funcionalidad, las actualizaciones de instrucciones y habilidades, y el agente de QA en varias PR. Para simplificar el taller, has mantenido todo el flujo de filtrado y calidad en una conversación y una rama, y lo incluirás en esta PR.

En este ejercicio:

- aprenderás qué es Agent Merge y cómo automatiza el ciclo de vida de una PR.
- inspeccionarás el cambio completo de la funcionalidad y las pruebas de verificación.
- crearás la PR de filtrado.
- habilitarás Agent Merge solo después de la revisión y confirmarás que la PR se ha combinado.

## Situación

Durante el flujo de filtrado, has usado Copilot para planificar, implementar y verificar una funcionalidad. Tailspin Toys quiere ahora automatizar el resto del trabajo de la PR, pero mantener bajo el control del desarrollador la autorización para combinarla.

## Presentación de Agent Merge

**Agent Merge** automatiza el trabajo restante para incorporar una solicitud de cambios. Cuando lo habilitas, Copilot resuelve los bloqueos de la PR: corrige las comprobaciones de integración continua (CI) que fallan, responde a comentarios de revisión y vuelve a aplicar la base cuando hace falta. Después habilita la combinación automática de GitHub si el repositorio lo permite.

Hasta ahora has seleccionado **Merge pull request** personalmente. Agent Merge puede hacerse cargo de esa responsabilidad. Revisa el trabajo y confirma que está listo antes de habilitarlo.

## Usa Agent Merge para gestionar la PR

Ya tienes todo el código. Revísalo, crea la PR y deja que Agent Merge gestione el resto.

1. Vuelve a tu Codespace.
2. Escribe `/agent` para abrir el cuadro de diálogo de agentes.
3. Selecciona **Default** en la lista y pulsa <kbd>Enter</kbd>.
4. Ejecuta `/pr create` para crear una PR.
5. Activa Agent Merge con `/pr agentmerge`.
6. Copilot supervisará la integración continua de la PR. Cuando todo se complete correctamente, la combinará.
7. Confirma que Copilot muestra un mensaje parecido a "PR #14 was squash-merged successfully".

> [!IMPORTANT]
> Agent Merge no omite las aprobaciones obligatorias, la protección de ramas, las colas de combinación, la configuración del repositorio ni los permisos que falten. Si se bloquea, revisa el motivo indicado y completa manualmente la combinación revisada cuando el repositorio lo permita.

## Resumen y próximos pasos

Has automatizado varias partes del desarrollo: generar código, probarlo y validarlo, y ahora gestionar la solicitud de cambios. Has:

- aprendido qué es Agent Merge y cómo automatiza el ciclo de vida de una PR.
- inspeccionado el cambio completo de la funcionalidad y las pruebas de verificación.
- creado la PR de filtrado.
- habilitado Agent Merge solo después de la revisión y confirmado que la PR se ha combinado.

A continuación, [explorarás comandos de barra útiles de Copilot CLI][next-lesson] para gestionar el contexto, los modelos, el uso compartido y la delegación opcional en cloud.

## Recursos

- [Gestión de solicitudes de cambios con Copilot CLI][manage-prs]
- [Referencia de comandos de Copilot CLI][cli-reference]

[previous-lesson]: ../7-qa-agent/
[next-lesson]: ../9-cli-power-tools/
[manage-prs]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/manage-pull-requests
[cli-reference]: https://docs.github.com/copilot/reference/copilot-cli-reference/cli-command-reference
