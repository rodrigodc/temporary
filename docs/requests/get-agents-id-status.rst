GET /agents/:id/status
======================

Solicita o estado atual do atendente cujo id é ``:id``.


Destino
-------

* **Sala de conferência:** ``filis@conference.platform.converja.com``
* **Membro:** ``filis@conference.platform.converja.com/filis``


Requisição
----------

* **Método:** ``GET``
* **Recurso:** ``/agents/:id/status``
* **Parâmetros:** nenhum


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``filis@conference.platform.converja.com/filis`` solicita o estado atual do atendente cujo id é ``22010``:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "GET",
        "resource": "/agents/22010/status",
        "params": {}
    }


Resposta
--------

``Object`` cujos campos descrevem o estado do atendente:

 * ``agent``: id do atendente
 * ``name``: estado do atendente
 * ``show``: complemento do estado
 * ``timestamp``: momento de início do estado atual

O estado do atendente descrito pelo campo ``name`` pode ser:

 * ``idle``: se o atendente está livre
 * ``busy``: se o atendente está atendendo uma chamada
 * ``paused``: se o atendente está bloqueado

O complemento do estado descrito pelo campo ``show`` é sempre ``null`` se o atendente está livre, o *número de origem da chamada* se o atendente está atendendo uma chamada ou o *id do motivo de bloqueio* se o atendente está bloqueado.


Exemplo 1
^^^^^^^^^

A mensagem abaixo indica que o atendente cujo id é ``22010`` está livre desde ``1468526509.844612``:

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {
            "agent": "22010",
            "name": "idle",
            "show": null,
            "timestamp": 1468526509.844612
        }
    }


Exemplo 2
^^^^^^^^^

A mensagem abaixo indica que o atendente cujo id é ``22010`` está atendendo uma chamada vinda de ``01921215544`` desde ``1468526143.411364``:

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {
            "agent": "22010",
            "name": "busy",
            "show": "01921215544",
            "timestamp": 1468526143.411364
        }
    }


Exemplo 3
^^^^^^^^^

A mensagem abaixo indica que o atendente cujo id é ``22010`` está bloqueado pelo motivo de bloqueio cujo id é ``11`` desde ``1468522292.074272``:

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {
            "agent": "22010",
            "name": "paused",
            "show": "11",
            "timestamp": 1468522292.074272
        }
    }
