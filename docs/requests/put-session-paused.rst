PUT /session/paused
===================

Bloqueia ou desbloqueia o atendente cujo id é ``<id>``.


Destino
-------

* **Sala de conferência:** ``agent.<id>@conference.platform.converja.com``
* **Membro:** ``agent.<id>@conference.platform.converja.com/<id>``


Requisição
----------

* **Método:** ``PUT``
* **Recurso:** ``/session/paused``
* **Parâmetros:**

 * ``value``: ``0`` para *desbloquear* ou um id de motivo de bloqueio para *bloquear*


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``agent.22010@conference.platform.converja.com/22010`` bloqueia o atendente cujo id é ``22010`` pelo motivo cujo id é ``11``:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "PUT",
        "resource": "/session/paused",
        "params": {
            "value": 11
        }
    }


Resposta
--------

Nenhum parâmetro descreve a resposta, apenas o código de status.


Exemplo
^^^^^^^

A mensagem abaixo indica que o atendente foi bloqueado com sucesso (código de status ``200``):

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {}
    }
