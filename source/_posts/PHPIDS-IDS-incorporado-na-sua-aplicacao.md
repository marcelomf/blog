---
title: PHPIDS - IDS incorporado na sua aplicação
tags:
  - arquitetura
  - coding
  - ids/ips
  - php
  - segurança
excerpt: ''
date: 2009-09-11 09:46:00
---

<!-- @page { margin: 2cm } P { margin-bottom: 0.21cm } A:link { so-language: zxx } -->  

Quero compartilhar com vocês um projeto que conheci através do colega Wagner Elias, chama-se PHPIDS, através de assinaturas que utilizam expressões regulares você cria filtros que tem o objetivo de detectar ataques que exploram a falta de tratamento na entrada de dados, como iSQL, XSS(para + veja owasp). O legal é que conseguindo diminuir os falsos positivos, você pode por exemplo integrar o phpids a sua camada de controle e fazer com que o mesmo funcione como um IPS.  

Outro fato importante é que você aproxima a segurança da equipe de desenvolvimento e que a segurança fica incorporada a sua aplicação e não ao seu servidor de aplicação e ou protocolo de comunicação(http), como no caso de se usar o mod\_security do apache para WAF, mesmo que com proxy reverso você consiga fazer o filtro em um ambiente destinto da aplicação e até mesmo de outros servidores de aplicação que não o apache, mas é importante lembrar que com o mod\_security o tratamento se restringe a tráfego http que você acaba criando mais um vetor de ataque(alá falhas do mod\_proxy), além de que com mod\_security, normalmente a configuração do mesmo fica atrelada a equipe de infra e não a de desenvolvimento.  

Gostei muito do projeto, gostaria de saber se existe algum semelhante em java e o mais legal, seria poder compartilhar regras entre os mais diversos IDS's, para evitar retrabalho... desconheço um projeto que se preocupe com a interoperabilidade de regras entre IDS's.  

O Wagner Elias vai palestrar sobre o phpids na PHPConference 2009, inclusive, levantando a possibilidade de integrar o mesmo ao memcached, evitando ou minimizando assim o overhead.  

Abaixo um filtro do PHPIDS:

<filter>  
<id>44</id>  
<rule>  
(?:\\d"\\s+"\\s+\\d)|(?:^admin\\s\*"|(\\/\\\*)+"+\\s?(?:--|#|\\/\\\*|{)?)|(?:"\\s\*or\[\\w\\s-\]+\\s\*\[+<>=(),-\]\\s\*\[\\d"\])|(?:"\\s\*\[^\\w\\s\]?=\\s\*")|(?:"\\W\*\[+=\]+\\W\*")|(?:"\\s\*\[!=|\]\[\\d\\s!=+-\]+.\*\["(\].\*$)|(?:"\\s\*\[!=|\]\[\\d\\s!=\]+.\*\\d+$)|(?:"\\s\*like\\W+\[\\w"(\])|(?:\\sis\\s\*0\\W)|(?:where\\s\[\\s\\w\\.,-\]+\\s=)|(?:"\[<>~\]+")  
</rule>  
<description>  
Detects basic SQL authentication bypass attempts 1/3  
</description>  
<tags>  
<tag>sqli</tag>  
<tag>id</tag>  
<tag>lfi</tag>  
</tags>  
<impact>7</impact>  
</filter>  
  
Para saber mais:  

[http://php-ids.org/faq/](http://php-ids.org/faq/)