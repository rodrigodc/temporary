Especificação de mensagens: eventos
===================================

Eventos são recebidos da Plataforma Converja® como mensagens conforme descrito abaixo.


Recebimento
-----------

Eventos são recebidos como *mensagens de grupo* em salas de conferência *XMPP*.

A sala de conferência onde a mensagem é recebida varia de acordo com o evento de interesse. A mesma está especificada na documentação de cada um dos tipos de evento descritos neste documento.

Para inscrever-se para receber eventos de determinado tipo basta entrar na sala de conferência para onde eles são enviados segundo sua documentação.


Mensagem
--------

Um evento deve ser uma mensagem no formato *JSON* contendo um ``Object`` cujos campos descrevem seu conteúdo:

 * ``id``: número único que serve para identificar o evento.
 * ``type``: o tipo de mensagem e deve sempre ser ``event``.
 * ``name``: o nome do evento.
 * ``params``: os parâmetros do evento.

O campo ``params`` é um ``Object`` cujos campos descrevem o evento.

Por exemplo, a mensagem abaixo é um evento cujo nome é ``CallDidStart`` e cujos parâmetros que o descrevem são ``callid``, ``destination``, ``origin``, ``queue`` e ``timestamp``:

.. code-block:: json

    {
        "id": 1,
        "type": "event",
        "name": "CallDidStart",
        "params": {
            "callid": 123,
            "destination": "22010",
            "origin": "01921215544",
            "queue": 7,
            "timestamp": 1468418331.7214
        }
    }

