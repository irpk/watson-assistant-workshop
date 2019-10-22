# Telegram

O Telegram é o aplicativo de mensagens mais utilizado quando o WhatsApp está fora do ar 😂.

## Criando um bot no Telegram

Para criar um *chatbot* no Telegram integrado com o Watson Assistant, vá no telegram e inicie uma conversa com o **BotFather**.

![](bot-father.png)

Envie o comando `/newbot` e siga as instruções:

* Informe o nome do *bot*.
* Informe o *username* do *bot*. Ele deve terminar com o termo `bot`.

![](newbot.png)

Você receberá uma token de acesso que será usado posteriormente na integração.

## Provisionando o Node-RED

O Node-RED é uma ferramente de desenvolvimento baseada em fluxo para programação visual, que roda sobre Node.js.

Para provisionar o serviço Node-RED, acesse o *dashboard* da IBM Cloud e acione o botão **Create resource**.

![](create-resource.png)

Você será direcionado para o catálogo de serviços. Na lista de categorias, selecione a opção **Starter Kits**. Depois, selecione o serviço **Node-RED Starter**.

![](node-red-service.png)

* No campo **Select a region**, selecione a região onde deseja provisionar o serviço

  ![](select-a-region.png)
* Na seção **Select a pricing plan**, mantenha a opção **Lite** selecionada, tanto para **SDK for Node.js** como para **Cloudant**

  ![](select-pricing-plan.png)
* Preencha o campo **App name** com o nome do seu aplicativo.
* No campo **Host name** defina o nome da URL do seu aplicativo.
* No campo **Domain** selecione um dos domínios disponíveis.

  ![](configure-your-resource.png)
* Clique em **Create** para concluir

  ![](create.png)