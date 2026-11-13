---
title: "Ejercicio 12 - Publica el sitio con GitHub Pages"
description: "Usa GitHub Copilot app para configurar un flujo de trabajo de Pages, revisar su solicitud de cambios y comprobar que Space Quiz está disponible."
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

Publica Space Quiz para que cualquiera pueda acceder. Copilot puede preparar el flujo de trabajo y guiar la implementación, pero tú debes revisar los cambios y confirmar que el sitio está disponible.

En este ejercicio:

- pedirás a Copilot que configure la implementación en GitHub Pages.
- revisarás el flujo de trabajo y la solicitud de cambios antes de combinarla.
- seguirás la implementación y comprobarás el sitio publicado.

## Situación

Space Quiz ya está en un repositorio de GitHub, pero todavía hace falta una forma sencilla de probarlo. Publicar el sitio de un solo archivo con GitHub Pages lo hace accesible mediante una URL pública, sin añadir un servidor ni una dependencia de ejecución.

## Pide a Copilot que publique el sitio

En la sesión de Copilot app para `space-quiz`, envía esta solicitud:

```plaintext
Enable GitHub Pages for this repository. Create a GitHub Actions workflow that builds the website if needed and deploys it to GitHub Pages. Add a README describing the app and how to run it locally if one does not already exist. Create a pull request with these changes and merge it after required checks pass. Monitor the deployment until it succeeds, then report the final URL of the live website. If you lack permission to enable Pages or merge, tell me exactly what I need to approve or do; do not report success until the site is live.
```

![Diagrama de tres etapas: una solicitud de cambios de space-quiz combinada; una ejecución correcta de Deploy website en GitHub Actions con los pasos Build website, Upload artifact y Deploy to Pages; y Space Quiz publicado en yourname.github.io/space-quiz/.](../../../_images/first-steps-app-pages-deploy.svg)

> [!WARNING]
> Esta solicitud pide al agente que cree y combine una solicitud de cambios y modifique la configuración de Pages del repositorio. Revisa las diferencias, los permisos de implementación y cualquier solicitud de aprobación de GitHub antes de continuar.

## Revisa el flujo de trabajo y comprueba la implementación

1. Confirma que el archivo README solo se añade si el repositorio aún no tiene uno.
2. Revisa los cambios de la solicitud, incluidos los pasos de compilación e implementación del flujo de trabajo.
3. Combina los cambios solo después de que se superen las comprobaciones obligatorias.
4. Sigue la ejecución de implementación de GitHub Actions hasta que se complete correctamente.
5. Abre la URL indicada y confirma que Space Quiz se carga.

Si el agente no puede habilitar Pages o combinar la solicitud de cambios, sigue las instrucciones específicas que te proporcione. No des la tarea por terminada hasta que la implementación se complete y el sitio publicado se cargue.

## Resumen y próximos pasos

Space Quiz ya está disponible como sitio web y has comprobado la implementación en lugar de confiar solo en el informe del agente. Continúa con el [ejercicio 13: Repaso y próximos pasos][next-lesson].

[next-lesson]: ../13-review/
