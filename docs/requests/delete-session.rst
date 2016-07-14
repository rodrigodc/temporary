DELETE /session
===============

Desloga o atendente cujo id é ``<id>``.


Destino
-------

* **Sala de conferência:** ``agent.<id>@conference.platform.converja.com``
* **Membro:** ``agent.<id>@conference.platform.converja.com/<id>``


Requisição
----------

* **Método:** ``DELETE``
* **Recurso:** ``/session``
* **Parâmetros:** nenhum


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``agent.22010@conference.platform.converja.com/22010`` solicita que o atendente cujo id é ``22010`` seja deslogado imediatamente:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "DELETE",
        "resource": "/session",
        "params": {}
    }


Resposta
--------

Nenhum parâmetro descreve a resposta, apenas o código de status.


Exemplo
^^^^^^^

A mensagem abaixo indica que o atendente foi deslogado com sucesso (código de status ``200``):

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {}
    }
