---
title: PEV peres
tags:
  - c
  - segurança
  - software livre
excerpt: ''
date: 2012-12-30 08:25:00
---

Quem testou o POC do peres, aproveite para testar a nova versão(quem não testou nada, manda bala ai o/):

  
git clone git@github.com:marcelomf/pev.git  
  
cd pev/src; make peres; ./peres -h  
  
$ ./peres -h  
Usage: peres OPTIONS FILE  
Show information about resource section and extract it  
  
Example: peres -a putty.exe  
  
Options:  
 -a, --all                     Show all information, statistics and extract resources  
 -x, --extract              Extract resources  
 -i, --info                    Show informations  
 -s, --statistics          Show statistics  
 -v, --version              Show version and exit  
 --help                       Show this help and exit

Detalhe para a o NODE\_PERES que facilita muito o manuseio dos resources.

  

Da para adicionar muitas opções, mas eu não devo faze-lo por enquanto. Quanto ao peres, quero agora corrigir bugs que surgirem, talvez alguma melhoria no discoveryNodePeres() e também warnings de compilação, no mais, quero começar a brincar com o pesec.

Este é o primeiro e último post de 2012 ;), em 2013 acredito que irei postar bastante por aqui! Aos poucos estou estudando e fazendo mais as coisas que eu gosto, o que com certeza irá render posts legais.  
  
Abraços e feliz ano novo para todos!