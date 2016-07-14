DELETE /calls/active
====================

Desliga a chamada que o atendente cujo id é ``<id>`` está atendendo no momento.


Destino
-------

* **Sala de conferência:** ``agent.<id>@conference.platform.converja.com``
* **Membro:** ``agent.<id>@conference.platform.converja.com/<id>``


Requisição
----------

* **Método:** ``DELETE``
* **Recurso:** ``/calls/active``
* **Parâmetros:** nenhum


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``agent.22010@conference.platform.converja.com/22010`` solicita que a chamada que o atendente cujo id é ``22010`` está atendendo no momento seja desligada imediatamente:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "DELETE",
        "resource": "/calls/active",
        "params": {}
    }


Resposta
--------

Nenhum parâmetro descreve a resposta, apenas o código de status.


Exemplo
^^^^^^^

A mensagem abaixo indica que a chamada foi desligada com sucesso (código de status ``200``):

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {}
    }
