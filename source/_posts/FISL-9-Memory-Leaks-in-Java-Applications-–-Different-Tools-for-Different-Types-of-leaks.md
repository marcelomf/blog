---
title: >-
  FISL 9: Memory Leaks in Java Applications – Different Tools for Different
  Types of leaks
tags:
  - fisl
  - java
excerpt: ''
date: 2008-04-22 17:45:00
---

Palestrante: Kristen Accardi  
Considerações: Marcelo M. Fleury

No inicio o palestrante deu um apanhado geral dos problemas que podem ocorrer com a má utilização de memória, que acabam por lançar exceções do tipo “Out of memory for java heap space” , falou sobre os parâmetros da jvm para setar um limite mínimo e a máximo para alocação dinâmica de memória(heap), que são -Xms e -Xmx respectivamente. Apresentou a utilização de algumas ferramentas(java -verbose:gc, java -Dcom.sun.management.jmxremote , VisualVM, jmap, jhat), explicou como a garbage collection lida com os hashMap's.