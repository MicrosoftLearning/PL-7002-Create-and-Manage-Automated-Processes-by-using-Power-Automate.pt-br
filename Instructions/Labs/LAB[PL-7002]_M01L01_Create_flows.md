---
lab:
  title: 'Laboratório 1: Criar fluxos da nuvem'
  module: 'Module 1: Get started with Power Automate'
---

# Laboratório de prática 1 – Criar fluxos de nuvem

Neste laboratório, você criará fluxos de nuvem.

## O que você aprenderá

- Como criar fluxos de nuvem do Power Automate a partir de um modelo e com o CoPilot
- Como criar um fluxo de nuvem do Power Automate em branco e adicionar ações

## Macroetapas do laboratório

- Criar um fluxo da nuvem a partir de um modelo
- Criar um fluxo de nuvem com o Copilot
- Criar um fluxo da nuvem
- Monitorar a atividade de fluxo de nuvem
  
## Pré-requisitos

- Precisa ter concluído o **Laboratório 0: Validar o ambiente de laboratório**

## Etapas detalhadas

## Exercício 1 – Criar um fluxo de nuvem a partir de um modelo

### Tarefa 1.1 – Selecionar um modelo

1. Navegue até o portal do Power Automate `https://make.powerautomate.com`.

1. Se aparecer a caixa de diálogo pop-up **Boas-vindas ao Power Automate**, selecione **Introdução**.

1. Selecione o ambiente **Dev One**.

    ![Seletor de ambiente no Power Automate.](../media/select-dev-one-environment-power-automate.png)

1. Selecione a guia **Modelos** no menu esquerdo.

1. Selecione a guia **Botão**.

1. No campo **Pesquisar modelos**, insira `location`.

    ![Captura de tela dos modelos de fluxo.](../media/flow-templates.png)

1. Selecione **Obter a previsão do tempo de hoje para a minha localização atual**.

    ![Captura de tela da criação de conexões.](../media/create-connections.png)

1. Selecione **Criar** em **MSN Clima**.

1. Selecione **Criar** em **Notificações**.

1. Selecione **Criar Fluxo**.

1. Se aparecer a caixa de diálogo pop-up **Seu fluxo está pronto**, clique em **Não mostrar novamente** e depois em **Entendi**.

    ![Captura de tela dos detalhes do fluxo.](../media/flow-details.png)


### Tarefa 1.2 – Executar o fluxo

1. Selecione **Executar**.

1. Se solicitado, selecione **Permitir** em **Saber sua localização**

1. Selecione **Continuar**.

1. Selecione **Executar fluxo**.

1. Selecione **Concluído**.

    ![Captura de tela do histórico de execuções de fluxo.](../media/run-history.png)


### Tarefa 1.3 – Examinar o fluxo

1. Selecione a data e a hora no histórico de execução do fluxo.

    ![Captura de tela dos detalhes da execução do fluxo.](../media/flow-run-collapsed.png)

1. Selecione a etapa **Obter previsão para hoje** com o tique verde.

    ![Captura de tela da saída da etapa de execução de fluxo.](../media/flow-run-step.png)

1. Selecione **Editar**.

1. Selecione uma das etapas em **Enviar uma notificação por push**.

1. Selecione o **Verificador de fluxo**. Não deve haver erros ou avisos.

1. Feche o painel do **Verificador de fluxo**.


### Tarefa 1.4 – Testar o fluxo

1. Selecione **Testar**, selecione **Automaticamente**, selecione **Com um gatilho usado recentemente** e, em seguida, selecione a execução do fluxo.

    ![Captura de tela do fluxo de teste com o gatilho usado recentemente.](../media/test-flow.png)

1. Selecione **Testar**.

1. Selecione o botão Voltar **<-** no canto superior esquerdo da barra de comandos.


## Exercício 2 – Criar um fluxo de nuvem com o Copilot

### Tarefa 2.1 – Inserir um prompt

1. Navegue até o portal do Power Automate `https://make.powerautomate.com`. 

1. Certifique-se de que você esteja no ambiente **Dev One**.

1. Selecione a guia **Página Inicial** no menu esquerdo.

1. Em **Criar sua automação com o Copilot**, insira `Every day send me an email with the daily summary from MSN Weather`

    ![Captura de tela de solicitação do copilot.](../media/copilot-prompt.png)

