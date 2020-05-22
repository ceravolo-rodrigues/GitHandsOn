# RoadMap GIT 

# Cenário 1 - Repositório local
## 1 - Criando Repositório local
Para Criar o Repositório, rode o comando no diretório desejado

`git init`


### 2 - Criando o projeto no GitHub

1. Logado no GitHub, no canto esquerdo está escrito REPOSITORIES e ao lado existe um botão NEW. Clique nele.
2. Preencha o Nome do repositório. A descrição é opcional, mas sempre que puder, a preencha (principalmente para projetos colaborativos)
3. Selecione se o projeto é público ou privado  
4. O arquivo README é uma *boa prática*. Descreva seu projeto nele. Nesse tutorial ele será solenemente deixado de lado, mas para seus projetos, veja como são exemplos de outros projetos
5. Add a .gitIgnore file. No nosso caso, não

>**Atenção:**
>**O .gitIgnore é um arquivo que diz quais extensões, diretórios ou arquivos não devemos subir para o repositório para não onerar o servidor. Por Exemplo: Um projeto em C, não devemos subir os EXE compilados (no Windows) ou os .out no Linux. Em termos gerais, arquivos GERADOS por código não devem ser enviados ao servidor**

6. Licença. No nosso caso não, mas estude um pouco sobre as licenças e como elas impactam no seu desenvolvimento

7. Após a criação, temos que copiar o endereço do repositório. Selecione a opção SSH e copie

### 3 - Configurando o Remote

Crie um Repositório no GitHub
Copie a URL SSH do REMOTE

`git remote add origin URL_REPO`


>**Nota**
>
>*Criaremos dois branches aqui, faremos um commit e pushes, explicaremos o que isso significa nas próximas seções. Aceite como um dogma os comando abaixo*
>
>`git checkout -b master`
`touch readme.md`
`git add .`
`git commit -m "Creating Readme"`
`git push -u origin master`
`git checkout -b release`
`git push -u origin release`
`git checkout master`

## 4 - Adicionando o primeiro arquivo e Commitando

Vamos criar um arquivo vazio. Esse comando não é do GIT, mas sim do S.O. para criar um arquivo vazio. Temos outras formas de fazê-lo
`touch file1`

### Adicionando para Stagging

O que é Stagging?
Adicionar algo ao stage no git permite que você continue fazendo modificações no seu diretório de trabalho e, quando decidir que quer interagir com o controle de versão, permite que guarde as mudanças em pequenos commits.

`git add file1` 

*Podemos adicionar tudo o que foi alteardo para Stagging*

`git add .` 

*Boa prática: Quantos mais commits, melhor. A cada alteração, commite. Commit não custa, um bug sim.*

### Commitando o arquivo com uma mensagem
*Boa Prática: Commit SEMPRE com mensagem*
*Boa Prática: Commits em inglês. Algumas empresas trabalham com commits em inglês, portanto, tenha essa prática desde cedo*

`git commit -m "Create first File"`

###  5 - Fazendo o Push 
Enviando os arquivos para o remote

`git push`

Da primeira vez, precisamos informar quem é nosso repositorio remoto

`git push -u origin master`

Esse comando já foi dado anteriormente, por isso utilizamos somente o `git push`

**Erros Comuns**
1. `# fatal: No configured push destination.`
*Soluçâo: Adicione o Remote*
` git remote add ORIGIN <url>`

2. `# fatal: The current branch master has no upstream branch.`
   *Solução: É necessário correlacionar o branch local e o branch remoto*
   `git push -u origin master` 
   *Fique atento ao nome do branch local e ao branch remoto ao criar novos branches. No começo é um pouco complicado mesmo*

Como é nosso primeiro push, precisaremos colocar `git push -u origin master``

### 6 - Branches
1. Criando Branches


`git checkout -b NOME_DO_BRANCH`

*Lembrando que o novo branch vai ser criado a partir do atual (histórico de commits)*

Criamos o branch e já estamos trabalhando nele

*Para cada FEATURE (funcionalidade) é interessante (em alguns fluxos de trabalho, é obrigatório) criar um novo Branch e codificar SOMENTE essa funcionalidade. Assim, caso exista um bug, ele fica restrito ao branch e o bugfix é específico*

Vamos criar um Branch chamado *feature1*
*Assim como codificar, a semântica é essencial para os branches. Alguns lugares, os branches tem o nome de CARDS de FEATURE (em organizações com um nível de maturidade maior)*

Vamos para master e criar um branch a partir dele
`git checkout master`
`git checkout -b feature1`

### Trabalhando no Branch

Vamos criar um arquivo vazio e commitar

`touch file_feature1`
`git add .`
`git commit -m "Creating file for feature`

