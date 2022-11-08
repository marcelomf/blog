---
title: Do php estruturado ao RAD com symfony
tags:
  - php
excerpt: ''
date: 2008-02-25 00:30:00
---

Comecei a trabalhar como desenvolvedor em meados de 2006, no inicio, tudo era novo e passivo de ser melhorado(não que hoje não seja), isso me motivava e fazia com que eu aprendesse mais e mais! Falando especificamente em PHP, eu comecei desenvolvendo da forma mais procedural possível... no máximo um funcoes.php no qual eu tinha funções para conectar aos BD's, tirar acentos, validar input's, dentre outras... formulários com tabelas e sem nenhum CSS, estrutura de diretórios bizarra, nomeclatura de arquivos, idem! Arquivos de relatórios cheios de sql's... No final de 2006, programar já não era algo novo e empolgante, estava caindo em uma rotina de crud's chatos, manutenção de sistemas antigos e consequentemente, perdendo-me pela falta de padronização em meio a tantos sistemas e códigos, era hora de mudar!  
  
Passei a aprender orientação a objetos, design patterns, ajax, tableless... comecei com css, queria entender como aquilo funcionava e passar o conhecimento adquirido para o designer da empresa onde trabalho, assim, acreditava que iria ficar livre de formulários, algo que sempre me entediou, além é claro de aderir a modinha "tableless", confesso que no inicio foi bem chato, mas no final foi bom, consigo um designer legal, usando códigos \\o/... quanto mais eu aprendia, mais eu me convencia de que era o designer que tinha que manjar aquilo... falava isso para o meu colega e ele: "isso é código, não vejo imagem nenhuma ai...", haha quem diria... hoje o garoto vê no css uma maneira rápida e fácil de desenvolver os seus layouts :), na mesma época estava aprendendo ajax... o tal das informações assíncronas, comecei aprendendo o DOM cruzão até a utilização da jquery, buscando sempre um maior nível de produtividade... afinal, produzir mais rápido, me garantia mais moral para investir em novos estudos dentro da empresa e assim garantindo o padrão de auto-motivação exigido por mim.  
  
Comecei a desenvolver utilizando classes... era simples, eu tinha uma classe de conexão e outras para cada modulo do sistema... tinha os seus atributos e métodos CRUD, alem das regras de negocio, passei a utilizar o PEAR:DB para abstração de base dados, que mais tarde viraria MDB2, juntamente com classes auxiliares, para criação de grid's e outros, eu achava as coisas meio zoneadas ainda, não sabia ao certo o que era o certo, mas sabia que aquilo não me satisfazia, precisava de maior organização/padronização, comecei a aprender MVC e a ler alguns artigos sobre templates(smarty/fasttemplates), em paralelo ouvia os estrondos de RubyOnRails e Python... pensava eu: "Chega de perder tempo com CRUD(no model), form's e grid's, quero scaffolding também!", comecei a criar um projeto para realizar o scaffolding, mas logo vi que compensava mais aderir a algo existente, lá vou eu a procura de framework's PHP, qual seria a melhor ?  
  
Eu Tinha 3 objetivos, não perder tempo com coisas repetitivas e ter um nível de segurança/perfomace aceitável! Comecei estudando a framework da zend, li alguns artigos, mas via que não era o que eu realmente queria... para esclarecer: Buscava algo que seguisse o padrão MVC/tableless, fizesse eu ganhar tempo com os CRUD's, comunidade forte e que finalmente me desse TOTAL controle do que fosse gerado, enfim, passei a utilizar o symfony como framework, no inicio foi ou melhor, está sendo "canseira" em alguns momentos eu tenho que rê-aprender coisas básicas que antes eu não tinha a menor duvida, como popular um select a partir de outro select usando ajax... mas não da maneira antiga com a jquery e sim usando o que o symfony chama de AjaxHelper's(prototype)... haha, caso eu não aprendesse, o symfony tinha total integração com a jquery, o que ainda não foi necessário usufruir... aprender sobre os generators, MRO\->creole, criteria, etc... o que eu posso garantir é que a cada novo aprendizado eu vejo como eu e a empresa podemos ganhar... já vi muitas criticas sobre desenvolvimento RAD, por favor, seja imparcial, deixe suas classes particulares e busque conhecer o symfony de verdade antes de critica lo. Tenho vários amigos que procuram fazer o que o symfony faz e eu não entendo o porque, mas eles insistem que o projeto deles é melhor... não estou desmerecendo o trabalho de ninguém, mas sejamos sensatos, qual a chance de um projeto pessoal de uma só pessoa ser melhor do que um projeto livre e desenvolvido por dezena de milhares delas ?  
  
É isso, convido a todos a conhecer o symfony(www.symfony\-project.org), apenas não pense que o symfony irá gerar sistemas, ele gera códigos, o sistema mesmo, continua sendo o desenvolvedor quem o faz :), todo esse papo me deu a idéia de um post, em meados de abril/maio, irei postar um artigo explicando do estruturado, passando pelo MVC c/ O.O. ao frameworkzado(symfonyzado xD), veremos na pratica os prós e contras :), abraços e até a próxima!