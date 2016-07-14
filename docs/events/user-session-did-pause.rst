UserSessionDidPause
===================

Indica o bloqueio de um atendente.


Origem
------

* **Sala de conferência:** ``catraquis@conference.platform.converja.com``


Evento
------

* **Nome:** ``UserSessionDidPause``
* **Parâmetros:**

 * ``agent``: id do atendente
 * ``queues``: ids das filas das quais o atendente é membro
 * ``reason``: id do motivo do bloqueio
 * ``timestamp``: momento em que o bloqueio ocorreu


Exemplo
^^^^^^^

Evento recebido em ``catraquis@conference.platform.converja.com`` que indica o bloqueio de um atendente cujo id é ``22010`` e membro da fila cujo id é ``7`` pelo motivo cujo id é ``11``.

.. code-block:: json

    {
        "id": 1,
        "type": "event",
        "name": "UserSessionDidPause",
        "params": {
            "agent": "22010",
            "queues": [7],
            "reason": "11",
            "timestamp": 1468494950.918491
        }
    }
