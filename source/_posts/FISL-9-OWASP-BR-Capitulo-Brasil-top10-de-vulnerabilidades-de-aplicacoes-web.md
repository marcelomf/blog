---
title: 'FISL 9: OWASP-BR - Capitulo Brasil top10 de vulnerabilidades de aplicações web'
tags:
  - fisl
  - java
  - metodologia
  - php
  - segurança
  - software livre
excerpt: ''
date: 2008-05-01 21:40:00
---

Palestrante: Marcos Aurelio e Leonardo Cavallari  
Considerações: Marcelo M. Fleury

Palestra bastante esclarecedora sobre as 10+ vulnerabilidades de aplicações web(vide OWASP), pra quem não conhece, a OWASP é uma comunidade livre que tem como objetivo principal documentar as maneiras de se explorar aplicações, bem como se prevenir, dês de uma simples filtragem de um input até à implementação de uma metodologia de desenvolvimento seguro(CLASP). A palestra abordou todas as 10 falhas(xss, sql injection, csrf...), e eu ganhei o livro owasp clasp 1.2, por comentar sobre a utilização de checksum para identificar registros em uma tabela(ao invés de se usar ?codigo=NUMERO\_OU\_NUMERO\_ALEATORIO, usar: ?codigo=hash) e comentar que segurança no brasil é de baixo para cima e que o investimento em mão de obra qualificada é apreciado por uma minoria! Mas, fiquei feliz de ter ganhado o livro, hehe. No final tive uma conversa com o Marcos Aurelio, sobre alguns aspectos éticos... do tipo, é ético um sistema de uma empresa estar vulnerável, e os seus usuários não terem o conhecimento de tal vulnerabilidade ? É ético uma empresa, mesmo ciente que sua aplicação esta vulnerável, não tomar medidas para corrigir a mesma ? Então, diante dessas perguntas, porque não é ético que pessoas providas do conhecimento da vulnerabilidade, e após alertar a empresa, a mesma não se pronunciar, nem mesmo corrigir a sua aplicação, essas pessoas então, divulgam a falha, dando maior visibilidade ao problema e conseqüentemente tendo a atenção da empresa, e por fim o problema é corrigido... porque essas pessoas não são éticas ? Eu nunca soltei nenhuma falha encontrada por mim em alguma mail-list ou qualquer tipo de canal publico, mas confesso que diversas vezes isso me passou pela cabeça! E não tenho nada contra quem o faz! Enfim, quando eu acabar os resumos do fisl, eu alongo esse tema em outro post, abraços!