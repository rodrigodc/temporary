Especificação de mensagens: requisições
=======================================

Requisições devem ser enviadas à Plataforma Converja® como mensagens conforme descrito abaixo.


Envio
-----

Requisições devem ser enviadas como *mensagens privadas* para determinado membro de uma sala de conferência *XMPP*.

A sala de conferência e o membro para onde a mensagem deve ser enviada variam de acordo com requisição a ser feita. Os mesmos estão especificados na documentação de cada uma das requisições descritas neste documento.


Mensagem
--------

Uma requisição deve ser uma mensagem no formato *JSON* contendo um ``Object`` cujos campos descrevem o que está sendo solicitado:

 * ``id``: número único que identifica a requisição.
 * ``type``: o tipo de mensagem e deve sempre ser ``request``.
 * ``method``: o método descrito na documentação da requisição.
 * ``resource``: o recurso descrito na documentação da requisição.
 * ``params``: os parâmetros descritos na documentação da requisição.

O id da requisição pode ser qualquer número arbitrário desde que o mesmo número não seja utilizado em duas requisições distintas.

Por exemplo, a mensagem abaixo contém uma requisição cujo id é ``1``, o método é ``GET``, o recurso solicitado é ``/queues`` e sem nenhum parâmetro. Ela solicita que seja enviada resposta contendo a listagem de todas as filas de atendimento existentes:

.. code-block:: json

    {  
        "id": 1,
        "type": "request",
        "method": "GET",
        "resource": "/queues",
        "params": {}
    }
