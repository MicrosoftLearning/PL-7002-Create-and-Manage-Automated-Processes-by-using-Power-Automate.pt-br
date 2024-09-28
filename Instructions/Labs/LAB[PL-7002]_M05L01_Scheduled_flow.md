---
lab:
  title: 'Laboratório 6: Fluxo agendado'
  module: 'Module 5: Power Automate’s deep integration across multiple data sources'
---

# Laboratório de prática 6: Fluxo agendado

Neste laboratório, você vai criar um fluxo agendado.

## O que você aprenderá

- Como criar um fluxo agendado do Power Automate e processar uma lista de itens do SharePoint.

## Macroetapas do laboratório

- Criar um fluxo agendado
- Consultar uma lista do SharePoint
- Usar operações de dados
- Testar o fluxo
  
## Pré-requisitos

- Precisa ter concluído o **Laboratório 3: SharePoint**

## Etapas detalhadas

## Exercício 1: Criar fluxo agendado

### Tarefa 1.1: Criar o gatilho

1. Navegue até o portal do Power Automate `https://make.powerautomate.com`.

1. Verifique se você está no ambiente **Dev One**.

1. Selecione a guia **+ Criar** no menu de navegação à esquerda.

1. Selecione **Fluxo da nuvem agendado**.

1. Insira `Daily New Tasks` em **Nome do fluxo**.

1. Defina **Repetir a cada** como **1****dia**.

    ![Captura de tela do build de um fluxo agendado.](../media/build-scheduled-flow.png)

1. Selecione **Criar**.


### Tarefa 1.2: Configurar o gatilho

1. Escolha a etapa **Recorrência**.

1. Clique no nome da etapa **Recorrência** e insira `Daily`


### Tarefa 1.3: Consultar novas tarefas

1. Selecione o ícone **+** na etapa de gatilho e escolha **Adicionar uma ação**.

1. Insira `list items` na pesquisa.

1. Selecione **Obter itens** em **SharePoint**.

1. Clique no nome da etapa **Obter itens** e insira `New tasks`

1. Selecione o **site do SharePoint do Power Automate**.

1. Escolha a lista **Tarefas**.

1. Em **Parâmetros avançados**, escolha **Mostrar tudo**.

1. Escolha o campo **Filtrar Consulta** e insira `ApprovalStatus eq 'New'`

    ![Captura de tela da consulta de itens de lista.](../media/list-items.png)


### Tarefa 1.4: Selecionar colunas

1. Clique no ícone **+** na etapa **Novas tarefas** e escolha **Adicionar uma ação**.

1. Insira `Select` na pesquisa.

1. Selecione **Integrado** em **Runtime**.

1. Escolha **Selecionar** em **Operações de Dados**.

1. Selecione o campo **De** e escolha o ícone de Conteúdo dinâmico.

1. Escolha **corpo/valor** em **Novas tarefas**.

1. Clique no campo **Inserir chave** e insira `Task`

1. Selecione o campo **Inserir valor** e escolha o ícone de Conteúdo dinâmico.

1. Escolha **Título** em **Novas tarefas**.

1. Clique no campo **Inserir chave** e insira `Description`

1. Selecione o campo **Inserir valor** e escolha o ícone de Conteúdo dinâmico.

1. Escolha **Descrição** em **Novas tarefas**.

1. Clique no campo **Inserir chave** e insira `Due`

1. Selecione o campo **Inserir valor**, selecione o ícone de Conteúdo dinâmico e selecione **Ver Mais**.

1. Escolha **Data Limite** em **Novas tarefas**.

    ![Captura de tela da ação Selecionar.](../media/select-action.png)

1. Se o designer de fluxos adicionou automaticamente um ou mais loops "Para Cada", arraste a etapa “Seleção” para fora dos loops e remova o(s) loop(s).

    ![Captura de tela das etapas do fluxo sem loops.](../media/flow-without-loops.png)


### Tarefa 1.5: Criar tabela

1. Selecione o ícone **+** na etapa Selecionar e escolha **Adicionar uma ação**.

1. Insira `create html` na pesquisa.

1. Escolha **Criar tabela HTML** em **Operações de dados**.

1. Selecione o nome da etapa **Criar tabela HTML** e insira `Format as HTML table`

1. Selecione o campo **De** e escolha o ícone de Conteúdo dinâmico.

1. Escolha **Saída** em **Selecionar**.

    ![Captura de tela da ação Formatar tabela HTML.](../media/format-html-action.png)


### Tarefa 1.6: Enviar email

1. Clique no ícone **+** na etapa **Formatar como tabela HTML** e escolha **Adicionar uma ação**.

1. Insira `email` na pesquisa.

1. Selecione **Enviar um email (V2)** em **Office 365 Outlook**.

1. Clique no nome de etapa **Enviar um email (V2)** e insira `Notify by email`

1. Selecione o campo **Para** e escolha **Inserir valor personalizado**.

1. Insira sua ID de usuário do locatário em **Para**.

1. Clique no campo **Assunto** e insira `Daily Tasks`

1. Selecione o campo **Corpo** e escolha o ícone de Conteúdo dinâmico.

1. Selecione **Saída** em **Formatar como tabela HTML**.

1. Selecione **Salvar**.


## Exercício 2: Teste de fluxo agendado

### Tarefa 2.1: Executar o fluxo agendado manualmente

1. Escolha **Testar**

1. Selecione **Manualmente**.

1. Selecione **Testar**.

1. Selecione **Executar fluxo**.

1. Selecione **Concluído**.

1. No portal do Power Automate, selecione o **Inicializador de aplicativos** no canto superior esquerdo da janela do navegador e escolha **Outlook**.

    ![Captura de tela da ação Formatar tabela HTML.](../media/daily-tasks-email.png)

