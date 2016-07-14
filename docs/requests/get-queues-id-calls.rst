GET /queues/:id/calls
=====================

Lista todas as chamadas aguardando atendimento e em atendimento da fila cujo id é ``:id``.


Destino
-------

* **Sala de conferência:** ``filis@conference.platform.converja.com``
* **Membro:** ``filis@conference.platform.converja.com/filis``


Requisição
----------

* **Método:** ``GET``
* **Recurso:** ``/queues/:id/calls``
* **Parâmetros:** nenhum


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``filis@conference.platform.converja.com/filis`` solicita a listagem de todas as chamadas aguardando atendimento e em atendimento da fila cujo id é ``7``:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "GET",
        "resource": "/queues/7/calls",
        "params": {}
    }


Resposta
--------

``Array`` de chamadas onde cada chamada é um ``Object`` cujos campos descrevem a mesma:

 * ``call``: id da chamada
 * ``callee``: id do atendente se a chamada está em atendimento, ou ``null``
 * ``caller``: número de origem da chamada
 * ``queue``: id da fila à qual a chamada pertence
 * ``timestamps``: ``Object`` cujos campos descrevem os momentos em que eventos ocorreram na chamada:

  * ``answer``: momento em que a chamada foi atendida, ou ``null``
  * ``hangup``: momento em que a chamada foi encerrada, ou ``null``
  * ``join``: momento em que a chamada começou a aguardar atendimento
  * ``miss``: momento em que a chamada foi abandonada, ou ``null``


Exemplo
^^^^^^^

A mensagem abaixo indica a existência de ``2`` chamadas na fila cujo id é ``7``:

 * A primeira cujo id é ``123``, vinda do número ``01921215544``, está aguardando atendimento desde ``1468515991.651137``.
 * A segunda cujo id é ``456``, vinda do numero ``01921215566``, começou a aguardar atendimento em ``1468515991.651137`` e está agora sendo atendida pelo atendente cujo id é ``22010`` desde ``1468516274.090253``.

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {
            "calls": [
                {
                    "call": 123,
                    "callee": null,
                    "caller": "01921215544",
                    "queue": 7,
                    "timestamps": {
                        "answer": null,
                        "hangup": null,
                        "join": 1468515991.651137,
                        "miss": null
                    }
                },
                {
                    "call": 456,
                    "callee": 22010,
                    "caller": "01921215566",
                    "queue": 7,
                    "timestamps": {
                        "answer": 1468516274.090253,
                        "hangup": null,
                        "join": 1468515991.651137,
                        "miss": null
                    }
                }
            ],
            "queue": 7,
            "timestamp": 1468515991.651137
        }
    }
