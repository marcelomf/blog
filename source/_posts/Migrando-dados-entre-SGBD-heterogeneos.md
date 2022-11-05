---
title: Migrando dados entre SGBD heterogêneos
tags:
  - banco de dados
  - coding
  - java
  - software livre
excerpt: ''
date: 2009-09-29 16:09:00
---

No início do ano foi me dada a tarefa de sincronizar 2 bases de dados(+300 tabelas de alguns gigas) entre SGBD's distintos(db2 -> mysql), estando limitado a um link de 512kb para a transferência dos dados. Pesquisei diversas soluções open source's e proprietárias, as soluções proprietárias para realizar ETL foram descartadas pela empresa devido ao custo. Logo, me sobrou as soluções open source, oba ;).  
  
Como já era de se esperar, eu não encontrei nenhuma solução open source que se encaixasse como um luva para o meu problema, mais tudo bem, é nesse momento que entra a diversão xD. Dividindo a esquemática em 2 etapas, temos:  
  
   1.Migrar o DDL, deixando que o novo banco de dados(slave/destino dos dados/mysql) tenha a estrutura semelhante ou igual ao do banco já existente(master/origem dos dados/db2).  
   2.Migrar e sincronizar os dados todas as noites, pois não fazia parte dos requisitos da solução uma sincronização “on the fly”.  
  
No início eu estava procurando por features do próprio banco de dados para tentar trabalhar com task's e procedure's, li algumas coisas sobre dblink(postgresql/mysql)/data federation(db2), mas como o meu acesso ao ambiente de origem era restrito(ddl dos schema's e view's para acessar os dados) eu tive que ir para outro rumo. Antes de começar a falar sobre o dbmt(http://sourceforge.net/projects/dbmt/) software que me ajudou a resolver o problema, quero citar outros 2 projetos que me chamaram a atenção, mas que infelizmente não deu para serem aplicados na minha realidade(restrições de acesso no ambiente de origem), são eles:  
http://symmetricds.codehaus.org/  
http://www.drbd.org/  
  
Para migrar o DDL foi utilizado o mysql migration tools, existe diversas ferramentas que fazem isso, o melhor é pegar uma especifica do seu banco destino(no meu caso mysql)... testei varias e mesmo o mysql migration tools não funcionou 100%, pois tive que migrar schema por schema e consertar algumas foreign key na mão(isso porque o mysql não suporta foreign key entre schemas, já o DB2 sim). Depois de estar com o DDL 100%, realizei algumas alterações na nomeclatura das tabelas para atender melhor ao padrão de modelagem de dados da empresa onde trabalho. Feito isso, fui para a segunda etapa, customizar o DBMT para migrar e sincronizar os dados todas as noites.  
  
O dbmt é software open source escrito em java que realiza a engenharia reversa em uma fonte de dados(jdbc/xml/csv/dbf) e gera um xml relacionado a fonte de origem e de destino, bem como suas tabelas e colunas. É exatamente o que eu pensei em fazer na época, mas graças ao open source consegui pronto ;), mas como eu tinha dito antes, não foi lá as mil maravilhas, então vamos aos fatos.  
  
Todas as noites o banco de dados de destino(mysql) tinha as suas tabelas truncadas e os seus dados eram reimportados do banco origem(db2), isso é algo bastante ruim, pois eu não queria perder tempo/banda, trazendo novamente dados que eu já tinha e que não sofreram alterações(a regra de negócio me garantia isso)... para resolver isso, comecei a trabalhar nas tabelas mais criticas em termos de tamanho (tabelas de movimentação financeira/contábil) e passei a trazer os registros a partir do último registro que eu possuía, na realidade alguns registros para traz, utilizando unique's compostas, eu conseguia garantir que jamais teria um dado duplicado. Isso vai depender muito do seu negócio e da sua necessidade.  
  
Para migrar dados com o dbmt, você passa por 2 etapas, são elas:  
  
   1.Criação do xml.  
È aqui que altero o xml que será gerado, buscando atender as minhas necessidades e que verifico os últimos registros das tabelas de movimentação no banco destino(mysql) e crio as condições/where's que serão executadas lá no banco de dados origem(db2), isso para ganhar tempo. Para fazer isso, foi necessário alterar a classe:  
      1.CreateMigration  
         1.Criei também 2 métodos, um para adicionar prioridade para determinadas tabelas e outro para bypassar determinadas tabelas.  
         2.Uma classe para conexão jdbc ao meu banco destino(mysql).  
         3.Uma classe para geração das condições/where's de cada tabela que é feito de acordo com a “regra de negócio de persistência” das mesmas.  
         4.Alterei o método extractTable() para gerar as tabelas e colunas de acordo com a nomeclatura padrão do meu banco destino(mysql).  
   2.Importação dos dados.  
Uma vez que o xml está gerado, o dbmt utiliza o mesmo para começar a importação. Nessa etapa eu tive 2 problemas:  
      1.Precisava desabilitar a checagem de integridade de referencia das foreign keys no mysql, para isso, alterei o método initTarget da classe MigrationJDBC e adicionei as seguintes variáveis de conexão:  
?autoReconnect=true&sessionVariables=FOREIGN\_KEY\_CHECKS=0  
      2.Outro problema estava relacionado ao SqlJep que o DBMT utiliza para a aplicação dos where's, o SqlJep busca ser uma linguagem padrão para DML em SGBD's distintos, o problema é que o where erá aplicado em cima do resultset select \* from dborigemDB2.nome\_tabela, ou seja, o where não erá aplicado diretamente no banco de dados origem(db2) e sim seu resultset(do select \* from...), dessa forma, toda a economia de banda que eu teria ganhando criando os where's dinâmicos na etapa 1(criação do xml) seria perdida... para resolver isso, foi necessário alterar o método initSource para não utilizar o sqljep e aplicar o where diretamente no banco de dados origem(db2), o ruim disso é que o DML desse select teve que ser padrão DB2 que por sinal é bem chatinho, mas nada que uma googada não resolva.  
  
Se você achou interessante essa solução, baixe o source do dbmt e estude principalmente as classes: CreateMigration, Migration, MigrationJDBC e Step. Não deixe de criar rotinas que possam validar realmente a integridade dos dados entre origem/destino, é isso! Abraços.