Protocolos, formatos e padrões utilizados
=========================================

Toda interação com a *API* da Plataforma Converja® é realizada por meio do protocolo `XMPP <https://xmpp.org/>`_.

O protocolo XMPP é um protocolo aberto e padronizado (`RFC 3920 <https://xmpp.org/rfcs/rfc3920.txt>`_ e `outras <https://xmpp.org/rfcs/>`_) que propicia nativamente tanto o envio como o recebimento de mensagens em *tempo real*. Tal característica é adequada para sistemas de telecomunicações como a Plataforma Converja®, onde eventos podem ocorrer a qualquer momento e de modo assíncrono.

A Plataforma Converja® faz uso de *salas de conferência* XMPP (`XEP 0045 <http://xmpp.org/extensions/xep-0045.html>`_) e de seus *membros* como entidades centrais para a comunicação com a plataforma por meio de sua *API*. A comunicação é feita pelo envio de mensagens para aquelas entidades bem como pelo recebimento de mensagens enviadas por elas.

As mensagens enviadas e recebidas são codificadas no formato `JSON <http://json.org/>`_, que é um formato aberto e padronizado (`RFC 4627 <https://www.ietf.org/rfc/rfc4627.txt>`_) para troca de mensagens entre sistemas computacionais de modo simples e portável.
