Definição de Conectividade para APIs, Services, and Microservices
--------------------------------

Status
------
Draft 

Context
-------
Começando por microsserviços que está em maior evidência na composição de novas aplicações, como também ao reescrever parte de uma aplicação legada (monolito) tornando-as num conjunto de microsserviços. Primeiramente, sabemos que os microsserviços são uma arquitetura de aplicação, não uma arquitetura de integração. No entanto, existem dois cenários em torno de microsserviços em que precisamos considerar a conectividade.

Decision
--------

*Cenário 1. Conectividade interna da aplicação de microsserviço (Call-Method)*

  Na arquitetura de microsserviço, teremos vários microsserviços trocando dados para compor a aplicação. Esses microsserviços precisam se comunicar uns aos outros. 
  - Em aplicação de silo, isso seria equivalente a chamar sub-rotinas. Não há necessidade de introduzir uma camada de API ou da aplicação de política para garantir a segurança neste cenário. A conectividade direta entre os microsserviços é tudo o que é necessário.
  
*Cenário 2. Conectividade entre microsserviços separados*

  Com várias aplicações de microsserviço separados que precisam chamar uns aos outros. Nesse caso, adicionar APIs e um Gateway para gerenciar essa conectividade e fornecer governança e políticas de segurança, o Gateway deve fornecer a conectividade entre microsserviços, como também para aplicações de front-end. O Gateway é responsável por separar a camada de responsabilidade que realiza a governança e a segurança dos microserviços.

Consequences
------------
Ao utilizar a arquitetura de *Conectividade entre microsserviços separados (Cenário 2)* sem a utilização de um Gateway, isso implica em:
  - Excesso de responsabilidade na arquiteutra de aplicação do microserviço, pois ele deverá garantir as políticas de segurança e de governança dos consumers, tornando o microserviço com excesso de responsabilidade em sua arquitetura de aplicação;
  - Se o microserviço for exposto como API de forma pública (como para o consumo de uma aplicação front-end), o não uso de um Gateway implica em falhas de segurança como falta de definição de autentiticação (ou autenticação fraca / sem governança), falta de governança sobre os consumers (um microserviço pode servir um ou mais consumers).
