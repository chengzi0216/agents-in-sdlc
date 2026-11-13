---
slug: es-es/real-world-development/cli
title: "GitHub Copilot CLI"
description: "Crea, verifica y entrega dos cambios en Tailspin Toys mientras aprendes los modos de Copilot CLI, sus personalizaciones, las herramientas MCP y la automatización de solicitudes de cambios."
authors:
  - geektrainer
lastUpdated: 2026-09-18
---

**[GitHub Copilot CLI][about-copilot-cli]** incorpora GitHub Copilot al terminal como asistente de programación agéntico. Explora bases de código, genera código, ejecuta comandos y se conecta a herramientas externas desde la línea de comandos, para que puedas mantener el flujo sin cambiar a un editor gráfico.

El taller sigue un flujo de trabajo continuo de Tailspin Toys:

1. Prepara el proyecto en GitHub Codespaces, instala Copilot CLI y familiarízate con el entorno.
2. Añade valoraciones con estrellas, revisa el resultado en el navegador y combina manualmente tu primera solicitud de cambios (PR).
3. Empieza por la incidencia de filtrado, define el enfoque en el modo Plan, implementa en el modo Autopilot y revisa en el modo Interactive.
4. Actualiza las instrucciones del repositorio y aplícalas al trabajo de filtrado.
5. Personaliza la habilidad existente `quality-checks` y úsala para ejecutar las comprobaciones del proyecto.
6. Añade el servidor Model Context Protocol (MCP) de Playwright y úsalo para explorar el filtrado en un navegador.
7. Crea un agente personalizado de control de calidad (QA) y úsalo para revisar requisitos, cobertura y pruebas.
8. Revisa todo el cambio de filtrado y usa Agent Merge para la PR.
9. Explora comandos de barra útiles para el contexto, los modelos, el uso compartido y la delegación opcional en cloud.

Para centrar el taller, crearás dos PR: primero las valoraciones con estrellas y después el filtrado junto con las actualizaciones de instrucciones y habilidades, el perfil de QA y las pruebas. El trabajo de filtrado y calidad comparte una conversación y una rama para que puedas aprovechar lo que has hecho mientras exploras cada herramienta.

## Ejercicios

| Ejercicio | Tema | Descripción |
| ------ | ----------- | ----------- |
| [0. Requisitos previos][ex0] | Configuración | Crea el repositorio y el Codespace |
| [1. Instala Copilot CLI][ex1] | Instalación | Instala y autentica Copilot CLI, y familiarízate con el entorno |
| [2. Añade valoraciones con estrellas][ex2] | Primer cambio | Muestra las valoraciones existentes y el estado sin valoración; combina tu primer PR |
| [3. Modos de agente: Plan y Autopilot][ex3] | Modos de agente | Planifica la funcionalidad desde su incidencia, impleméntala con Autopilot y revísala con Interactive |
| [4. Guía a Copilot con instrucciones personalizadas][ex4] | Contexto | Revisa y actualiza las instrucciones, y aplícalas al filtrado |
| [5. Personaliza una habilidad de comprobaciones de calidad][ex5] | Comprobaciones repetibles | Revisa la habilidad existente, cambia el formato del informe y ejecútala |
| [6. Valida la funcionalidad con Playwright MCP][ex6] | Observación en navegador | Configura MCP en la CLI e inspecciona el comportamiento del filtrado |
| [7. Crea y usa un agente de QA][ex7] | Requisitos y cobertura | Crea y selecciona un perfil especializado y reúne las pruebas finales |
| [8. Crea y combina la PR de la funcionalidad][ex8] | Revisión y combinación | Revisa todo el cambio, crea la PR y usa Agent Merge |
| [9. Comandos de barra en GitHub Copilot CLI][ex9] | Funciones de CLI | Explora el contexto, los modelos, el uso compartido y la delegación opcional |
| [10. Repaso y próximos pasos][ex10] | Resumen | Repasa el flujo de trabajo, las personalizaciones reutilizables y otros recursos |
| [Opcional: incorpora Foundry][foundry] | Agentes hospedados | Prepara un modelo, implementa un agente fundamentado en un catálogo y conéctalo al sitio web |

## Requisitos previos

Antes de asistir a este taller, asegúrate de tener:

- [ ] Una cuenta de GitHub con un plan activo **Copilot Student, Pro, Pro+, Business o Enterprise**
- [ ] Permiso para crear un repositorio y un Codespace
- [ ] Conocimientos básicos del terminal o de la línea de comandos

> [!TIP]
> ¿No tienes un plan de pago? Los estudiantes verificados pueden obtener GitHub Copilot gratis a través de [GitHub Education][student-plan]. El plan **Copilot Student** incluye las funciones de agente, MCP, revisión de código y Copilot CLI que se usan en este taller.

> [!NOTE]
> Si usas Copilot Business o Copilot Enterprise, asegúrate de que tu administrador haya habilitado Copilot CLI.

## Primeros pasos

**[Empieza con los requisitos previos →][ex0]**

[about-copilot-cli]: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
[student-plan]: https://github.com/education/students
[ex0]: 0-prerequisites/
[ex1]: 1-install-copilot-cli/
[ex2]: 2-add-star-rating/
[ex3]: 3-agent-modes/
[ex4]: 4-custom-instructions/
[ex5]: 5-agent-skills/
[ex6]: 6-mcp-playwright/
[ex7]: 7-qa-agent/
[ex8]: 8-create-pull-request/
[ex9]: 9-cli-power-tools/
[ex10]: 10-review/
[foundry]: 8-foundry-agent/
