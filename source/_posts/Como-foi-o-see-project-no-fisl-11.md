---
title: Como foi o see project no fisl 11
tags:
  - eventos
  - fisl
  - see
  - segurança
  - software livre
excerpt: ''
date: 2010-07-29 13:13:00
---

O Fisl como sempre é um evento para renovação, esse ano eu dividi quarto com os amigos Tulio Henrique e Otávio Calaça, revi e fiz também boas amizades.  
  
Infelizmente eu assisti pouquíssimas palestras, pois até o último momento eu estava codificando o see, por mais que eu atingisse o objetivo inicial, eu pensava: "Mas ainda da tempo de fazer isso aqui", haha e assim foi indo :), acredito que a apresentação foi bacana, fiquei bem mais tranquilo do que no flisol de Goiânia, tivemos algumas perguntas e de cara algumas idéias novas para o projeto.  
  
Existem 3 pessoas que eu gostaria de identificar, um que perguntou sobre a funcionalidade reverseFlow(justificando que a mesma não é legal, pois o ideal é tratar com state match na conntrack), sinceramente, não tenho estudo de casos o suficiente para decidir se em todas as situações, vale a pena fazer com que o iptables trabalhe como stateful, por isso a funcionalidade será mantida.  
[http://www.sns.ias.edu/~jns/wp/2006/01/12/iptables-connection-tracking-udp/](http://www.sns.ias.edu/%7Ejns/wp/2006/01/12/iptables-connection-tracking-udp/)  
[http://www.linuxtopia.org/Linux\_Firewall\_iptables/x1544.html](http://www.linuxtopia.org/Linux_Firewall_iptables/x1544.html%20)  
[http://www.iptel.org/sipalg/](http://www.iptel.org/sipalg/)  
  
Uma outra pessoa perguntou sobre o puppet e inclusive conversamos um pouco após a palestra, caso você leia esse post, favor se identificar :). E o outro perguntou se o projeto ira suportar configurações de cluster de firewall e como eu disse sim! Mas ainda não sei se irei utilizar o ucarp ou heartbeat por exemplo, quem puder dar um feedback das aplicações conntrackd(similar ao pfsync, proposta bem legal), vrrpd, heartbeat, ucarp, keepalived e OpenAIS, seria interessante. A ideia é que seja o mais simples possível, pois as configurações precisam ser geradas dinamicamente. Nesse sentido, gostei muito do ucarp, alguém tem alguma queixa ?  
  
È isso, muito obrigado aos que compareceram, vamos que vamos! :)  
  
Abaixo um vídeo de 7min demo do projeto:  
[http://www.youtube.com/watch?v=aQk7ZiMdi5Y](http://www.youtube.com/watch?v=aQk7ZiMdi5Y)  
  
Slides da palestra no FISL 11:  
[http://www.slideshare.net/marcelomf/see-project-segurana-em-cloud-computing-v2-fisl-11-2010](http://www.slideshare.net/marcelomf/see-project-segurana-em-cloud-computing-v2-fisl-11-2010)  
  
\[\]s