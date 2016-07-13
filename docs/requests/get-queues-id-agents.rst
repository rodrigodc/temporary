GET /queues/:id/agents
======================

Lista todos os atendentes da fila de atendimento cujo id é ``:id``.


Destino
-------

* **Sala de conferência:** ``filis@conference.platform.converja.com``
* **Membro:** ``filis@conference.platform.converja.com/filis``


Requisição
----------

* **Método:** ``GET``
* **Recurso:** ``/queues/:id/agents``
* **Parâmetros:** nenhum


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``filis@conference.platform.converja.com/filis`` solicita a listagem de todos os atendentes da fila de atendimento cujo id é ``7``:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "GET",
        "resource": "/queues/7/agents",
        "params": {}
    }


Resposta
--------

``Array`` de atendentes onde cada atendente é um ``Object`` cujos campos descrevem o mesmo:

 * ``agent``: id do atendente
 * ``name``: nome do atendente


Exemplo
^^^^^^^

A mensagem abaixo indica a existência de ``3`` atendentes cujos nomes são ``Ana Cláudia da Silva``, ``Bruno dos Reis`` e ``Camila Borges`` e os ids são ``22031``, ``22034`` e ``22039``, respectivamente:

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {
            "data": [
                {
                    "name": "Ana Cláudia da Silva",
                    "agent": "22031"
                },
                {
                    "name": "Bruno dos Reis",
                    "agent": "22034"
                },
                {
                    "name": "Camila Borges",
                    "agent": "22039"
                }
            ]
        }
    }
