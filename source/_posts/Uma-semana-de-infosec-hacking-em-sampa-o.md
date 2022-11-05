---
title: Uma semana de infosec/hacking em sampa o/
tags:
  - arquitetura
  - eventos
  - see
  - segurança
excerpt: ''
date: 2010-05-21 11:37:00
---

Depois de uma semana vivendo infosec/hacking em sampa, eu realmente pude entender muitas coisas! Não só tecnicamente, mas de um ponto de vista social, econômico e comportamental. Esperava mais tecnicamente do GTS, mas no geral foi legal! No GTER, tivemos palestras sobre BGP, Fibre Channel, IPV6 e outras... também foi legal.

  

Mais na boa ? YSTS – You Sh0t The Sheriff foi muito bom! Com certeza está na minha lista de eventos mais esperados do ano! Os kras conseguem reunir geral da infosec! Realmente trata-se de um evento diferenciado, palestras com alto nível técnico, diversas pessoas, altas discussões interessantes, networking, poutz, conheci uma galera pessoalmente, neguinho que eu trocava ideia em 2000/2001 no irc! Muito legal mesmo.

  

Só tenho a agradecer a todos que me receberam super bem, realmente me senti a vontade com os senhores :). Um plus a mais com certeza foram as operações aurora haha, muito maneiro!

  

Agora é continuar desenvolvendo o seeproject, pesquisar algumas coisas legais para submeter para a h2hc e ver o que rola! Tenho um compromisso a ser honrado e pode parecer besteira para alguns, mas não faço esse projeto pelo dinheiro... quero dinheiro, mas o tesão de poder lidar com infosec dia a dia, fazer o que eu gosto porque simplesmente gosto... poutz, isso sim é bom :), só tenho a agradecer a todas as pessoas que estão me ajudando a incentivando, vamos que vamos!

  

Conversando com o Rodrigo Rubira e posteriormente com o Nelson Murilo, quanto a questão de que em determinados momentos a aplicação terá que ser root, mas que eu não iria botar ela para rodar como root e não gostaria de depender do sudoers ou selinux(nesse caso, poderia limitar até mesmo o poder do root frente a aplicação, mas vale ler sobre kernel hacking), foi exposto que atualmente esse problema é sanado de 2 maneiras:

  

Subir como root e dropar privilégios... por exemplo, a main thread é root, mas as demais não... o apache faz isso:

  

root@mmf-synack:~# ps aux | grep apache

root 4052 0.7 0.3 201924 11404 ? Ss 10:24 0:00 /usr/sbin/apache2 -k start

www-data 4057 0.0 0.2 201924 6184 ? S 10:24 0:00 /usr/sbin/apache2 -k start

www-data 4058 0.0 0.2 201924 6184 ? S 10:24 0:00 /usr/sbin/apache2 -k start

www-data 4059 0.0 0.2 201924 6184 ? S 10:24 0:00 /usr/sbin/apache2 -k start

www-data 4060 0.0 0.2 201924 6184 ? S 10:24 0:00 /usr/sbin/apache2 -k start

www-data 4061 0.0 0.2 201924 6184 ? S 10:24 0:00 /usr/sbin/apache2 -k start

  

Ou subir como usuário comum o processo main(no caso do see, o processo que irá receber requisições remotas) e demais partes da aplicação iria subir como root, achei essa abordagem a mais interessante! Tks Rodrigo e Nelson! O legal nesse caso é que como estou arquitetando a aplicação pensando em algumas questões como atualização parcial que não comprometa os demais serviços, requisito este já previsto no brainstorm inicial, essa abordagem encaixou como uma luva! Como o middleware está sendo desenvolvido em java, na hora eu pensei em utilizar RMI(apenas localhost) para realizar a comunicação entre processos(IPC)! Se alguém tiver uma sugestão mais interessante, favor compartilhar.

  

Devido a essa alteração significativa na arquitetura, o lançamento da RC1, foi adiado para 28/06. Conversando com alguns amigos, resolvi lançar o projeto utilizando o que conheço de melhor para o mesmo, isso irá evitar possíveis frustrações e principalmente retrabalho. De qualquer maneira, no dia 24/05, lançarei o wiki e scv públicos e talvez o site. 

  

É isso, parabéns ao Willian Caprino, Nelson Murilo e Luiz Eduardo, o YSTS é do kralho! :), foi um prazer conhecer pessoalmente a galera: Leandro Rocha, Leandro Neves, Filipe Balestra, Wagner Elias, Alan, Alex, Clebeer, Nelson Murilo, Willian Caprino, Luiz Eduardo, Nelson Brito, Bonagura, Bordini, Carol Bozza, Vugo, Julio Fort, Julio Auto, Anchises, Sergio Dias, Marlon Borba, Alex Kirk, Jespinhara, Bruno Oliveira, Tony Rodrigues, Denerval(Barata Elétrica) e rever os amigos Rodrigo Montoro, Rodrigo Rubira, IP\_FIX, Montanaro e Dum\_Dum(podia fazer um stand up hacking :), cheio de mensagens subliminares :))

  

Tks! :).