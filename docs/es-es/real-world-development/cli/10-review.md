---
title: "Ejercicio 10 - Repaso y próximos pasos"
description: "Repasa el flujo de trabajo de Copilot CLI, las dos solicitudes de cambios, las personalizaciones reutilizables y otros recursos."
authors:
  - geektrainer
lastUpdated: 2026-09-29
---

Has utilizado GitHub Copilot CLI en un flujo de trabajo continuo de Tailspin Toys. Has:

- preparado un Codespace, instalado Copilot CLI, explorado el proyecto y encontrado la incidencia de filtrado ya creada.
- añadido valoraciones con estrellas, revisado el resultado en un navegador reenviado y combinado manualmente tu primera solicitud de cambios (PR).
- partido de la incidencia de filtrado, definido el enfoque en el modo Plan, implementado la funcionalidad en el modo Autopilot y revisado el resultado en el modo Interactive.
- guiado al agente con instrucciones personalizadas y, después, personalizado la habilidad existente `quality-checks` para ejecutar pruebas unitarias, lint y comprobaciones de tipos.
- añadido el servidor Model Context Protocol (MCP) de Playwright y utilizado para explorar el filtrado en un navegador real.
- creado y seleccionado un agente personalizado de control de calidad (QA) para evaluar los requisitos, la cobertura, los resultados de la habilidad y las pruebas del navegador.
- revisado todo el cambio de filtrado y autorizado Agent Merge para la PR de filtrado.
- explorado comandos de barra para gestionar el contexto, los modelos y el uso compartido, además de la delegación opcional en cloud.

## Lo que has entregado

El taller incluye dos hitos de PR, cada uno en su propia rama basada en `main` actualizado:

1. **Valoraciones con estrellas:** muestra el valor existente de `starRating` y un estado explícito sin valoración en las tarjetas de juegos.
2. **Filtrado y flujo de calidad:** implementa el filtrado, actualiza las instrucciones y las aplica a la funcionalidad, personaliza el informe de `quality-checks`, crea un perfil de QA e incluye las pruebas correspondientes.

Desde la planificación del filtrado hasta la apertura de su PR, has usado la misma conversación y rama. Hemos combinado ese trabajo en una PR para simplificar el taller.

## Diferentes formas de verificar

Has comprobado el código de varias maneras: con pruebas automatizadas, inspeccionándolo en el navegador y usando MCP para que Copilot lo explore en un navegador. La habilidad `quality-checks` ejecutó las pruebas unitarias, lint y comprobaciones de tipos, y comunicó los resultados con el nuevo formato. Antes de la PR, QA reunió esos resultados con una revisión de los requisitos y la cobertura de las pruebas.

Las pruebas nuevas deben cubrir carencias reales; una ejecución de QA puede ser correcta aunque no requiera añadir pruebas. La falta de herramientas, las comprobaciones omitidas y los errores son bloqueos visibles, no resultados satisfactorios. Revisa el código y las pruebas antes de autorizar la combinación, y vuelve a recopilar las pruebas afectadas después de hacer cambios.

## Buenas prácticas

El contexto y las herramientas que proporcionas a Copilot dan forma a su trabajo. En este taller, has actualizado instrucciones, personalizado una habilidad, creado un perfil de QA y configurado un servidor MCP. Reutiliza estas personalizaciones entre sesiones y ajústalas a las necesidades del equipo. Las instrucciones establecen estándares, las habilidades describen tareas repetibles, los agentes personalizados definen funciones especializadas y los servidores MCP conectan herramientas externas. Revisa los cambios reales y los resultados de las herramientas, no solo el resumen del agente.

Adapta el **modo y el modelo** a la tarea. Usa **Plan** para analizar un enfoque antes de construir, **Interactive** para seguir de cerca los cambios concretos y **Autopilot** solo para tareas aisladas y bien delimitadas. Elige un modelo más rápido para ediciones rutinarias y otro más capaz, con mayor esfuerzo de razonamiento, para trabajos complejos.

El contexto sigue siendo tan importante como la infraestructura. Describir claramente *qué* quieres crear, *por qué* y *cómo* influye de forma significativa en el resultado. Los chats rápidos son útiles para concretar una idea antes de iniciar una sesión completa.

## Más opciones para explorar

Ya has cubierto el flujo de trabajo principal. Estas son algunas funciones más que puedes probar:

- [**Automatizaciones**][using-automations] para tareas periódicas o puntuales, como resumir el trabajo reciente. Revisa la programación, los permisos y el alcance antes de adoptar una; crear una automatización es un paso posterior, no forma parte de este taller.
- **Rubber duck** para analizar un problema y obtener comentarios útiles antes de empezar a implementarlo.
- [`/chronicle`][chronicle] para generar una narración de lo ocurrido en una sesión.
- [Trae tu propia clave (BYOK)][byok] para usar modelos de tu proveedor, incluidos modelos locales mediante Ollama, Foundry Local o LM Studio.
- [Enlaces profundos][deep-links] para abrir la aplicación directamente en un repositorio, una sesión o un mensaje.

## Próximos pasos

La mejor forma de mejorar con cualquier herramienta es seguir utilizándola. Úsala para código de producción, proyectos personales o esa pequeña aplicación que tienes en mente desde hace años y aún no has creado. Comparte lo que aprendas con el equipo y aprende también de sus experiencias. Y, como siempre, consulta la documentación.

Si quieres explorar más el ecosistema de GitHub Copilot, consulta el [recorrido de VS Code][vscode-harness], el [recorrido de Copilot CLI][cli-harness] o el [recorrido de Cloud agent][cloud-harness].

## Recursos

- [Acerca de GitHub Copilot app][about-copilot-app]
- [Primeros pasos con GitHub Copilot app][getting-started]
- [Personalización de GitHub Copilot app][customize]
- [Uso de automatizaciones][using-automations]
- [Uso de extensiones de canvas][canvas-docs]

[vscode-harness]: ../../vscode/
[cli-harness]: ../../cli/
[cloud-harness]: ../../cloud/
[about-copilot-app]: https://docs.github.com/copilot/concepts/agents/github-copilot-app
[getting-started]: https://docs.github.com/copilot/how-tos/github-copilot-app/getting-started
[customize]: https://docs.github.com/copilot/how-tos/github-copilot-app/customize-github-copilot-app
[using-automations]: https://docs.github.com/copilot/how-tos/github-copilot-app/using-automations
[canvas-docs]: https://docs.github.com/copilot/how-tos/github-copilot-app/working-with-canvas-extensions
[chronicle]: https://docs.github.com/copilot/how-tos/copilot-cli/use-copilot-cli/chronicle
[byok]: https://docs.github.com/copilot/how-tos/github-copilot-app/use-byok-models
[deep-links]: https://docs.github.com/copilot/how-tos/github-copilot-app/open-with-deep-links
