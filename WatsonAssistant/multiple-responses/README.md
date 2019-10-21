# Respostas múltiplas condicionadas

Este recurso permite que um mesmo nó responda o usuário de diferentes maneiras baseados em condições. A título de exemplo, considere que no nó de boas-vindas desejamos emitir um cumprimento de acordo com a hora do dia:

* Até às 11h59m: Bom dia!
* A partir das 12h e antes das 18h: Boa tarde!
* A partir das 18h: Boa noite!

Naturalmente poderíamos criar algo como apresentado no exemplo a seguir.

![](MultipleResponsesExample01.gif)

Observe que nesse exemplo foram utilizadas algumas variáveis e funções para manipulação de data e hora. Para mais informações sobre manipulação de data e hora acesse a documentação [neste](https://cloud.ibm.com/docs/services/assistant?topic=assistant-dialog-methods#dialog-methods-date-time) endereço.

Apesar de funcionar muito bem, essa não é a forma mais elegante de criar respostas múltiplas. Portanto, vamos utilizar um recurso do Watson Assistant criado para esse tipo de situação: *Multiple conditioned responses*.

Para habilitar esse recurso, selecione o nó desejado. À direita do nome do nó clique no botão **Customize**. Na janela de customização, encontre e habilite a opção *Multiple conditioned responses*. Clique em **Apply** para concluir.

![](EnableMultipleConditionedResponses.gif)

Note que após a opção *Multiple conditioned responses* o nó mudou de aparência. Agora, na seção *Assistant responds*, é possível adicionar diferentes respostas baseadas em condições.

[Voltar](../)