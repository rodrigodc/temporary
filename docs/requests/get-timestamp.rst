GET /timestamp
==============

Solicita a data e horário atuais do atendente cujo id é ``<id>``.


Destino
-------

* **Sala de conferência:** ``agent.<id>@conference.platform.converja.com``
* **Membro:** ``agent.<id>@conference.platform.converja.com/<id>``


Requisição
----------

* **Método:** ``GET``
* **Recurso:** ``/timestamp``
* **Parâmetros:** nenhum


Exemplo
^^^^^^^

A mensagem abaixo enviada para ``agent.22010@conference.platform.converja.com/22010`` solicita a data e horário atuais do terminal onde o atendente cujo id é ``22010`` está logado no momento:

.. code-block:: json

    {
        "id": 1,
        "type": "request",
        "method": "GET",
        "resource": "/timestamp",
        "params": {}
    }


Resposta
--------

``Object`` cujos campos descrevem a data e horário atuais:

 * ``timestamp``: timestamp com data e horário atuais em *milissegundos*


Exemplo
^^^^^^^

A mensagem abaixo indica a data e horário atuais por meio do campo ``timestamp`` com o valor ``1468501446711`` em *milissegundos*:

.. code-block:: json

    {
        "id": 2,
        "type": "response",
        "to": 1,
        "failure": false,
        "status": 200,
        "params": {
            "timestamp": 1468501446711
        }
    }
