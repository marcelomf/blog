---
title: See Project - Gerador de regras em iptables
tags:
  - see
  - segurança
  - software livre
excerpt: ''
date: 2010-04-10 09:25:00
---

Algumas pessoas estão com dificuldades para testar o projeto, segue o shellscript abaixo para testar:  
  
#!/bin/bash  
wget http://cdnetworks-us-1.dl.sourceforge.net/project/seeproject/network.xml && wget http://cdnetworks-us-1.dl.sourceforge.net/project/seeproject/see.jar && wget http://cdnetworks-us-1.dl.sourceforge.net/project/seeproject/firewall.xml && wget http://cdnetworks-us-1.dl.sourceforge.net/project/seeproject/see  
mkdir data; mv network.xml data/; mv firewall.xml data/  
echo -e "\\n\\nNetwork e regras do firewal em SLF:\\n"  
cat data/network.xml  
cat data/firewall.xml  
sleep 10  
echo -e "\\n\\nRegras do firewall geradas em iptables:\\n\\n"  
./see -f  
  
  
cole em um editor de texto, salve e dê chmod 755 nomescript.sh; sh nomescript.sh  
  
\[\]s