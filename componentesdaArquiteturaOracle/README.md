#Componentes da Arquitetura Oracle

Um servidor Oracle é composto por processos de 2 plano, estruturas de memoria e arquivos.

Esses componentes tem diversas funções dentro do ecosistema Oracle. Como melhoria de desempenho, mecanismos de recuperação de desastres e até mesmo para execução de funcionalidades triviais do banco de dados.

##Componentes de Memoria

A estrutura de memoria do Oracle se divide em duas areas:


###System Global Area  - SGA

Sempre que uma instancia Oracle é inicializada é criada em memoria uma area chamada System Global Area e os processos de 2 plano são inicializados.

É componente fundamental em uma instância e possui as seguintes caracteristicas:

Ela é dinamicamente alocada e seu tamanho é definido pelo parametro SGA_MAX_SIZE. tamanho das suas subareas, tambem chamadas de granulos é definida de forma proporcioanal de acordo com o SGA_MAX_SIZE.

####Shared Pool

Relacionada ao desempenho. Nessa area são armazenadas consultas SQL e definições de dados recentemente executadas. 

É subdividida duas areas: Cache de Biblioteca e Cache de Dicionário de Dados. É dimensionado pelo parametro SHARED_POOL_SIZE.


	ALTER SYSTEM SHARED_POOL_SIZE = 64M;

#####Cache de Biblioteca

Armazena informações sobre instruções SQL

#####Cache do Dicionario de Dados

Armazena informações sobre definições utilizadas mais recentemente, informações sobre arquivos, privilegios etc...


####Cache de Buffer do Banco de Dados

####Buffer de Redo Log

####Outras extruturas

####Large Pool

####Java Pool

###Process Global Area - PGA

	Alocado quando o processo no servidor é iniciado.

##Arquivos

No Oracle os arquivos servem para armazenar fisicamente os dados inseridos no banco, realizar recuperação de desastres.	Arquivos de banco de dados servem para garantir a integridade do banco. Consiste basicamnete em 3 tipos de arquivo:

###Arquivos de Dados

Composto pelo dicionário de dados e ~cabeçalho~

###Arquivos de Controle



###Arquivos de Redo Log On-line

Existem ainda outros arquivos importantes que servem para relizar configurações da propria instancia, configurações de acesso, privilegios de usuários e recuperar o banco em caso de falhas.

##Processos do Cliente e do Servidor

Esses processos que envolvem o Cliente e o Servidor são os principais envolvidos na execução de uma instrução SQL. No entanto outros processos processos que podem participar da execução dessas instruções.

### Outros Processos

Ainda existem outros processos onde cada um tem um escopo muito bem definido, mas que no momento não seram abordados.