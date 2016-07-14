UserSessionDidFinish
====================

Indica o logout de um atendente.


Origem
------

* **Sala de conferência:** ``catraquis@conference.platform.converja.com``


Evento
------

* **Nome:** ``UserSessionDidFinish``
* **Parâmetros:**

 * ``agent``: id do atendente
 * ``queues``: ids das filas das quais o atendente é membro
 * ``timestamp``: momento em que o logout ocorreu


Exemplo
^^^^^^^

Evento recebido em ``catraquis@conference.platform.converja.com`` que indica o logout de um atendente cujo id é ``22010`` e membro da fila cujo id é ``7``.

.. code-block:: json

    {
        "id": 1,
        "type": "event",
        "name": "UserSessionDidFinish",
        "params": {
            "agent": "22010",
            "queues": [7],
            "timestamp": 1468494931.332954
        }
    }
