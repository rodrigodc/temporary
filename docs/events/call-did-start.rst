CallDidStart
============

Indica o início do atendimento de uma chamada na fila cujo id é ``<id>``.


Origem
------

* **Sala de conferência:** ``queue.<id>@conference.platform.converja.com``


Evento
------

* **Nome:** ``CallDidStart``
* **Parâmetros:**
 * ``callid``: id da chamada
 * ``destination``: id do atendente que atendeu a chamada
 * ``origin``: número de origem da chamada
 * ``queue``: id da fila à qual a chamada pertence
 * ``timestamp``: momento em que a chamada foi atendida


Exemplo
^^^^^^^

Evento recebido em ``queue.7@conference.platform.converja.com`` que indica o início do atendimento de uma chamada vinda do número ``01921215544`` na fila cujo id é ``7`` pelo atendente cujo id é ``22010``:

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
