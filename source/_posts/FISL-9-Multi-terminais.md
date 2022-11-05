---
title: 'FISL 9: Multi-terminais'
tags:
  - fisl
  - linux
excerpt: ''
date: 2008-04-22 17:29:00
---

Palestrante: Paulo Ricardo Zanoni e Luis Carlos Espen de Borna  
Considerações: Marcelo M. Fleury

Deu para se ter uma idéia dos problemas enfrentados pelos desenvolvedores do X que buscam o uso de multi-terminais, o palestrante fez um apanhado geral dos problemas enfrentados antigamente, dos encontrados hoje e no futuro e expôs que 2 de seus colegas que começaram como bolsistas na faculdade não puderam estar presente, pois estavam na califórnia em uma reunião de 50 pessoas com os desenvolvedores do X(sem nenhum custo para nenhum dos 2). Quanto aos problemas, foi exposto que antigamente o console não possuía a capacidade de se ter varias sessões X e que o X não era capaz de controlar mais de hardware(video/teclado/mouse), como solução posterior, foi apresentado a utilização de um X por console, mas que logo foi abolida e que a solução, seria então instanciar um X e a partir desse X, se istanciar outros X, e além disso, fazer com que cada X instanciado trate de maneira independente o seu hardware(video/teclado/mouse), com isso eles estão enfrentando problemas de escalonamento, logo, estão estudando uma maneira de se instanciar vários X através de um console, de forma independente.