---
title: "Lição 10 - Recapitulação e próximos passos"
description: "Recapitule o fluxo de trabalho do Copilot CLI, dois pull requests, personalizações reutilizáveis e outros recursos."
authors:
  - geektrainer
lastUpdated: 2026-09-29
---

Você usou o GitHub Copilot CLI em um fluxo de trabalho contínuo da Tailspin Toys. Você:

- preparou um Codespace, instalou o Copilot CLI, explorou o projeto e encontrou a issue de filtragem já criada.
- adicionou avaliações por estrelas, revisou o resultado em um navegador encaminhado e mesclou manualmente seu primeiro pull request (PR).
- começou pela issue de filtragem, definiu a abordagem no modo Plan, implementou no modo Autopilot e revisou no modo Interactive.
- orientou o agente com instruções personalizadas e, em seguida, personalizou a skill `quality-checks` existente para executar testes unitários, lint e verificações de tipos.
- adicionou o servidor Model Context Protocol (MCP) do Playwright e o usou para explorar a filtragem em um navegador real.
- criou e selecionou um agente personalizado de garantia de qualidade (QA) para avaliar requisitos, cobertura, resultados da skill e evidências do navegador.
- revisou toda a mudança de filtragem e autorizou o Agent Merge para o PR de filtragem.
- explorou comandos de barra para contexto, modelos, compartilhamento e delegação opcional para a nuvem.

## O que você entregou

O workshop tem dois marcos de PR, cada um em sua própria branch criada a partir da `main` atualizada:

1. **Avaliações por estrelas:** exibe o valor existente de `starRating` e um estado explícito sem avaliação nos cartões de jogos.
2. **Filtragem e fluxo de qualidade:** implementa a filtragem, atualiza as instruções e as aplica à funcionalidade, personaliza o relatório de `quality-checks`, cria um perfil de QA e inclui os testes associados.

Da etapa de planejamento da filtragem até a abertura do PR, você usou a mesma conversa e branch. Reunimos esse trabalho em um único PR para simplificar o workshop.

## Diferentes tipos de verificação

Você verificou o código de várias maneiras: testes automatizados, inspeção própria no navegador e exploração do navegador pelo Copilot via MCP. A skill `quality-checks` executou testes unitários, lint e verificações de tipos, e apresentou os resultados no novo formato. Antes do PR, o QA reuniu esses resultados com a revisão dos requisitos e da cobertura de testes.

Os testes adicionados devem preencher lacunas reais; uma execução de QA pode estar correta mesmo sem exigir novos testes. Ferramentas ausentes, verificações ignoradas e falhas são bloqueios visíveis, não aprovações. Revise o código e as evidências antes de autorizar a mesclagem e atualize as evidências afetadas depois de mudanças.

## Boas práticas

O contexto e as ferramentas que você fornece ao Copilot influenciam o trabalho. Neste workshop, você atualizou instruções, personalizou uma skill, criou um perfil de QA e configurou um servidor MCP. Reutilize essas personalizações entre sessões e ajuste-as às necessidades da equipe. Instruções definem padrões, skills descrevem tarefas repetíveis, agentes personalizados definem funções especializadas e servidores MCP conectam ferramentas externas. Revise as mudanças reais e os resultados das ferramentas, não apenas o resumo do agente.

Escolha o **modo e o modelo** de acordo com a tarefa. Use **Plan** para avaliar uma abordagem antes de começar a implementação, **Interactive** para acompanhar mudanças específicas e **Autopilot** somente em tarefas isoladas e bem delimitadas. Escolha um modelo mais rápido para edições rotineiras e outro mais capaz, com maior esforço de raciocínio, para tarefas complexas.

O contexto continua tão importante quanto a infraestrutura. Descrever com clareza *o que* você quer criar, *por que* e *como* influencia significativamente o resultado. Chats rápidos são úteis para definir melhor uma ideia antes de iniciar uma sessão completa.

## Mais recursos para explorar

Você já percorreu o fluxo de trabalho principal. Confira também estes recursos:

- [**Automações**][using-automations] para tarefas recorrentes ou sob demanda, como resumir o trabalho recente. Revise o agendamento, as permissões e o escopo antes de adotar uma automação. Criá-la é um próximo passo, não faz parte deste workshop.
- **Rubber duck** para conversar sobre um problema e obter feedback útil antes de começar.
- [`/chronicle`][chronicle] para gerar uma narrativa do que aconteceu em uma sessão.
- [Traga sua própria chave (BYOK)][byok] para usar modelos do seu provedor, incluindo modelos locais via Ollama, Foundry Local ou LM Studio.
- [Links diretos][deep-links] para abrir o aplicativo diretamente em um repositório, sessão ou prompt.

## Próximos passos

A melhor maneira de melhorar com qualquer ferramenta é continuar usando-a. Use-a em código de produção, projetos pessoais ou naquele pequeno aplicativo que você imagina há anos, mas ainda não construiu. Compartilhe o que aprendeu com a equipe e aprenda com as experiências dela. E, como sempre, consulte a documentação.

Para explorar mais o ecossistema do GitHub Copilot, confira o [workshop do VS Code][vscode-harness], o [workshop do Copilot CLI][cli-harness] ou o [workshop do Cloud agent][cloud-harness].

## Recursos

- [Sobre o GitHub Copilot app][about-copilot-app]
- [Primeiros passos com o GitHub Copilot app][getting-started]
- [Personalizar o GitHub Copilot app][customize]
- [Usar automações][using-automations]
- [Trabalhar com extensões de canvas][canvas-docs]

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
