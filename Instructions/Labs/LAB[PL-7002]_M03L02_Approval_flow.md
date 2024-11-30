---
lab:
  title: '‘Laboratório 4: Fluxo de aprovação'
  module: 'Module 3: Build approval flows with Power Automate'
---

# Laboratório de prática 4 – Fluxo de aprovação

Neste laboratório, você criará um fluxo de aprovação.

## O que você aprenderá

- Como criar um fluxo de nuvem de aprovações do Power Automate

## Macroetapas do laboratório

- Criar um fluxo de nuvem automatizado para a lista do SharePoint
- Criar uma aprovação
- Adicionar condição para o resultado da aprovação
- Testar o fluxo
  
## Pré-requisitos

- Precisa ter concluído o **Laboratório 3: SharePoint**

## Etapas detalhadas

## Exercício 1 – Criar fluxo de aprovação

### Tarefa 1.1 – Criar o gatilho

1. Navegue até o portal do Power Automate `https://make.powerautomate.com`.

1. Verifique se você está no ambiente **Dev One**.

1. Cliue na guia **+ Criar** no menu de navegação à esquerda.

1. Selecione **Fluxo de nuvem automatizado**.

1. Insira `Task approval` em **Nome do fluxo**.

1. Insira `SharePoint` em Pesquisar todos os gatilhos.

1. Selecione **Quando um item é criado**.

1. Selecione **Criar**.


### Tarefa 1.2 – Configurar o gatilho

1. Selecione a etapa **Quando um item é criado**.

1. Selecione o nome da etapa **Quando um item é criado** e insira `New task`.

1. Selecione o **Site do SharePoint do Power Automate** criado no laboratório anterior. Se o site não estiver listado, selecione **Inserir valor personalizado** e cole a URL do site do SharePoint do Power Automate

1. Selecione a lista **Tarefas**.

    ![Captura de tela do gatilho do SharePoint.](../media/sharepoint-trigger.png)


### Tarefa 1.3 – Adicionar ação de aprovação

1. Selecione o ícone **+** na etapa de gatilho e selecione **Adicionar uma ação**.

1. Insira `approval` na pesquisa.

    ![Captura de tela da pesquisa de aprovações.](../media/search-approval.png)

1. Selecione **Iniciar e aguardar uma aprovação** em **Aprovações**.

1. Selecione **Criar Novo**.

1. Selecione **Aprovar/Rejeitar – o primeiro a responder** para o **Tipo de aprovação**

1. Clique no nome da etapa **Iniciar e aguardar uma aprovação** e insira `Approval`

1. Insira `/` no campo **Título** e clique em **Inserir conteúdo dinâmico**.

1. Clique em **Título** em **Nova tarefa**.

    ![Captura de tela do conteúdo dinâmico do item do SharePoint.](../media/sharepoint-dynamic-content.png)

1. Insira sua ID de usuário de locatário para **Atribuído a**.

1. Insira `/` no campo **Detalhes** e clique em **Inserir conteúdo dinâmico**.

1. Selecione **Descrição**.

1. Insira `/` no campo **Link do item** e clique em **Inserir conteúdo dinâmico**. 

1. Clique em **Ver mais** e depois em **Vincular ao item**.


### Tarefa 1.4 – Adicionar condição

1. Selecione o ícone **+** na etapa de aprovação e selecione **Adicionar uma ação**.

1. Insira `condition` na pesquisa.

1. Selecione **Condição** em **Controle**.

1. Insira `/` no campo **Escolher um valor** e clique em **Inserir conteúdo dinâmico**.

    ![Captura de tela do conteúdo dinâmico para uma condição.](../media/add-condition.png)

1. Selecione **Resultado**.

1. Selecione **é igual a** em **Operador**.

1. Clique no campo do lado direito **Escolher um valor** e insira `Approve`

    ![Captura de tela da condição.](../media/condition.png)


### Tarefa 1.5 – Ações de atualização de status

1. Selecione o ícone **+** em **True** e selecione **Adicionar uma ação**.

1. Insira `update item` na pesquisa.

1. Selecione **Atualizar item** em **SharePoint**.

1. Clique no nome da etapa **Atualizar item** e insira `Set task to approved`

1. Selecione o **site do SharePoint do Power Automate**.

1. Escolha a lista **Tarefas**.

1. Insira `/` no campo **ID** e clique em **Inserir conteúdo dinâmico**.

1. Clique em **ID** em **Nova tarefa**.

1. Selecione **Mostrar tudo** em **Parâmetros avançados**.

1. Insira `/` no campo **Título** e clique em **Inserir conteúdo dinâmico**.

1. Selecione **Título** em **Nova tarefa**.

1. Selecione **Aprovado** para **Valor de status de aprovação**.

1. Selecione o ícone **+** em **False** e selecione **Adicionar uma ação**.

1. Insira `update item` na pesquisa.

1. Selecione **Atualizar item** em **SharePoint**.

1. Selecione o nome da etapa **Atualizar item 1** e insira `Set task to declined`.

1. Selecione o **site do SharePoint do Power Automate**.

1. Escolha a lista **Tarefas**.

1. Insira `/` no campo **ID** e clique em **Inserir conteúdo dinâmico**.

1. Clique em **ID** em **Nova tarefa**.

1. Selecione **Mostrar tudo**.

1. Insira `/` no campo **Título** e clique em **Inserir conteúdo dinâmico**.

1. Selecione **Título** em **Nova tarefa**.

1. Selecione **Recusado** para o **Valor do Status de Aprovação**.

1. Selecione **Salvar**.

1. Selecione o botão Voltar **<-** no canto superior esquerdo da barra de comandos.


## Exercício 2 – Aprovação de teste

### Tarefa 2.1 – Disparar fluxo de aprovação

1. Navegue até o site do SharePoint e selecione a lista **Tarefas**.

1. Selecione **+ Adicionar novo item**, insira os seguintes dados e escolha **Salvar**:

   1. Título=`Approval test`
   1. Descrição`Test`
   1. Nome do Proprietário=`MOD Administrator`
   1. Prazo=**Hoje**
   1. Status de aprovação=**Novo**


### Tarefa 2.2 – Aprovação de progresso

1. Navegue até o portal do Power Automate `https://make.powerautomate.com`.

1. Verifique se você está no ambiente **Dev One**.

1. Clique na guia **Meus fluxos** no menu de navegação à esquerda.

1. Selecione **Aprovação da tarefa**.

1. Selecione a data e a hora no histórico de execução do fluxo.

    > **Observação:** a funcionalidade Aprovações será instalada em segundo plano. Isso levará aproximadamente 10 minutos.

1. Clique na guia **Aprovações** no menu de navegação esquerdo.

    ![Captura de tela das aprovações no portal.](../media/approvals.png)

1. Selecione o **Teste de aprovação**, selecione o **Tique** e selecione **Confirmar**.

1. Selecione **Concluído**.

1. Clique na guia **Meus fluxos** no menu de navegação à esquerda.

1. Selecione **Aprovação da tarefa**.

1. Escolha a data e a hora no **Histórico de execuções de 28 dias**.

1. Navegue até o site do SharePoint e selecione a lista **Tarefas**.

1. Verifique se o **Status de aprovação** do item de **Teste de aprovação** é **Aprovado**.

