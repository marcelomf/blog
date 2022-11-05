---
title: Debugging
tags: []
excerpt: >-
  <span id="docs-internal-guid-9113a8f6-7fff-f99b-75da-2d69ccc2be43"><p
  dir="ltr" style="line-height: 1.38; margin-bottom: 0pt; margin-top:
  0pt;"><span style="font-family: Arial; font-size: 11pt;
  font-variant-east-asian: normal; font-variant-numeric: normal; vertical-align:
  baseline; white-space: pre-wrap;">Debugging é simplesmente a técnica mais
  importante para encontrar e resolver problemas na computação. O mais
  importante em um processo de debugging é ter e afirmar a todo o momento o
  sentimento de que não existem falhas sem explicação. Se você não está
  encontrando o erro, então sinto dizer que trata-se de uma falha sua e não do
  sistema. Este sentimento de desafio a ser vencido é o que motiva todos os dias
  os hackers. Um hacker não admite não entender algo, não admite se ver
  impotente diante de uma dada situação.</span></p><br /><p dir="ltr"
  style="line-height: 1.38; margin-bottom: 0pt; margin-top: 0pt;"><span
  style="font-family: Arial; font-size: 11pt; font-variant-east-asian: normal;
  font-variant-numeric: normal; vertical-align: baseline; white-space:
  pre-wrap;">A verdade é que poucos administradores de sistemas e
  desenvolvedores possuem essa "veia hacker", nem todos estão dispostos a
  trabalhar em madrugadas, às vezes sacrificando sua vida social, por puramente
  vencer um desafio técnico. Hackers não necessariamente não trabalham em
  equipe, mas o declínio de uma equipe ou profissional em fornecer uma ajuda,
  jamais é motivo relevante para ele desistir da "causa".</span></p><br /><p
  dir="ltr" style="line-height: 1.38; margin-bottom: 0pt; margin-top:
  0pt;"><span style="font-family: Arial; font-size: 11pt;
  font-variant-east-asian: normal; font-variant-numeric: normal; vertical-align:
  baseline; white-space: pre-wrap;">Diante de um erro, precisamos ver o problema
  não só de forma linear, entendendo </span><span style="font-family: Arial;
  font-size: 11pt; white-space: pre-wrap;">que o ponto em que estamos analisando
  é só um ponto de diversos outros que </span><span style="font-family: Arial;
  font-size: 11pt; white-space: pre-wrap;">podem conter ou explicar o erro. É
  preciso definir uma estratégia de análise e ter em </span><span
  style="font-family: Arial; font-size: 11pt; white-space: pre-wrap;">mente que
  às vezes você precisa rever toda a sua estratégia, pois não muito raro,
  </span><span style="font-family: Arial; font-size: 11pt; white-space:
  pre-wrap;">vamos de encontro a diversos "insights exponenciais", ou seja, que
  nada tem a ver </span><span style="font-family: Arial; font-size: 11pt;
  white-space: pre-wrap;">com a estratégia corrente. Entende-se então que
  debugging em si é linear(lógico/objetivo), mas que a definição da estratégia é
  exponencial(imaginação/subjetivo).</span></p><br /><p dir="ltr"
  style="line-height: 1.38; margin-bottom: 0pt; margin-top: 0pt;"><span
  style="font-family: Arial; font-size: 11pt; font-variant-east-asian: normal;
  font-variant-numeric: normal; vertical-align: baseline; white-space:
  pre-wrap;">Aplicando o teorema de pareto, seria justo afirmar que em situações
  complexas seria válido investir 80% do tempo na estratégia e 20% em código e
  ou configurações de sistema.&nbsp;</span></p><br /><p dir="ltr"
  style="line-height: 1.38; margin-bottom: 0pt; margin-top: 0pt;"><span
  style="font-family: Arial; font-size: 11pt; font-variant-east-asian: normal;
  font-variant-numeric: normal; vertical-align: baseline; white-space:
  pre-wrap;">Um exemplo é quando em uma infra-estrutura de balanceamento de
  carga apresenta algum problema, este problema pode ser no seu código, de infra
  física ou lógica, podendo ainda ser algum erro na sua framework, biblioteca
  utilizada, no seu servidor de aplicação ou mesmo no seu sistema operacional.
  Isso infere que uma pessoa para realizar um debugging completo, deve entender
  de todas as tecnologia envolvidas e não se conformar jamais com "eu não sei
  fazer isso" ou "isso não é minha responsabilidade".</span></p><br /><p
  dir="ltr" style="line-height: 1.38; margin-bottom: 0pt; margin-top:
  0pt;"><span style="font-family: Arial; font-size: 11pt;
  font-variant-east-asian: normal; font-variant-numeric: normal; vertical-align:
  baseline; white-space: pre-wrap;">"If debugging is the process of removing
  bugs, then programming must be</span></p><p dir="ltr" style="line-height:
  1.38; margin-bottom: 0pt; margin-top: 0pt;"><span style="font-family: Arial;
  font-size: 11pt; font-variant-east-asian: normal; font-variant-numeric:
  normal; vertical-align: baseline; white-space: pre-wrap;">the process of
  putting them in."Por Edsger Dijkstra</span>&nbsp;</p></span>
date: 2022-10-10 13:00:00
---

Debugging é simplesmente a técnica mais importante para encontrar e resolver problemas na computação. O mais importante em um processo de debugging é ter e afirmar a todo o momento o sentimento de que não existem falhas sem explicação. Se você não está encontrando o erro, então sinto dizer que trata-se de uma falha sua e não do sistema. Este sentimento de desafio a ser vencido é o que motiva todos os dias os hackers. Um hacker não admite não entender algo, não admite se ver impotente diante de uma dada situação.

  

A verdade é que poucos administradores de sistemas e desenvolvedores possuem essa "veia hacker", nem todos estão dispostos a trabalhar em madrugadas, às vezes sacrificando sua vida social, por puramente vencer um desafio técnico. Hackers não necessariamente não trabalham em equipe, mas o declínio de uma equipe ou profissional em fornecer uma ajuda, jamais é motivo relevante para ele desistir da "causa".

  

Diante de um erro, precisamos ver o problema não só de forma linear, entendendo que o ponto em que estamos analisando é só um ponto de diversos outros que podem conter ou explicar o erro. É preciso definir uma estratégia de análise e ter em mente que às vezes você precisa rever toda a sua estratégia, pois não muito raro, vamos de encontro a diversos "insights exponenciais", ou seja, que nada tem a ver com a estratégia corrente. Entende-se então que debugging em si é linear(lógico/objetivo), mas que a definição da estratégia é exponencial(imaginação/subjetivo).

  

Aplicando o teorema de pareto, seria justo afirmar que em situações complexas seria válido investir 80% do tempo na estratégia e 20% em código e ou configurações de sistema. 

  

Um exemplo é quando em uma infra-estrutura de balanceamento de carga apresenta algum problema, este problema pode ser no seu código, de infra física ou lógica, podendo ainda ser algum erro na sua framework, biblioteca utilizada, no seu servidor de aplicação ou mesmo no seu sistema operacional. Isso infere que uma pessoa para realizar um debugging completo, deve entender de todas as tecnologia envolvidas e não se conformar jamais com "eu não sei fazer isso" ou "isso não é minha responsabilidade".

  

"If debugging is the process of removing bugs, then programming must be

the process of putting them in."Por Edsger Dijkstra
<!-- more -->
