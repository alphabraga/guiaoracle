#Conceitos Básicos do Servidor Oracle

Nesse capitulo seram abordados as ferramentas de administração do banco de dados, os recursos do Oracle Universal Installer, interação com o banco de dados com o SQL*PLUS e outros compomentes importantes do Oracle Enterprise Manager.


##Oracle Universal Installer

O Oracle Universal Installer ou OUI é uma feramenta utilizada para instalar, atualizar e remover componentes de software e banco de dados.

Caracteristicas e funcionalidades

*Baseado em um mecanismo Java
	*Possiblita a resolução de dependencias automatizada.
	*Instalações baseadas na web.
	*Inventário de rastreamento de instalações de componentes instalados
	*Desinstalação  de componentes instalados
	*Suporte a vários diretorios Oracle Home
	*Suporte a tecnologia de globalização
	*Pode ser executado em modo interativo ou silencioso

###Para iniciar o OUI

No Linux:

	$ ./runInstaller

Atenção, no Linux não execute esse comando como usuário root.

No Windows:

	Start > Programs > Oracle Installation Products > Universal Installer 

O arquivo do instalador esta localizado em Program Files/Oracle/oui/install/install.exe

A instalção silenciosa é utilizada quanod não são planejadas ações do usuário ou se forem utilizados terminais não gráficos para a instalação.

Os parametros de instalaçãop são passados atravez de um arquivo de configuração. Esse arquivo de configuração é um arquivo de texto que contem os parametros. Existe um modelo de arquivo de configuração no Linux localizado em stage/response. Abrindo esse arquivo podemos  


##Oracle Database Configuration Assistant

É uma ferramenta que possui uma interface grafica que é utilizada para manipular bases de dados. Essa feramente por sua vez integarge com o OUI.

##SQL*PLUS

É um programa que se conecta a um servidor oracle e interage com bases de dados. Atravez dele você envia ao servidor instruções sql para seleção de dados, inserção, atualização, exclusão de dados dentre outros.

