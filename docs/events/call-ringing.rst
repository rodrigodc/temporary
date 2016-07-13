CallRinging
===========

Indica a entrada de uma chamada na fila cujo id é ``<id>``.


Origem
------

* **Sala de conferência:** ``queue.<id>@conference.platform.converja.com``


Evento
------

* **Nome:** ``CallRinging``
* **Parâmetros:**
 * ``callid``: id da chamada
 * ``origin``: número de origem da chamada
 * ``queue``: id da fila à qual a chamada pertence
 * ``timestamp``: momento em que a chamada entrou na fila


Exemplo
^^^^^^^

Evento recebido em ``queue.7@conference.platform.converja.com`` que indica a entrada de uma chamada vinda do número ``01921215544`` na fila cujo id é ``7``:

.. code-block:: json

    {
        "id": 1,
        "type": "event",
        "name": "CallRinging",
        "params": {
            "callid": 123,
            "origin": "01921215544",
            "queue": 7,
            "timestamp": 1468420431.355229
        }
    }
