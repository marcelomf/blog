---
title: Framework benchmark!
tags: []
excerpt: ''
date: 2018-04-25 14:26:00
---

  

  

Existem vários fatores para se escolher uma linguagem/framework para determinado projeto, como eu sempre gostei de conhecer tecnologias novas, nunca fui muito preso a uma ou outra linguagem/framework. Pensando em produtividade, performance e “elegância” resolvi fazer benchmark das seguintes tecnologias: GO/gorm+echo GO/xorm+echo NodeJS/express NodeJS/graojs NodeJS/loopback PHP/phalcon PHP/Lumen PHP/Smfony 4 Ruby/Rails API 5 Python/Flask Java/Spring A ideia era criar um RESTful de uma entidade simples(usuarios) utilizando ORM, para isso em cada linguagem foi criado as seguintes operações: GET /usuarios → Retorna todos os usuários do db. POST /usuarios → Cria um usuário no db. PUT /usuarios/{id} → Atualiza um usuário no db. DELETE /usuarios/{id} → Deleta um usuário no db. Em todas as frameworks o bd utilizado foi o mysql, com exceção do graojs que utilizei mongodb. Para realizar os testes de performance foi utilizado a ferramente bombardier que inclusive é escrito em GO. Abaixo o repositório com os resultados e códigos: [https://github.com/marcelomf/restful-orm](https://github.com/marcelomf/restful-orm)\* Questões de segurança não foram levadas em consideração.