PUT /calls/active/local
=======================

Transfere a chamada que o atendente cujo id é ``<id>`` está atendendo no momento.


Destino
-------

* **Sala de conferência:** ``agent.<id>@conference.platform.converja.com``
* **Membro:** ``agent.<id>@conference.platform.converja.com/<id>``


Requisição
----------

* **Método:** ``PUT``
* **Recurso:** ``/calls/active/local``
* **Parâmetros:**

 * ``value``: número do destino de transferência da chamada


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``agent.22010@conference.platform.converja.com/22010`` transfere para o número ``11001`` a chamada que o atendente cujo id é ``22010`` está atendendo no momento:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "PUT",
        "resource": "/calls/active/local",
        "params": {
            "value": "11001"
        }
    }


Resposta
--------

Nenhum parâmetro descreve a resposta, apenas o código de status.


Exemplo
^^^^^^^

A mensagem abaixo indica que a chamada foi transferida com sucesso (código de status ``200``):

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {}
    }
