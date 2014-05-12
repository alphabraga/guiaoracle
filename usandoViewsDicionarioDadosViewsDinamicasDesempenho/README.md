#Usando Views de diconarios de dados e views dinamicadas de desempenho

Esse capitulo tem o objetivo fornecer condições de identificar objetos internos do banco de dados , identificar o conteudo e os usos do dicionário de dados, descrever como as views de dicionário de dados são criadas. Identificar as categorias de views de dicionário de dados, consultar as views dinâmicas de desenpenho. Descrever as convenções de nomeação de scripts administrativos.

##Objetos Internos de Banco de Dados

###Dicionário de dados

Ele é eseencial para qualquer banco de dados Oracle. Contem informações sobre objetos internos do banco de dados. Essas informações ficam contidas em tabelas e views somente para leitura, armazenadas no tablespace SYSTEM. Pertencem ao usuario SYS, mantido pelo serviodor Oracle.

Essas views e tabelas são acessadas como uma tabela qualquer ou seja com um simples SELECT

Alem de ser essencial para o banco de dados, ele é uma fonte de dados muito importante para os usuarios do banco de dados. Desde usuários finais a desgners de aplicações a administradores de banco de dados.

O dicionário de dados são atualizados sempre que um comando DDL e DML são executados.

Dentro do dicionário de dados existem dois tipos de objetos. As Tabelas-Base e as Views de Dicionários de Dados.

####Tabelas-base

São tabelas subjacentes que armazenam informações sobre o banco de dados. Elas são os primeiros objetos a serem criados em qualquer banco de dados. Elas são criadas automaticamente quando o banco de dados executa o arquivo sql.bsq durante a criação do banco de dados. Apenas o servidor deve gravar essas tabelas. Usuários rarramente acessam essas tabelas diretamente pois os dados são armazaenados atravez de criptografia. Nunca use comandos DML para atualizar tabelas-base diratamente, exceto a tabela AUD$. Exemplo de uma tabela  IND$ que contem informações sobre os indices do banco de dados. 

Como já foi informado as tabelas-base são criadas no momento quem que o banco de dados é criado. Mas atenção quando um novo banco de dados for criado você deve executar o scrtipt manualmente e o mesmo deve ser feito quando um upgrade do banco de dados for realizado.

Esses scripts devem ser utilziados pelo usuário SYS com provilegio SYSDBA. Os scripts estão localizados no seguinte diretorios:

	$ORACLE_HOME/rdbms/admin //no (l)unix 

	$ORACLE_HOME\rdbms\admin //no windows


Um dicionário de dados contem:

*Estruturas logicas e fisicas de um banco de dados
	*tabelas
	*views
	*índices
	*clusters
	*sinôminos
	*sequências
	*procedimentos
	*funções
	*pacotes
	*triggers
*Definições e alocações de espaços de objetos
*Restruições de integridade
*Usuários
*Atribuições
*Privilegios
*Auditoria


####Tabelas Dinâmicas de Desempenho

São resumos das tabelas-base. Essas views fornecem informações mais amigaveis aos usuarios que as utilizam. Como por exemplo as views exibem os nomes dos objetos e não apenas os números  dos objetos, o que facilita a visualização das informações.

Para criar as views o script catalog.sql é executado após o comando CREATE DATABASE.

	catalog.sql //Cria as views de dicionário de dados e seus sinonimos


	catproc.sql //Executa scripts  necessarios para PL/SQL no lado do servidor.		



Contêm informações usadas pelo DBA para monitorar  e ajustar o banco de dados e a instância.

####Pacotes PL/SQL

Unidades de programa que eumentam a funcionalidade ao banco de dados. Esses pacotes são criados quando o script catprod.sql é executado após o comando CREATE DATABASE.

####Triggers de eventos do banco de dados: Os triggers são procedimentos executados implicitamente sempre que uma view ou uma tabela é modificada, ou quando ocorrem ações de usuários ou do sistema do banco de dados.