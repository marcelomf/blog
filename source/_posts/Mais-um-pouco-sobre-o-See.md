---
title: Mais um pouco sobre o See
tags:
  - java
  - see
  - segurança
  - software livre
excerpt: ''
date: 2010-04-08 20:33:00
---

Quanto ao See, gostaria de fazer algumas considerações,  
  
Diferencia-se de demais projetos open source como frontends e utm's, por pretender:  
  
1 - Arquitetura microkernel que possibilite habilitar somente a administração dos serviços necessários, bem como atualização de features de maneira interrupta.  
2 - Ser distribuído, possibilitando inclusive a funcionalidade de proxy, de modo que um daemon possa gerenciar demais daemon's atrás de firewall's. Em uma dmz por exemplo os daemons do see não precisam ficar expostos para ninguém, dessa forma o acesso externo fica centralizado em um daemon e a utilização de aplicações de segurança como ids's e waf's(já que será em cima de webservice) podem ser direcionado apenas ao daemon central.  
3 - Oferecer flexibilidade para quem quiser trabalhar com regras de firewall diretas por exemplo.  
4 - Ser desenvolvido em cima de tecnologias atuais e de fácil entendimento como restful, possibilitando a fácil criação de diferentes frontend's, por diferentes players de infosec.  
5 - Gerencia centralizada.  
6 - Suporte a https.  
7 - Ser leve, com a utilização mínima de libs externas para viabilizar embarcação em routerboard por exemplo.  
  
Com certeza o mais complicado para mim foi conseguir fazer a tradução do firewall... quando bolei o esquema de template, foi maravilhoso, mas antes disso, gastei muito tempo com código porco cheio de if's e else's Oo.  
  
No exemplo abaixo, um firewall simples, que nem mesmo possui chains's customizadas(o see suporta):  
[https://sourceforge.net/projects/seeproject/files/network.xml/download](https://sourceforge.net/projects/seeproject/files/network.xml/download)  
  
Esse exemplo com 34 regras, gera 101 regras iptables! Lógico que a intenção não é criar regras de firewall em xml, mas o xml vai ser o artefato de comunicação com sistemas frontend que possibilitará a gerencia centralizada.  
  
\[\]s