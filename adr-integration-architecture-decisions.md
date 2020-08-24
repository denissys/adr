Integration Architecture Decisions – APIs, Services, and Microservices
--------------------------------

Status
------
Draft 

Context
-------
Começando por microsserviços que está em maior evidência na composição de novas aplicações, como também ao reescrever parte das aplicaçÕes legadas, tornando-as num conjunto de microsserviços. 
Primeiramente, sabemos que os microsserviços são uma arquitetura de aplicação, não uma arquitetura de integração. No entanto, existem dois cenários em torno de microsserviços em que precisamos considerar a conectividade.

1. Conectividade interna da aplicação de microsserviço
Na arquitetura de microsserviço, teremos vários microsserviços trocando dados para compor a aplicação. Esses microsserviços precisam se comunicar uns aos outros. 
  - Em aplicação de silo, isso seria equivalente a chamar sub-rotinas. Não há necessidade de introduzir uma camada de API ou da aplicação de política para garantir a segurança neste cenário. A conectividade direta entre os microsserviços é tudo o que é necessário.
  

Decision
--------

Consequences
------------

Resources
---------

