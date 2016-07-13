GET /queues
===========

Lista todas filas de atendimento existentes.


Destino
-------

* **Sala de conferência:** ``filis@conference.platform.converja.com``
* **Membro:** ``filis@conference.platform.converja.com/filis``


Requisição
----------

* **Método:** ``GET``
* **Recurso:** ``/queues``
* **Parâmetros:** nenhum


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``filis@conference.platform.converja.com/filis`` solicita a listagem de todas as filas de atendimento existentes:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "GET",
        "resource": "/queues",
        "params": {}
    }


Resposta
--------

``Array`` de filas onde cada fila é um ``Object`` cujos campos descrevem a mesma:

 * ``id``: id da fila de atendimento
 * ``name``: nome da fila de atendimento


Exemplo
^^^^^^^

A mensagem abaixo indica a existência de ``3`` filas cujos nomes são ``Financeiro``, ``Suporte Técnico`` e ``Vendas`` e os ids são ``7``, ``8`` e ``9``, respectivamente:

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
                    "id": 7,
                    "name": "Financeiro"
                },
                {
                    "id": 8,
                    "name": "Suporte Técnico"
                },
                {
                    "id": 9,
                    "name": "Vendas"
                }
            ]
        }
    }
