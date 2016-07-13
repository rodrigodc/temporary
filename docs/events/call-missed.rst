CallMissed
==========

Indica o abandono de uma chamada na fila cujo id é ``<id>``.


Origem
------

* **Sala de conferência:** ``queue.<id>@conference.platform.converja.com``


Evento
------

* **Nome:** ``CallMissed``
* **Parâmetros:**
 * ``callid``: id da chamada
 * ``duration``: tempo de espera em segundos antes do abandono
 * ``origin``: número de origem da chamada
 * ``queue``: id da fila à qual a chamada pertence
 * ``timestamp``: momento em que a chamada foi abandonada


Exemplo
^^^^^^^

Evento recebido em ``queue.7@conference.platform.converja.com`` que indica o abandono de uma chamada vinda do número ``01921215544`` na fila cujo id é ``7`` após pouco mais de ``401`` segundos de espera:

.. code-block:: json

    {
        "id": 1,
        "type": "event",
        "name": "CallMissed",
        "params": {
            "callid": 123,
            "duration": 401.4312560558319,
            "origin": "01921215544",
            "queue": 7,
            "timestamp": 1468419508.22246
        }
    }
