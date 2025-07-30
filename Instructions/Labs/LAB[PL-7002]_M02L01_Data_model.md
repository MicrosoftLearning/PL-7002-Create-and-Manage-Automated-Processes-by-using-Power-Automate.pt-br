---
lab:
  title: 'Laboratório 2: Modelo de dados'
  module: 'Module 2: Get started with Microsoft Dataverse'
---

# Laboratório de prática 2 – Modelo de dados

Neste laboratório, você criará tabelas e colunas do Dataverse.

## O que você aprenderá

- Como criar tabelas e colunas no Microsoft Dataverse
- Como criar uma relação com uma coluna de pesquisa

## Macroetapas do laboratório

- Criar uma tabela personalizada
- Adicionar colunas à tabela
- Criar relação com o usando uma coluna de pesquisa
  
## Pré-requisitos

- Precisa ter concluído o **Laboratório 0: Validar o ambiente de laboratório**

## Etapas detalhadas

## Exercício 1 – Criar tabelas personalizadas

### Tarefa 1.1 – Criar a tabela Oportunidade

1. Navegue até o portal do Power Apps Maker `https://make.powerapps.com`

1. Verifique se você está no ambiente **Dev One**.

1. No painel de navegação esquerdo, selecione **Tabelas**.

1. Clique em **+ Nova tabela** e escolha **Tabela (propriedades avançadas)**.

    ![Captura de tela da criação de uma nova tabela no Dataverse.](../media/create-new-table-dataverse.png)

1. Para **Nome de exibição**, insira `Opportunity`.


### Tarefa 1.2 – Coluna primária

1. Selecione a guia **Coluna principal** ao lado da guia **Propriedades**.

    ![Captura de tela da coluna primária.](../media/primary-column.png)

1. Para **Nome de exibição**, insira `Opportunity Subject`.

1. Selecione **Salvar**.


### Tarefa 1.3 – Adicionar colunas

1. No painel **Colunas e dados de Oportunidade**, selecione **+** para adicionar uma nova coluna.

    ![Captura de tela do painel de dados.](../media/data-pane.png)

1. No painel **Nova coluna**, insira ou selecione os seguintes valores:

   1. Nome de exibição`Owner Name`
   1. Tipo de dados: **Linha única de texto**
   1. Obrigatório: **Empresa necessária**

    ![Captura de tela do painel nova coluna.](../media/new-column-pane.png)

1. Selecione **Salvar**.

1. No painel **Colunas e dados de Oportunidade**, selecione **+** para adicionar uma nova coluna.

1. No painel **Nova coluna**, insira ou selecione os seguintes valores:

   1. Nome de exibição`Customer`
   1. Tipo de dados: **Linha única de texto**
   1. Obrigatório: **Empresa necessária**

1. Selecione **Salvar**.

1. No painel **Colunas e dados de Oportunidade**, selecione **+** para adicionar uma nova coluna.

1. No painel **Nova coluna**, insira ou selecione os seguintes valores:

   1. Nome de exibição`Address`
   1. Tipo de dados: **Linha única de texto**
   1. Obrigatório: **Opcional**

1. Expanda **Opções avançadas** e insira `200` em **Contagem máxima de caracteres**.

1. Selecione **Salvar**.

1. No painel **Colunas e dados de Oportunidade**, selecione **+** e, no painel **Nova coluna**, insira ou selecione os seguintes valores:

   1. Nome de exibição`Estimated Close Date`
   1. Tipo de dados: **Data e hora**
   1. Formato: **Somente data**
   1. Obrigatório: **Opcional**

1. Selecione **Salvar**.

1. No painel **Colunas e dados de Oportunidade**, selecione **+** e, no painel **Nova coluna**, insira ou selecione os seguintes valores:

   1. Nome de exibição`Amount`
   1. Tipo de dados: **Moeda**
   1. Obrigatório: **Opcional**

1. Selecione **Salvar**.

