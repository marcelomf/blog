---
title: 'FISL 9: Real-Time linux e Real-Time java um novo mundo, sem delays'
tags:
  - coding
  - fisl
  - java
  - kernel
  - linux
excerpt: ''
date: 2008-05-01 21:30:00
---

Palestrante: Flavio C. Buccianti  
Considerações: Marcelo M. Fleury

A palestra começou com um apanhado geral sobre RTOS(Real-Time Operating System), explicando que o objetivo de um rtos é garantir um menor tempo possível na execução de um código entre um evento e outro, e que esse tempo é chamado de latência e que existem 2 tipos de latência (Scheduler/Interrupção). Existem basicamente 2 categorias de rtos, os Hard Real-Time que tem a máxima latência previsível e os Soft Real-Time que possuem uma latência de “melhor esforço”. Foi comentado que os rtos tradicionais utilizam mono-processamento, até porque possuem velocidade de CPU restritas. Porem os computadores SMP estão cada vez mais populares e a necessidade do mercado hoje é obter informações em um menor tempo possível, além de que, essas informações podem estar não somente em um local, mais em vários, tornando então a utilização de um protocolo de comunicação obrigatório(tcp/ip). Então nós temos um novo tipo de real-time, o “Enterprise real-time”, o mesmo suporta smp, tcp/ip, middleware's, etc. Já existe uma seria de colaborações voltadas a aplicações “Enterprise real-time”, dentre elas, podemos destacar: config\_preempt\_rt(patch para o kernel 2.6.\*, para suportar aplicações em tempo real) e o IBM Websphere Real-Time, jvm da ibm que trabalha junto com config\_preempt\_rt. O websphere possui as seguintes features: RTSJ(Real-Time Specification for Java), Metronome(garbage collector real-time) e AOT(Ahead of time compilation). Comentou-se sobre scoped memory, immortal memory e priority inheritance(glibc).