# Git

* Documento de registro de boas práticas e padrões de uso internos do Git.
* Documentação oficial: [https://git-scm.com/doc](https://git-scm.com/doc).

# 1 - Primeiros passos

### Instalação

* Realizar download do Git no link: [https://git-scm.com/downloads](https://git-scm.com/downloads).
* Durante a instalação, selecionar o **Visual Studio Code** como editor padrão do Git.

### Criar área de trabalho (workspace)

* Criar uma pasta para armazenar projetos do Git. Exemplo: **workspace**.
* Dica: configure o prompt de comando para inicializar no diretório da workspace.

### Inicializar Git

* Acessar a workspace pelo prompt de comando ou Visual Studio Code e digitar o comando:

```
git init
```

### Clonar repositório

* Criar uma cópia de um projeto hospedado em um repositório remoto de Git com o comando:

```
git clone url-do-projeto

```

* Para clonar este projeto digite o comando:

```
git clone https://github.com/juliogcampos/git.git

```

# 2 - Principais comandos

### Realizar commit

* A cada alteração importante no projeto, é recomendado registrar as alterações de código em um commit com o comando:

```
git add .
git commit -m "Sprint 01 - Descrição do commit"
```

* Ou, de forma simplificada:

```
git commit -a -m "Sprint 01 - Descrição do commit"
```

### Desfazer último commit

* Se foi realizado push após o commit, digite o comando:
```
git revert HEAD~1
```
Ou HEAD~2 para reverter os 2 últimos commits.

* Se não foi realizado push após o commit, digite o comando:

```
git reset HEAD~1
```
Ou HEAD~2 para reverter os 2 últimos commits.

### Realizar pull

* Use este comando para receber todas as alterações de código do projeto enviadas por outros desenvolvedores para o repositório remoto do Git.

```
git stash save
git pull
git stash apply
```

### Realizar push

* Use este comando para enviar todas as suas alterações de código do projeto para o repositório remoto do Git.

```
git push
```

# 3 - Desenvolvimento com branches

* Uma branch é um ramo criado na árvore de desenvolvimento de um projeto que permite, por exemplo, escrever código de forma isolada.
* Todo projeto Git possui uma branch principal chamada **master**.
* Os códigos criados em uma branch podem ser mesclados com a branch master pelo comando merge.

### Criar branch

* Para criar uma branch, digite o comando:

```
git-branch nome-da-branch
```

### Acessar branch

* Após criar a branch, acesse a branch com o comando:

```
git checkout nome-da-branch
```

* Para voltar a branch master, digite o comando **git checkout master**

### Verificar branch ativa

* Para verificar qual branch está ativa, digite o comando:
```
git-branch
```

### Realizar push na branch

* Para realizar o primeiro push na branch é necessário digitar o comando:

```
git push --set-upstream origin nome-da-branch
```

### Realizar merge de uma branch com a master

* Antes de realizar um merge (mesclagem) de código com a branch master, verifique se existe código não comitado com o comando **git status**.
* Envie todos os commits para a branch master com o comando **git push**.
* Mescle o código de uma branch com a master com os comandos:

```
git merge master
git push
```

### Realizar merge da master com uma branch

* Atenção: não execute esse passo sem realizar o anterior!
* Digite os comandos abaixo para mesclar o código da master com uma branch:

```
git checkout master
git pull
git merge nome-da-branch
git push
```

# 4 - Ignorar arquivos no Git

* O arquivo de extensão **.gitignore** especifica quais arquivos e diretórios não devem ser rastreados pelo Git. Em geral, são arquivos temporários, compilados e diretórios com dependências do projeto.
* O Git possui uma coleção de templates .gitignore disponíveis no link: [https://github.com/github/gitignore](https://github.com/github/gitignore).