1. No painel **Colunas e dados de Oportunidade**, selecione **+** e, no painel **Nova coluna**, insira ou selecione os seguintes valores:

   1. Nome de exibição`Notes`
   1. Tipo de dados: **Várias linhas de texto**
   1. Formato: **Text**
   1. Obrigatório: **Opcional**

1. Selecione **Salvar**.


### Tarefa 1.4 – Adicionar coluna de escolha

1. No painel **Colunas e dados de Oportunidade**, selecione **+** e, no painel **Nova coluna**, insira ou selecione os seguintes valores:

   1. Nome de exibição`Status`
   1. Tipo de dados: **Escolha** > **Escolha**
   1. Obrigatório: **Opcional**

1. Selecione **Não** para **Sincronização com escolha global?**

1. Insira `New` para **Rótulo** e insira `1` para **Valor**.

1. Selecione **+ Nova escolha** e insira `Open` para **Rótulo** e insira `2` para **Valor**.

1. Selecione **+ Nova escolha** e insira `Closed` para **Rótulo** e insira `3` para **Valor**.

1. Selecione **Novo** em **Escolha padrão**.

    ![Captura de tela do painel de colunas de nova escolha.](../media/new-local-choice.png)

1. Selecione **Salvar**.


## Exercício 2 – Criar relação

### Tarefa 2.1 – Criar uma coluna de pesquisa

1. Navegue até o portal do Power Apps Maker `https://make.powerapps.com`

1. Verifique se você está no ambiente **Dev One**.

1. No painel de navegação esquerdo, selecione **Tabelas**.

1. Selecione **Oportunidade**.

1. No painel **Colunas e dados de Oportunidade**, selecione **+** e, no painel **Nova coluna**, insira ou selecione os seguintes valores:

   1. Nome de exibição`Account`
   1. Tipo de dados: **Pesquisa**
   1. Obrigatório: **Opcional**
   1. Tabela relacionada: **Conta**

    ![Captura de tela do novo painel de colunas de pesquisa.](../media/new-lookup.png)

1. Selecione **Salvar**.

## Exercício 3 – Dados

### Tarefa 3.1 – Adicionar registros de oportunidade

1. Navegue até o portal do Power Apps Maker `https://make.powerapps.com`

1. Verifique se você está no ambiente **Dev One**.

1. No painel de navegação esquerdo, selecione **Tabelas**.

1. Selecione **Oportunidade**.

1. No painel **Colunas e dados da oportunidade**, selecione o cursor suspenso ao lado de **Editar** e selecione **Editar na nova guia**.

1. Selecione **+ Nova linha** e insira ou selecione os seguintes valores:

   1. Assunto da oportunidade: `100 Widgets`
   1. Nome do proprietário: `MOD Administrator`
   1. Cliente: `Adventure Works`
   1. Data de fechamento estimada: **Escolher uma data no mês anterior**
   1. Valor: `10,000`
   1. Status: **Fechada**

1. Selecione **Inserir linha abaixo** e insira ou selecione os seguintes valores:

   1. Assunto da oportunidade: `Key customer`
   1. Nome do proprietário: `MOD Administrator`
   1. Cliente: `Fabrikam`
   1. Data de fechamento estimada: **Escolher uma data futura no mês atual**
   1. Status: **Novo**
   1. Valor: `50,000`

1. Selecione **Inserir linha abaixo** e insira ou selecione os seguintes valores:

   1. Assunto da oportunidade: `New customer`
   1. Nome do proprietário: `MOD Administrator`
   1. Cliente: `Coho Winery`
   1. Data de fechamento estimada: **Escolher uma data futura no próximo mês**
   1. Valor: `25,000`
   1. Status: **Novo**

1. Selecione **Inserir linha abaixo** e insira ou selecione os seguintes valores:

   1. Assunto da oportunidade: `Repeat customer`
   1. Nome do proprietário: `MOD Administrator`
   1. Cliente: `Fourth Coffee`
   1. Data de fechamento estimada: **Escolher uma data futura no próximo mês**
   1. Valor: `15,000`
   1. Status: **Aberta**

    ![Captura de tela do painel editar dados.](../media/edit-data.png)

1. Feche a guia.
