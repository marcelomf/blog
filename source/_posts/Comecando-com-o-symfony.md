---
title: Começando com o symfony
tags:
  - arquitetura
  - coding
  - php
excerpt: ''
date: 2009-09-10 10:45:00
---

Diversos colegas já me pediram ajuda para começar com o symfony, então eu enviava um email para eles explicando o básico sobre o symfony(escrito referenciando a versão 1.0, mas sem grandes dramas para a 1.2), segue abaixo o conteúdo do email.

Ele usa o propel para orm ou o doctrine, a versão 1.3 do propel está usando o pdo para abstração de dados, enquanto que a 1.2 utiliza o creole, o doctrine já nasceu usando o pdo... é mais vantagem utilizar o PDO pois o mesmo tornou-se nativo no php, recomendo então que você utilize o symfony com a versão 1.3 do propel ou com o doctrine...  
  
o symfony funciona em MVC e com as seguintes particularidades:  
  
1 - Preparar o apache para o symfony funcionar... habilitar o mod\_rewrite e criar um Alias...(na documentação em anexo ensina isso)  
  
2 - Modela-se([http://sourceforge.net/projects/dbdesigner-fork](http://sourceforge.net/projects/dbdesigner-fork)) o banco de dados seguindo os padrões que o symfony exige, exemplo:  
Chave primaria -> id  
Chave estrangeiras -> tabela\_id  
boolean como tinyint...

3 - Cria a pasta do projeto(mkdir projeto) e dentro dela cria-se o projeto com symfony init-project e depois cria-se a aplicação com symfony init-app.  
  
4 - Faz-se a engenharia reversa no banco com o intuito de gerar o schema.xml/schema.yml utilizado pelo propel para criar o modelo, symfony propel-build-schema (antes você tem que configurar config/databases.yml e propel.ini )  
  
5 - Gerar o model com symfony propel-build-model, as classes ficam em lib/model, em lib/model/om ficam as classes que ele realmente gerou... as que ficam no model são as que você ira adicionar código... seja para persistência ou regra de negocio. Lendo a documentação você consegue trabalhar com pacotes! Para criar pacotes com classes que não tem a ver com o banco, procure sobre autoload, além disso você pode trabalhar com mais de um banco de dados, basta configurar o databases.yml corretamente.  
  
6 - Gerar o view e o controle com propel-init-admin, existe o generete-crud e init-crud, de longe eu prefiro o init-admin, pois o código gerado segue os padrões tableless..., uma vez gerado com o  
init-admin você precisa aprender a utilizar o generators.yml que é o que "configura" o VIEW... para telas mais trabalhadas eu prefiro criar a pasta templates no modulo da aplicação e copiar do cache o código gerado do view, copio só o que preciso e altero... é bom dar uma lida no código gerado na pasta cache... só assim para entender legal como funciona o controle e o view...  
  
Dos framework's que eu olhei na época(meados de 2007... cakephp, phpinsigner, symfony, zend) o symfony é o que tem uma maior curva de aprendizado... mas de longe era o melhor estruturado e que me fornece total possibilidade de customização... recomendo ele fortemente!  
  
links:  
[http://www.symfony-project.org/doc/1\_0/](http://www.symfony-project.org/doc/1_0/)  
[http://symfony-brasil.com/](http://symfony-brasil.com/)  
[http://trac.symfony-brasil.com/](http://trac.symfony-brasil.com/)  
  
plugins:  
[http://trac.symfony-project.com/wiki/SymfonyPlugins](http://trac.symfony-project.com/wiki/SymfonyPlugins)  
  
lista:  
[http://groups.google.com/group/symfony-pt/topics](http://groups.google.com/group/symfony-pt/topics)