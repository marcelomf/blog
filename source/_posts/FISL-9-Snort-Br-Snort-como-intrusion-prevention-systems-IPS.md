---
title: 'FISL 9: [Snort-Br] Snort como intrusion prevention systems(IPS)'
tags:
  - fisl
  - ids/ips
  - segurança
excerpt: ''
date: 2008-04-22 18:47:00
---

Palestrante: Rodrigo Montoro aka Spooker  
Considerações: Marcelo M. Fleury  

Foi-se apresentando o snort de uma maneira geral(sistema que baseado em assinaturas, consegue detectar ataques de rede/host), mostrou-se algumas topologias para o uso do snort(basicamente atrás do firewall ou ná frente) e explicou-se o seu funcionamento. Posteriormente, foi falado da integração do snort com alguns modulos auxiliares(fwsam, snort inline e snort inline(inlianiac)) que além de detectar conseguem bloquear ataques utilizando o iptables, a um tempo atrás(2002+-) eu utilizei o guardian para isso, de qualquer forma o guardian deve estar obsoleto pois o mesmo nem foi citado na palestra. Algo que foi legal tomar conhecimento é que com o ip\_queue ou nfqueue habilitado(normal/smp), o netfilter consegue enviar pacotes pre-estabelecidos para o userspace, e utilizando o snort\_inline(inliniac), você consegue capturar os pacotes e assim baseado em alguma assinatura você pode logar, dropar ou rejeitar o mesmo.