Vamos adicionar um texto nela e salvá-la. (Utilize o editor de sua preferência)

Criaremos outro arquivo e vamos adicionar um conteúdo nele

Verifique o status dos arquivos modificados

`git status`

>On branch feature1
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file_feature1
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file2_feature1

*Boa Prática: Vamos criar 2 commits
Um para **criação e alteração da file2_feature1** e outro para **modificação da file_feature1***

`git add file_feature1`
`git commit -m "Changing file_feature1`
`git add file2_feature1`
`git commit -m Creating file2_feature1 and adding its contents`

Vamos ver a nossa história
`git log --oneline`

Enviando pra Remote
`git push`

*Erro:*
`#fatal: The current branch feature1 has no upstream branch.`
Precisamos linkar nosso branch local a um branch remoto
`git push -u origin feature1`

### 7 -  Mergeando e Resolvendo conflitos

Criar um Novo Branch a partir de feature1
Certificando que estamos em feature1
`git checkout feature1`
Criando o branch feature2
`git checkout feature2`

Vamos alterar o arquivo file_feature1, adicionando conteúdo e modificando conteúdo. utilize o editor de sua preferência

Commitemos e façamos o push. Primeiro push, precisamos setar o upstream

`git add .`
`git commit -m "Improving feature1 to code feature2"`
`git push -u origin feature2`
Vamos criar outro arquivo e commitar
`touch file_feature2`
`git add .`
`git commit -m "Creating file_feature2"`
Alteremos o conteúdo do arquivo, commitemos e push
`git add .`
`git commit -m "Coding file_feature2"`
`git push`
Façamos o push.  


Agora, vamos *mesclar* dois branches, mesclar o que foi codificado em feature1 dentro de master, ou seja **MERGE**

Vamos para master
`git checkout master`
`git merge feature1`
Enviando as alterações pro remote
`git push`

## Vamos conflitar

O que vai acontecer quando mesclarmos o conteúdo de master com o de feature2 (após o merge anterior?)

`git merge feature2`

>Saída:
**Updating 5972141..43aef15
Fast-forward
 file_feature1 | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)**

Magicamente o git fez uma solução automática de conflitos
Nem sempre é assim.Vamos forçar uma resolução de conflitos

`git checkout feature1`

Vamos o conteúdo de file_feature1 para #changed
>// appended
dummy
>#changed

Commit e Push
`git add .`
`git commit -m "Coding feature1`
`git push`


Vamos fazer o merge de feature1 pra master
`git checkout master`
`git merge feature1`

Temos o seguinte:

>Auto-merging file_feature1
CONFLICT (content): Merge conflict in file_feature1
Automatic merge failed; fix conflicts and then commit the result.

Eis nosso conflito!
Vamos abrir e resolver no editor.
Técnicas de solução de conflitos que requerem intervenção não serão abordadas aqui. Use o bom senso, o que é preciso estar no arquivo?

Salve o arquivo, Commit e Push

`git add .`
`git commit -m "file_feature1 merge solution"`
`git push`
## 8 - Pull Request

Via GUI do GitHub.

# Como Clonar um repositório existente

Vá para outro diretório
Rode `git clone URL`
Você tem outra estrutura prontinha!

# Dicas com amor (que aprendi pela dor)

- Sempre verifique se seu branch está atualizado com remote ANTES de começar a codificar.
   `git pull origin`
- Vefique em qual branch está antes de começar a codificar.
- No merge, se certifique o branch de origem e o de destino.
- Verifique outros comandos como STASH, REBASE
- Quase nunca, em uma organização com uma maturidade de código mínima, você poderá fazer pushes ou commits para master/release. Somente com pull requests. Isso é necessário por conta da revisão de código.
