# Voice Agent

O **Voice Agent** é uma tecnologia da IBM que permite realizar comunicação com assistentes construídos com o Watson Assistant através de chamadas telefônicas. Isso mesmo! Nós vamos ligar para um número de telefone e quem irá nos atender será o nosso assistente virtual.

Para fazer essa mágica acontecer, a IBM usa duas API's adicionais:

1. **Speech to Text**: Transforma fala em texto.
2. **Text to Speech**: Transforma texto em fala.

A imagem abaixo foi extraída da [documentação oficial](https://cloud.ibm.com/docs/services/voice-agent?topic=voice-agent-about#watson) da IBM e ilustra como funciona o processo de comunicação.

![](https://cloud.ibm.com/docs-content/v1/content/2f01e455e40ca9ab1a0aff24636a1c4d4edda527/services/voice-agent/images/conversation-flow.png)

1. A pessoa que iniciou a ligação faz uma pergunta.
2. A fala é enviada para o serviço **Speech to Text**.
3. A transcrição do texto é retornada.
4. O texto é enviado para o serviço **Watson Assistant** como um mensagem.
5. A resposta para a mensagem é retornada.
6. O texto da resposta é enviado para o serviço **Text to Speech**.
7. O áudio sintetizado é retornado.
8. O **Voice Agent with Watson** envia a resposta para a pessoa.

## Integrando com o Voice Agent

Na plataforma Watson Assistant:

* Acesse a seção **Assistants**

  ![](assistants.png)
* Selecione o assistente desejado

  ![](select-assistant.png)
* Acione o botão **Add integration**

  ![](add-integration.png)
* Selecione a opção **Voice Agent (Telephony)**

  ![](voice-agent.png)

Você será redirecionado para uma página para realizar o provisionamento do serviço **Voice Agent with Watson**.

* Selecione a região onde o serviço será provisionado

  ![](select-region.png)
* Mantenha o plano **Lite** selecionado

  ![](select-a-pricing-plan.png)
* Na parte inferior da página, batize o seu serviço

  ![](service-name.png)
* Para concluir, clique em **Create**, localizado no painel à direita

  ![](create.png)

Depois de concluir o provisionamento do serviço **Voice Agente with Watson**, você será redirecionado para uma página com instruções para configuração do serviço.

Para permitir chamadas telefônicas, nós precisamos adiquirir um tronco SIP (*SIP trunk*). Nós podemos adiquirir esse serviço com um dos seguintes provedores:

* [Nexmo](https://dashboard.nexmo.com/sign-up)
* [NetFoundry](https://watson.netfoundry.io/watson-login)
* [Twillio](https://www.twilio.com/try-twilio)
* [VoxImplant](https://voximplant.com/sign-up)

Neste tutorial vamos usar o Twillio.

### Criando um SIP Trunk no Twillio

* Acesse [este](https://www.twilio.com/try-twilio) endereço para criar uma conta no Twillio
* Preencha o formulário de cadastro e clique em **Start your free trial**

  ![](twillio-sign-up.png)
* Verifica a caixa de entrada do seu e-mail para concluir o processo de criação da conta no Twillio

  ![](confirm-your-email.png)
* Informe um número de telefone válido para confirmar a sua conta

  ![](verify-phone-number.png)
* Um código de verificação será enviado para o telefone informado. Entre com esse código e clique em **Submit** para avançar

  ![](verification-code.png)
* Siga os passos para concluir a criação da conta

Após finalizar a criação da conta, você será direcionado para o painel do Twillio. Clique no botão **Get a Trial Number** para obter um número de testes com $15.50 de crédito.

![](get-a-trial-number.png)

Agora vamos criar um *SIP Trunk*.

* No menu lateral do Twillio, clique no símbolo **...** para abrir o menu completo

  ![](twillio-main-menu.png)
* No menu principal, selecione a opção **Elastic SIP Trunking**

  ![](elastic-sip-trunking.png)
* Na barra de navegação selecione a opção **Trunks**

  ![](trunks.png)
* Clique no botão **Create new SIP Trunk**

  ![](create-new-sip-trunk.png)
* Dê um novo amigável para o seu *SIP Trunk* e clique em **Create**

  ![](create-a-new-sip-trunk.png)
* Uma nova barra de navegação com as opções do novo *SIP Trunk* será exibida. Selecione a opção **Origination**

  ![](origination.png)
* Clique no botão **Add new Origination URI**

  ![](add-new-origination-uri.png)
* No campo **ORIGINATION SIP URI**, cole a URI disponibilizada no campo **Your agent endpoint**, na página de configuração do **Voice Agent with Watson**

  ![](your-agent-endpoint.png)
  ![](add-origination-url.png)
* Na barra de opções do *SIP Trunk*, selecione a opção **Numbers**

  ![](numbers.png)
* Clique no botão **Add an Existing Number**

  ![](add-an-existing-number.png)
* Na janela, selecione o número *trial* que criamos anteriormente e clique em **Add Selected** para concluir

  ![](add-an-number.png)

### Configurando o Voice Agent with Watson

Retornando à página de configuração do Voice Agent with Watson, na terceira seção, intitulada **Create and connect your agent**, clique na opção **Create an agent**.

![](create-an-agent.png)

Você será direcionado para um formulário de configuração do agente de voz.

* **Agent Type**: Selecione a opção **Voice**.
* **Name**: Dê um nome para o seu agente.
* **Phone number(s)**.
  * Clique em **Manage**

    ![](manage-phone-number.png)
  * Clique no símbolo **+** para incluir um número

    ![](add-phone-number.png)
  * Informe o número de telefone *trial* fornecido pelo Twillio

    ![](insert-phone-number.png)
  * Confirme a inclusão do número

    ![](save-phone-number.png)
  * Selecione o novo número incluído

    ![](select-number.png)
  * Clique em **Done** para concluir

    ![](done.png)

Na seção **Conversation**:

* **Service credentials**: Selecione a primeira opção disponível.
* **Skill name**: Selecione a *skill* do seu *chatbot*.

![](conversation.png)

As demais opção serão configuradas automaticamente. Para concluir, clique em **Create an agent**, no topo da página.

![](create-an-agent-save.png)

Se tudo correr bem, você verá algo semelhante a isto:

![](success.png)

Agora vamos fazer algumas configurações adicionais. Primeiro, clique sobre o menu do agente de voz recém criado e selecione a opção **Edit agent**.

![](edit-agent.png)

Navegue até a seção **Speech to Text**. No campo **Model** selecione um modelo do tipo português brasileiro, para indicar que o idioma reconhecido será o português do Brasil.

![](speech-to-text-model.png)

Na seção **Text to Speech**, no campo **Voice**, selecione um modelo de voz do tipo **pt-BR**.

![](text-to-speech-voice.png)

Clique em **Save changes** para concluir.

![](save-changes.png)

## É hora do show!

Pegue o seu telefone e faça uma ligação para o número de telefone *trial* fornecido pelo Twillio.

![](https://media.giphy.com/media/DKnMqdm9i980E/giphy.gif)

[Voltar](../)