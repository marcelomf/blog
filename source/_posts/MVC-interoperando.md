---
title: MVC interoperando
tags:
  - arquitetura
  - coding
  - java
  - php
excerpt: ''
date: 2009-10-22 12:02:00
---

Tivemos uma thread esse mês sobre MVC sem SGBD's no DFJUG, como não tenho um link público, irei colar a minha opinião exposta lá:  
  
“Não tenho um SGBD, preciso de model ?”  
  
...  
  
Os arquivos são os seus dados....ou seja, seu banco de dados. Ai você pode ter os dto's que são a representação dos seus objetos abstrai-dos dos seus dados(seus arquivos) e o dao para acesso/persistência de dados, ou seja, o trabalho de parsing dos seus dados e talvez manipulação(ler os arquivos e alimentar dto's, talvez realizar uma regra de negocio a salvar no arquivo ou em outro... depende do que você quer). Logo, você tem sim um model... se você quiser né... você é livre para escolher a arquitetura que melhor te atende.  
  
O que vai determinar se sua aplicação é em MVC, é a independência das camadas e o fluxo dos dados... vamos supor que agora os seus arquivos são xml's e não txt... pois bem, você deve alterar somente o seu model e a aplicação deve continuar funcionando normalmente.  
  
Agora você quer um view em jsf ou flex, sendo que antes era jsp... blz, agora você deve alterar somente o seu view e a aplicação deve continuar funcionando normalmente.  
  
E o seu controller ? Deve ser capaz de fazer o que cujo dito acima. Mas vamos supor que agora você quer tirar o sistema da WEB e fazer ele rodar no console ou com swing, então você vai ter que alterar o seu view e o seu controle, mas o model, você pode reutilizar sem drama nenhum...  
  
Com relação a distribuição de pacotes e classes, isso vai depender do tamanho do projeto, do que você quer com ele, particularmente eu não conheço nenhuma regra pra isso envolvendo mvc... acredito que o importante mesmo é o fluxo dos dados ser correto e existir essa certa independência entre camadas, mesmo que o controller esteja "mais preso" ao view...  
  
Para saber mais:  
[http://java.sun.com/blueprints/patterns/MVC-detailed.html](http://java.sun.com/blueprints/patterns/MVC-detailed.html)  
[http://www.moock.org/lectures/mvc/](http://www.moock.org/lectures/mvc/)  
[http://en.wikipedia.org/wiki/Model-view-controller](http://en.wikipedia.org/wiki/Model-view-controller)  
  
Grande parte das framework's MVC's pecam por não interoperar entre arquiteturas/linguagens. Acredito que a arquitetura MVC em si seja legal, mas as implementações da mesma deixam a desejar. O controller deve ser reaproveitado para diferentes arquiteturas/linguagens, a renderização do resultado do model, realizada pelo controller, deve ser reaproveitada em diferentes view's. É necessário que o controller seja totalmente desacoplado do VIEW. Para fazer isso de maneira interoperável, penso na seguinte solução:  
  
Model → ORM(EJB3, Doctrine, Propel, etc).  
Controller → REST(Assim eu consigo interoperar e estabelecer uma comunicação simples com o VIEW)  
VIEW → XHtml, JavaScript, ActionScript(Flex).  
  
Dessa forma, eu consigo inclusive desenvolver webservice's embarcados, com frontend's distintos.  Hoje, se juntarmos pedaços de framework's, conseguimos implementar facilmente uma arquitetura similar a exposta, mas precisamos mais do que isso... precisamos que códigos sejam gerados... trabalho de maquina, deve ser feito por maquina, o designer deve fazer designer e o desenvolvedor deve codificar negócios e ou arquitetura. Particularmente eu desconheço uma framework que gere código em cima dessa arquitetura, grande abraço a todos!