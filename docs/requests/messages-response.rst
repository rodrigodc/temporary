Especificação de mensagens: respostas
=====================================

Respostas são recebidas da Plataforma Converja® como mensagens conforme descrito abaixo.

Recebimento
-----------

Uma resposta recebida é necessariamente o resultado de uma requisição enviada anteriomente e está, portanto, ligada a ela.

Respostas são recebidas como *mensagens privadas* do *mesmo* membro da sala de conferência *XMPP* para onde a respectiva requisição foi enviada anteriomente.


Assincronismo
-------------

O recebimento ocorre de modo assíncrono, ou seja, respostas *não* são recebidas necessariamente na mesma sequência de envio das respectivas requisições.

O campo ``to`` das mensagens, descrito abaixo, cumpre a função de relacionar a resposta à sua respectiva requisição de modo em que a ordem de recebimento não seja relevante.


Mensagem
--------

Uma resposta deve ser uma mensagem no formato *JSON* contendo um ``Object`` cujos campos descrevem o conteúdo respondido:

 * ``id``: número único que serve para identificar a resposta.
 * ``type``: o tipo de mensagem e deve sempre ser ``response``.
 * ``to``: o número identificador da requisição à qual a resposta se refere.
 * ``failure``: se a resposta indica sucesso (``false``) ou falha (``true``).
 * ``status``: o código de status da resposta.
 * ``params``: o conteúdo da resposta.

Em geral, o código de status da resposta é:

 * ``200`` em caso de sucesso.
 * ``400`` caso a requisição seja inválida, por exemplo faltando algum parâmetro requerido.
 * ``404`` caso o recurso da requisição não exista.
 * ``405`` caso o método da requisição não seja permitido para o recurso.
 * ``500`` em caso de problemas para atender à requisição.

O campo ``params`` é um ``Object`` cujos campos descrevem o conteúdo da resposta.

Por exemplo, a mensagem abaixo é uma resposta que se refere a uma requisição enviada anteriormente cujo id é ``1``, indica sucesso, código de status ``200`` e contém a listagem das filas como um ``Array`` no parâmetro ``data``:

.. code-block:: json

    {  
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {  
            "data": [  
                {  
                    "id": 7,
                    "name": "Financeiro"
                },
                {  
                    "id": 8,
                    "name": "Suporte Técnico"
                },
                {  
                    "id": 9,
                    "name": "Vendas"
                }
            ]
        }
    }
