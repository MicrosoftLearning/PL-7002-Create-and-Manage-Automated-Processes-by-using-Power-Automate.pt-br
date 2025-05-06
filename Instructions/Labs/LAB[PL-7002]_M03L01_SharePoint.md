---
lab:
  title: 'Laboratório 3: SharePoint'
  module: 'Module 3: Build approval flows with Power Automate'
---

# Laboratório de prática 3: SharePoint

Neste laboratório, você vai criar um site e uma lista do SharePoint.

## O que você aprenderá

- Como criar uma lista do SharePoint
- Como carregar dados

## Macroetapas do laboratório

- Criar uma lista do SharePoint para Oportunidades
  
## Pré-requisitos

- Precisa ter concluído o **Laboratório 0: Validar o ambiente de laboratório**

## Etapas detalhadas

## Exercício 1 – Criar uma lista do SharePoint

### Tarefa 1.1 Criar um site do SharePoint

1. No portal do criador do Power Apps, `https://make.powerapps.com`

1. Selecione o **Inicializador de aplicativos** no canto superior esquerdo da janela do navegador e escolha **SharePoint**.

1. Se a caixa de diálogo pop-up **Boas-vindas à Página Inicial do SharePoint** for exibida, clique no **X** para fechá-la.

1. No SharePoint, selecione **+ Criar site**.

1. Escolha **Site de equipe**, selecione o modelo **Equipe padrão** e escolha **Usar modelo**.

1. Insira `Power Automate` em **Nome do site** e selecione **Avançar**.

1. Selecione **Criar site**.

1. Selecione **Concluir**.

1. Se a caixa de diálogo pop-up **Comece a projetar seu site** for exibida, feche-a.

### Tarefa 1.2 Criar uma lista do SharePoint

1. No site do SharePoint, selecione **+ Novo** e escolha **Lista**.

    ![Captura de tela da nova lista do SharePoint.](../media/new-sharepoint-list.png)

1. Selecione **Lista** em **Criar do zero**.

1. Insira `Tasks` em **Nome** e escolha **Criar**.

1. Selecione **+ Adicionar coluna**, escolha **Várias linhas de texto** e selecione **Avançar**.

1. No painel **Criar uma coluna**, insira ou selecione os seguintes valores:

   1. Nome: `Description`
   1. Tipo: **Várias linhas de texto**

1. Selecione **Salvar**.

1. Selecione **+Adicionar coluna**, escolha **Texto** e selecione **Avançar**.

1. No painel **Criar uma coluna**, insira ou selecione os seguintes valores:

   1. Nome: `Owner Name`
   1. Tipo: **Linha única de texto**

1. Selecione **Salvar**.

1. Selecione **+ Adicionar coluna**, escolha **Data e hora** e selecione **Avançar**.

1. No painel **Criar uma coluna**, insira ou selecione os seguintes valores:

   1. Nome: `Deadline`
   1. Tipo: **Data e hora**

1. Selecione **Salvar**.

1. Selecione **+ Adicionar coluna**, **Escolha** e **Avançar**.

1. No painel **Criar uma coluna**, insira ou selecione os seguintes valores:

   1. Nome: `Approval Status`
   1. Tipo: **Escolha**
   1. Escolha 1=`New`
   1. Escolha 2=`Approved`
   1. Escolha 3=`Declined`

1. Selecione **Novo** em **Valor padrão**

    ![Captura de tela da nova lista do SharePoint.](../media/add-choice-column.png)

1. Selecione **Salvar**.

1. Copie a primeira parte da URL do site do SharePoint, por exemplo, `https://m365x99999999.sharepoint.com/sites/PowerAutomate/`


## Exercício 2: Adicionar uma lista de dados do SharePoint

### Tarefa 2.1: Adicionar dados

1. Navegue até o site do SharePoint e selecione a lista **Tarefas**.

    ![Captura de tela da lista Tarefas do SharePoint.](../media/tasks-sharepoint-list.png)

1. Selecione **+ Adicionar novo item**, insira os seguintes dados e escolha **Salvar**:

   1. Título=`Contact Jon`
   1. Descrição=`Call or email`
   1. Nome do Proprietário=`MOD Administrator`
   1. Data Limite=**Ontem**
   1. Status de Aprovação=**Recusado**

1. Selecione **+ Adicionar novo item**, insira os seguintes dados e escolha **Salvar**:

   1. Título=`Create Quote`
   1. Descrição=`No discount`
   1. Nome do Proprietário=`MOD Administrator`
   1. Data Limite=**Hoje**
   1. Status de Aprovação=**Aprovado**

1. Selecione **+ Adicionar novo item**, insira os seguintes dados e escolha **Salvar**:

   1. Título=`Visit Jim`
   1. Descrição=`First visit`
   1. Nome do Proprietário=`MOD Administrator`
   1. Data Limite=**Amanhã**
   1. Status de Aprovação=**Novo**

    ![Captura de tela dos dados das Tarefas do SharePoint.](../media/tasks-data.png)

