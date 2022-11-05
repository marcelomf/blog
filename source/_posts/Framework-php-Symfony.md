---
title: Framework php ? Symfony!
tags:
  - arquitetura
  - coding
  - php
excerpt: ''
date: 2009-09-10 10:25:00
---

<!-- @page { margin: 2cm } P { margin-bottom: 0.21cm } -->

Utilizar framework's que agilizam e padronizam o desenvolvimento de código é uma ótima idéia! O que não quer dizer que seja fácil. Comecei utilizando o symfony como framework php, acredito ter feito uma ótima escolha, mas hoje enfrento algumas dificuldades que quero compartilhar com vocês:

1.  Um grande problema é querer usar tudo que o framework oferece sem entender a fundo a sua arquitetura, as vezes você chega em uma solução e mais pra frente descobre que o mesmo resultado poderia ser alcançado de maneira mais elegante. Portanto, sempre que você estiver diante de algo novo, além de pesquisar em listas de discussões e dar um googada, reúna todos os diagramas que você tem referente a arquitetura da framework e identifique as classes relacionadas ao seu problema, pegue a documentação da api e leia toda a documentação das classes identificadas.
    
2.  As vezes a api da framework não irá te atender e será necessário criar um novo método ou até mesmo classe que irá interagir diretamente com a arquitetura, nesses casos, releia a documentação e tenha a certeza de que a framework realmente não te atende :), caso ela realmente não te atenda, procure estender as classes da framework e codificar sua própria classe, documente bem toda a alteração e submeta a mesma ao projeto da sua framework(principalmente se o mesmo for open source). Lembre-se de garantir que em uma próxima versão da framework, as suas alterações irão funcionar perfeitamente.
    
3.  As vezes, os kras da sua framework decidem fazer alterações significativas na próxima versão da mesma e nesse caso é bom que você tenha um bom plano de ação para integrar as aplicações da versão anterior com a atual, acredite, se você quer utilizar framework's terceiras, é bom que você se preocupe com isso! Técnicas de roteamento e sandbox podem te ajudar bastante.
    
4.  Jamais utilize features da framework sem antes garantir a eficácia das mesmas, não é porque funcionou hoje que sempre irá funcionar! Sanitize todos os dados de entrada, garanta que sua framework faça isso! Esmiúce ao máximo todo o fluxo referente a controle de acesso, leia os fontes e faça muitos testes!
    

Agora que eu desabafei com vocês sobre minha experiência com o symfony, destaco que a versão 1.2 está com uma série de melhorias quanto a parte de form's com a utilização de object forms(+widget's, +validators), além da integração com o doctrine(orm que utiliza o PDO para abstração de acesso a dados e utilizando o padrão active records) nativa.