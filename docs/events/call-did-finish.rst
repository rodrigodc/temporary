CallDidFinish
=============

Indica o fim do atendimento de uma chamada na fila cujo id é ``<id>``.


Origem
------

* **Sala de conferência:** ``queue.<id>@conference.platform.converja.com``


Evento
------

* **Nome:** ``CallDidFinish``
* **Parâmetros:**
 * ``callid``: id da chamada
 * ``destination``: id do atendente que atendeu a chamada
 * ``duration``: duração da chamada em segundos
 * ``origin``: número de origem da chamada
 * ``queue``: id da fila à qual a chamada pertence
 * ``timestamp``: momento em que a chamada foi finilizada


Exemplo
^^^^^^^

Evento recebido em ``queue.7@conference.platform.converja.com`` que indica o fim do atendimento de uma chamada vinda do número ``01921215544`` na fila cujo id é ``7`` após pouco mais de ``352`` segundos de duração:

.. code-block:: json

    {  
        "id":1,
        "type":"event",
        "name":"CallDidFinish",
        "params":{  
            "callid":123,
            "destination":"22010",
            "duration":352.33586382865906,
            "origin":"01921215544",
            "queue":7,
            "timestamp":1468419340.901568
        }
    }
