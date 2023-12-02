---
layout: title
title: DDD com NestJS
date: 2023-12-02 11:16:46
tags:
---
Ano passado publiquei no meu github um exemplo de app utilizando:
DDD, SOLID, CLEAN, TDD, DTO, DAO, ORM, RESTFUL com typescript, fastify e prisma.
https://github.com/marcelomf/treino-ddd

Agora publiquei o mesmo projeto só que utilizando NestJS:
https://github.com/marcelomf/treino-ddd-nestjs

O bacana é que só foi necessário alterar as rotas, controllers e services para a realidade no NestJS, o resto deu para reaproveitar tudo(DDD é show!).

É bem curioso como o NestJS lembra spring boot/java.

Da uma olhada:
https://github.com/marcelomf/treino-ddd-nestjs/blob/main/src/main.ts
https://github.com/marcelomf/treino-ddd-nestjs/blob/main/src/app.module.ts
https://github.com/marcelomf/treino-ddd-nestjs/blob/main/src/controllers/sales/customer.ts
https://github.com/marcelomf/treino-ddd-nestjs/blob/main/src/services/sales/customer.ts