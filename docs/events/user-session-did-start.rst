UserSessionDidStart
===================

Indica o login de um atendente.


Origem
------

* **Sala de conferência:** ``catraquis@conference.platform.converja.com``


Evento
------

* **Nome:** ``UserSessionDidStart``
* **Parâmetros:**

 * ``agent``: id do atendente
 * ``queues``: ids das filas das quais o atendente é membro
 * ``timestamp``: momento em que o login ocorreu


Exemplo
^^^^^^^

Evento recebido em ``catraquis@conference.platform.converja.com`` que indica o login de um atendente cujo id é ``22010`` e membro da fila cujo id é ``7``.

.. code-block:: json

    {
        "id": 1,
        "type": "event",
        "name": "UserSessionDidStart",
        "params": {
            "agent": "22010",
            "queues": [7],
            "timestamp": 1468494948.61721
        }
    }