1. Selecione **Gerar**.

    ![Captura de tela do fluxo sugerido.](../media/copilot-suggestion.png)

1. Selecione **Manter e continuar**.

1. Selecione **Criar fluxo**.

    ![Captura de tela do fluxo criado pelo Copilot.](../media/copilot-flow.png)


### Tarefa 2.2 – Configurar a etapa de fluxo

1. Selecione a etapa **Obter previsão para hoje**.

1. Insira `Seattle` para **Localização**.

1. Clique no **X** para limpar **Unidades** e, na lista suspensa, clique em **Imperial**.

    ![Captura de tela dos parâmetros da etapa de fluxo.](../media/flow-step-parameters.png)

1. Selecione **Salvar**.

1. Para testar seu fluxo, clique em **Testar**, na opção **Manualmente** e, depois, em **Testar**. 

1. Selecione **Executar fluxo** e, depois, **Concluído**.

1. Selecione o botão Voltar **<-** no canto superior esquerdo da barra de comandos.


## Exercício 3 – Criar um fluxo de nuvem em branco

### Tarefa 3.1 – Criar o gatilho

1. Navegue até o portal do Power Automate `https://make.powerautomate.com`.

1. Certifique-se de que você esteja no ambiente **Dev One**.

1. Selecione a guia **+ Criar** no menu esquerdo.

1. Selecione **Fluxo de nuvem automatizado**.

1. Insira `Important email` em **Nome do fluxo**.

1. No campo **Pesquisar todos os gatilhos**, insira `email arrives`.

1. Selecione **Quando um novo email chegar (V3)**.

    ![Captura de tela da caixa de diálogo Criar um fluxo automatizado.](../media/build-automated-flow.png)

1. Selecione **Criar**.


### Tarefa 3.2 – Configurar o gatilho

1. Selecione a etapa **Quando um novo email chegar (V3)**.

1. Selecione **Mostrar tudo**.

    ![Captura de tela da caixa de diálogo de fluxo automatizado de parâmetros de gatilho de email.](../media/email-trigger-parameters.png)

1. Selecione **Não** em **Incluir anexos**.

1. Selecione **Alta** em **Importância**.

1. Selecione **Caixa de entrada** em **Pasta**.


### Tarefa 3.3 – Adicionar uma ação

1. Selecione o ícone **+** na etapa de gatilho e selecione **Adicionar uma ação**.

1. Se solicitado, selecione **Permitir** para **Ver texto e imagens copiados para a área de transferência**.

1. Insira `notification` na pesquisa.

    ![Captura de tela da pesquisa de ação.](../media/search-action.png)

1. Selecione **Postar uma notificação no feed** em **Microsoft Teams**.

1. Selecione **Entrar**.

1. Use suas credenciais de locatário.

1. Selecione **Equipe** em **Tipo de notificação**.

1. Insira a ID de usuário do locatário em **Destinatário**.

1. No campo **Texto de notificação**, insira `/` e clique em **Inserir conteúdo dinâmico**.

    ![Captura de tela do conteúdo dinâmico.](../media/flow-dynamic-content.png)

1. Selecione **Assunto**.

1. Selecione **Contoso** em **Equipe**.

1. Selecione **Geral** em **Canal**.

1. Selecione **Salvar**.

1. Selecione o botão Voltar **<-** no canto superior esquerdo da barra de comandos.


## Exercício 4 – Monitorar fluxos

### Tarefa 4.1 – Atividade de fluxo de nuvem

1. Navegue até o portal do Power Automate `https://make.powerautomate.com`.

1. Certifique-se de que você esteja no ambiente **Dev One**.

1. Selecione **... Mais** do menu esquerdo.

    ![Captura de tela de mais opções do portal do Power Automate.](../media/power-automate-menu.png)

1. Selecione **Descobrir tudo** e pesquise **Atividade de fluxo da nuvem** na seção Monitorar.

1. Selecione o ícone de alfinete em **Atividade de fluxo de nuvem**.

1. Selecione a guia **Atividade de fluxo de nuvem** no menu esquerdo.

    ![Captura de tela da atividade de fluxo de nuvem.](../media/cloud-flow-activity.png)

