# Git Quickstart Guide


## Preparando o Ambiente
Antes de entrar no que é o GIT e seus usos, vamos explicar como instalá-lo nas plataformas
# Instalação 
Para esse Quickstart não utilizaremos GUI, somente linha de comando
###	Windows
Para instalar o GIT em seu Windows, acesse https://git-scm.com/downloads e baixe a versão para Windows. 
O Instalador é simples, next-next-finish.
###	Linux / Unix
####	Debian/Ubuntu
`apt-get install git`

*Para Ubuntu, esse PPA fornece a última versão estável*

`add-apt-repository ppa:git-core/ppa `
` apt update`
` apt install git`


## Configuração do Git
Após a instalação, podemos verificar se o GitBash se encontra instalado no Windows, ou abrirmos um console no Linux e digitar o seguinte comando
`git` 
 
 Como resultado de sucesso, deveremos ver algo similar a:

 

Devemos configurar nosso user global:
# git config --global user.name "Paulo Antonio Cerávolo"
# git config --global user.email "contato@ceravolo.com.br"
  
Essas são as configurações padrão para todos os repositórios.
Dica
Para uma configuração específica de repositório, você deverá, na pasta dele, digitar
# git config user.name "Paulo Antonio Cerávolo"
# git config user.email "contato@email2.com.br"
 
Utilizamos essa opção quando temos credenciais específicas para um projeto. 
2.	GIT e Versionamento
Um sistema de controle de versões (ou versionamento), VCS (do inglês version control system) ou ainda SCM (do inglês source code management) na função prática da Ciência da Computação e da Engenharia de Software, é um software que tem a finalidade de gerenciar diferentes versões no desenvolvimento de um documento qualquer. Esses sistemas são comumente utilizados no desenvolvimento de software para controlar as diferentes versões — histórico e desenvolvimento — dos códigos-fontes e da documentação
O Git é um sistema open-source de controle de versão.
2.1.	História
O desenvolvimento do Git surgiu após vários desenvolvedores do kernel do Linux terem uma desavença com o proprietário do BitKeeper por conta de engenharia reversa de protocolos (não ocorreu, na verdade foi um telnet para a porta do servidor e envio do comando help).
A partir daí, Linus Torvalds e sua equipe começaram a desenhar um sistema para desenvolvimento não linear, distribuído, retrocompatível, escalável, com suporte para grandes projetos, timeline com criptografia, 
2.2.	Motivação
Imagine os seguintes cenários
Tenho uma aplicação que desenvolvo com mais pessoas. Cada pessoa é responsável por uma funcionalidade específica do código. Como vamos trabalhar em conjunto para que todas as partes sejam integradas da forma menos traumática possível?
Tenho uma aplicação que mantenho sozinho. Quero aumentar as funcionalidades da aplicação. Fiz uma modificação que inseriu um bug, e meu backup tem data de ontem. Perdi um dia de trabalho? Tento fazer um BugFix? Quanto tempo eu vou gastar caçando esse Bug?
Por isso é importante termos um sistema de controle de código
2.3.	Benefícios
Linha do tempo
	Temos uma linha cronológica de desenvolvimento de um aplicativo, mostrando a ordem de commits, branches, merges etc.
Segurança
	Evita corrupções de arquivos, identificação de mudanças. Uso de repositórios remotos garante resiliência.
Trabalho em equipe
	Os branches permitem que mais de uma pessoa possa trabalhar na mesma feature ou no mesmo projeto. 	
Organização
	O ciclo de vida da aplicação é controlado.
Rasterabilidade
	Quando se trata de algo importante, é sempre interessante saber “Quem”, “Quando”, “Como”, “Por que” e “Onde”.
3.	GitHub – Um depósito de Códigos social
3.1.	O que é
O GitHub é uma plataforma de desenvolvimento inspirada na maneira como você trabalha. Do código aberto aos negócios, você pode hospedar e revisar códigos, gerenciar projetos e criar software junto a 50 milhões de desenvolvedores.
Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo.
Projetos hospedados: Worpress, GNU Linux, Atom, Electron

3.2.	Criação de Conta

3.3.	Configuração de Chaves SSH

3.4.	Conceitos e Comandos
Regra de ouro: Teve dúvida? Sua primeira linha de frente é
git NOME_COMANDO --help
3.4.1.	Repositório

3.4.2.	Init
Utilizado para iniciar nosso projeto com um sistema de controle de versão de código
Na pasta do projeto, digite
git init 
3.4.3.	3. Clone
Clona um projeto já existente
git clone URL
Com o GitHub, é necessário a configuração das chaves SSH
3.4.4.	Remote
Repositório Remoto do nosso Projeto. Para configurá-lo: 
git remote add origin URL_REPO
git remote remove origin 

3.4.5.	Workflow

3.4.6.	Branch

3.4.7.	Checkout

3.4.8.	Commit

3.4.9.	Amend

3.4.10.	Push / Pull

3.4.11.	Merge e Conflitos

3.4.12.	Pull Requests

3.4.13.	Rebase

3.4.14.	Tagging

4.	Futuro

Referências
https://git-scm.com/ - Git 






