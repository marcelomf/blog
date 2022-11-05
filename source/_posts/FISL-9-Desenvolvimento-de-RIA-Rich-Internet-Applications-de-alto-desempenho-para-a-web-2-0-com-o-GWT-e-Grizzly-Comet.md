---
title: >-
  FISL 9: Desenvolvimento de RIA(Rich Internet Applications) de alto desempenho
  para a web 2.0 com o GWT e Grizzly Comet
tags:
  - fisl
  - java
excerpt: ''
date: 2008-04-22 17:30:00
---

Palestrante: Alexandre Gomes e Jean-Francois Arcand  
Considerações: Marcelo M. Fleury

Desenvolver utilizando Ajax se tornou algo comum, o gwt te prove uma interface na qual o desenvolver java não precisa saber html ou javascript, o desenvolver java precisa saber java! E é baseado nesse conceito que o GWT foi desenvolvido, a intenção é prover ao desenvolver java, classes e métodos que provem a web 2.0, sem que o mesmo saiba javascript ou html. Com a utilização demasiada de ajax em websites, novos problemas foram encontrados e novos conceitos baseados em velhos conceitos estão sendo aplicados. Normalmente, quando se quer atualizar um elemento html(div...) de tempos em tempos, o desenvolvedor precisa a cada X segundos realizar uma chamada ao servidor(GET/POST), o servidor então processa e responde ao browser, com a resposta ou simplesmente com um: “Ainda não possuo dados atualizados”, e esse é um problema, existe um trafego desnecessário na rede, um processamento desnecessário, pensando nisso, os caras do Grizzly Comet, Jette e outros servidores de aplicação, implementarão o conceito “Ajax Comet”, o esquema é: Usuário acessa aplicação, a aplicação precisa atualizar os dados de um elemento html(div...), a aplicação então, faz uma chamada ao servidor(GET/POST), o servidor verifica se existem dados a serem atualizados, se existe, o servidor responde com os dados e o browser atualiza o elemento MAS se não existem dados atuais o servidor instância uma thread para aquela requisição, processa a requisição, associa o buffer da requisição a buffer's similares(utlizando a java.nio), finaliza a thread(mas a conexão é mantida(wtf?!), você consegue manter mais de uma conexão em uma thread(java.nio!)) e quando houver dados a serem atualizados o servidor envia para a aplicação as solicitações pendentes! O massa mesmo, foi exatamente finalizar a thread, evitando assim um problema de escalonamento, normalmente, você teria que ter 1000 threads para 1000 usuários, com a utilização da java.nio por parte do servidor, isso não se faz necessário! Com certeza essa foi uma das palestras mais legais que eu assisti, até porque eu não conhecia o conceito de “Ajax comet”, lembrando que “Comet” pode ser utilizado em outras plataformas, andei pesquisando na WEB, mais sobre o assunto e achei um link bem maneiro:  
http://www.webtide.com/downloads/whitePaperWhyAjax.html