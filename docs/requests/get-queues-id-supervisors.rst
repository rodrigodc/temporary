GET /queues/:id/supervisors
===========================

Lista todos os supervisores da fila de atendimento cujo id é ``:id``.


Destino
-------

* **Sala de conferência:** ``filis@conference.platform.converja.com``
* **Membro:** ``filis@conference.platform.converja.com/filis``


Requisição
----------

* **Método:** ``GET``
* **Recurso:** ``/queues/:id/supervisors``
* **Parâmetros:** nenhum


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``filis@conference.platform.converja.com/filis`` solicita a listagem de todos os supervisores da fila de atendimento cujo id é ``7``:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "GET",
        "resource": "/queues/7/supervisors",
        "params": {}
    }


Resposta
--------

``Array`` de supervisores onde cada supervisor é um ``Object`` cujos campos descrevem o mesmo:

 * ``name``: nome do supervisor
 * ``supervisor``: id do supervisor


Exemplo
^^^^^^^

A mensagem abaixo indica a existência de ``2`` supervisores cujos nomes são ``Daniela de Almeida`` e ``Eduardo Teixeira`` e os ids são ``22090`` e ``22087``, respectivamente:

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
                    "name": "Daniela de Almeida",
                    "supervisor": "22090"
                },
                {
                    "name": "Eduardo Teixeira",
                    "supervisor": "22087"
                }
            ]
        }
    }
