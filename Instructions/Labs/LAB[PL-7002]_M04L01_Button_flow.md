---
lab:
  title: 'Laboratório 5: Fluxo de botão'
  module: 'Module 4: Build flows to manage user information'
---

# Laboratório prático 5 – Fluxo de botão

Neste laboratório, você criará um fluxo de botão.

## O que você aprenderá

- Como criar um fluxo de botão instantâneo do Power Automate

## Macroetapas do laboratório

- Criar um fluxo de botão
- Usar tokens de gatilho
- Adicionar entrada de usuário
- Testar o fluxo
  
## Pré-requisitos

- É necessário ter concluído **Laboratório 2: Modelo de dados**

## Etapas detalhadas

## Exercício 1 – Criar fluxo de botão

### Tarefa 1.1: Criar o gatilho

1. Navegue até o portal do Power Automate `https://make.powerautomate.com`.

1. Certifique-se de que você esteja no ambiente **Dev One**.

1. Selecione a guia **+ Criar** no menu esquerdo.

1. Selecione **Fluxo da nuvem instantâneo**.

1. Insira `Create opportunity` em **Nome do fluxo**.

1. Expanda **Disparar um fluxo manualmente**.

1. Selecione **Criar**.


### Tarefa 1.2 – Adicionar entrada de usuário

1. Selecione a etapa **Disparar um fluxo manualmente**.

1. Clique no nome da etapa **Disparar um fluxo manualmente** e insira `Button triggered`

1. Selecione **Adicionar uma entrada**.

1. Selecione **Texto**.

1. Insira `Customer Name` em **Entrada**.

1. Insira `Please enter the customer name` em **Insira sua entrada**.

1. Selecione **Adicionar uma entrada**.

1. Selecione **Texto**

1. Insira `Comments` em **Entrada**.

1. Insira `Any comments` em **Insira sua entrada**.

1. Selecione **Adicionar uma entrada**.

1. Selecione **Número**

1. Insira `Potential Sale` em **Número**.

    ![Captura de tela da entrada de usuário.](../media/user-input.png)


### Tarefa 1.3 – Adicionar ação de criação de oportunidade

1. Selecione o ícone **+** na etapa de gatilho e escolha **Adicionar uma ação**.

1. Insira `add row` na pesquisa.

1. Clique em **Adicionar uma nova linha** em **Microsoft Dataverse**.

1. Selecione **Entrar**

1. Use suas credenciais de locatário.

1. Selecione o nome da etapa **Adicionar uma nova linha** e insira `New opportunity`.

1. Escolha **Oportunidades** em **Nome da tabela**.

1. Insira `/` no campo **Cliente**, clique em **Inserir conteúdo dinâmico** e depois em **Ver mais**.

1. Selecione **Nome do Cliente**.

1. Clique no campo **Nome do proprietário** e insira `MOD Administrator`

1. Selecione **Mostrar tudo**.

1. Clique no campo **Assunto da oportunidade** e insira `New opportunity`

1. Insira `/` no campo **Quantidade** e clique em **Inserir conteúdo dinâmico**.

1. Selecione **Venda Potencial**.

1. Selecione o campo **Observações**, selecione o ícone de conteúdo dinâmico e selecione **Ver mais**.

1. Selecione **Comentários**.

1. Insira `/` no campo **Data de fechamento estimada** e clique em **Inserir expressão**.

1. Insira a expressão `utcNow()` e selecione **Adicionar**.

    ![Captura de tela da ação de nova oportunidade.](../media/new-opportunity-action.png)

1. Selecione **Salvar**.


## Exercício 2 – Fluxo de botão de teste

### Tarefa 2.1 – Executar fluxo de botão

1. Selecione **Testar**

1. Selecione **Manualmente**.

1. Selecione **Testar**.

    ![Captura de tela do fluxo de botão de teste.](../media/user-input-test.png)

1. Insira os seguintes detalhes:

   1. Nome do Cliente=`Button test`
   1. Comentários=`This is a test`
   1. Venda Potencial=`9999`

1. Selecione **Executar fluxo**.

1. Selecione **Concluído**.

1. Selecione o botão **<-** Voltar no canto superior esquerdo da barra de comandos.


### Tarefa 2.2 – Verificar o registro de oportunidade criado

1. Navegue até o portal do Power Apps Maker `https://make.powerapps.com`

1. Verifique se você está no ambiente **Dev One**.

1. No painel de navegação esquerdo, selecione **Tabelas**.

1. Selecione **Oportunidade**.

