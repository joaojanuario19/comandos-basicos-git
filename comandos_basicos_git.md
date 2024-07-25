# COMANDOS BÁSICOS GIT

- **acessar pasta/repositório :**

  comando -> cd (nome_do_repositório) ou (.nome_do_repositorio)-> repositório oculto

```
joao@Megatron MINGW64 ~/git/repository (master)
$ cd .git

```

- **listar arquivos do repositório :**

  comando -> ls

```
joao@Megatron MINGW64 ~/git/repository/.git (BARE:master)
$ ls
COMMIT_EDITMSG  HEAD  branches/  config  hooks/  index  logs/  objects/  refs/

```

- **abrir arquivo :**

  comando -> cat nome_do_arquivo

```
joao@Megatron MINGW64 ~/git/repository/.git (BARE:master)
$ cat config
[core]
    symlinks = false
    repositoryformatversion = 0
    filemode = false
    logallrefupdates = true
[remote "origin"]
    url = https://github.com/joaojanuario19/dio-trilha-java-basico.git
    fetch = +refs/heads/_:refs/remotes/origin/_

```

- **vincular um repositório local (Computador) ao repositório remoto (github)**

   comando -> git remote add origin url_do_repositórioGithub

```
joao@Megatron MINGW64 ~/git/repository/.git (BARE:master)
$ git remote add origin https://github.com/joaojanuario19/dio-trilha-java-basico.git

```

- **consultar a árvore de trabalho, a área de preparação e mostrar o estado dos arquivos**

  comando -> status

```
joao@Megatron MINGW64 ~/git/repository (master)
$ git status
On branch master
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: jacAula1/src/jacAula1pkg/BoletimEstudantil.java
modified: jacAula1/src/minhaclasse/MinhaClasse.java

Untracked files:
(use "git add <file>..." to include in what will be committed)
jacAula1/src/minhaclasse/Operadores.java

no changes added to commit (use "git add" and/or "git commit -a")

```

- **criar um repositório**

  comando -> mkdir (nome_do_repositório)

```
joao@Megatron MINGW64 ~/git/repository (master)
$ mkdir rep-vazio

```

- **criar um arquivo(markdown) no repositório vazio (OBS 1)**

  comando : touch (nome_do_repositório/nome_do_arquivo.md)

```
joao@Megatron MINGW64 ~/git/repository (master)
$ touch rep-vazio/gitkeep.md

```

- **ignorar repositório**

  comando -> echo (nome_do_repositório/) > .gitignore

```
joao@Megatron MINGW64 ~/git/repository (master)
$ echo rep-vazio/ > .gitignore

```

- **adicionar repositório ou arquivo na área de preparação (OBS 2)**

  comando -> git add (nome_do_repositório ou nome_do_arquivo)

```
joao@Megatron MINGW64 ~/git/repository (master)
$ git add jacAula1/src/jacAula1pkg/BoletimEstudantil.java

```

- **adicionar todos os arquivos na área de preparação**

  comando -> git add .

```
joao@Megatron MINGW64 ~/git/repository (master)
$ git add .
```

> [!NOTE]

> Consultando a área de preparação após adicionar todos os meus arquivos.

```
joao@Megatron MINGW64 ~/git/repository (master)
$ git status
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
new file: .gitignore
modified: jacAula1/src/jacAula1pkg/BoletimEstudantil.java
modified: jacAula1/src/minhaclasse/MinhaClasse.java
new file: jacAula1/src/minhaclasse/Operadores.java

```

- **remover arquivo da área de preparação**

  comando -> git restore --staged (nome_do_arquivo)

```
joao@Megatron MINGW64 ~/git/repository (master)

$ git restore --staged .gitignore

```

- **Grava as alterações feitas no repositório**

  comando -> git commit

```
joao@Megatron MINGW64 ~/git/repository (master)
$ git commit -m"commit inicial"
[master b0e2e34] commit inicial
3 files changed, 125 insertions(+), 1 deletion(-)
create mode 100644 jacAula1/src/minhaclasse/Operadores.java

```

- **Mostrar logs de confirmação, o comando lista os commits realizados (do mais recente para o antigo)**

  comando -> git log

```
joao@Megatron MINGW64 ~/git/repository (master)
$ git log
commit b0e2e34ab8bf438eb566696ebc53ff041d2b2424 (HEAD -> master)
Author: joaojanuario <joao******\*\*******.com>
Date: Wed Jul 24 15:40:14 2024 -0300

    commit inicial

commit dbfcbde83e2619924b6f2d72b47b569c5ba48690
Author: joaojanuario <joao******\*\*******.com>
Date: Tue Jul 9 21:22:38 2024 -0300

    (BoletimEstudantil)algoritmo condicional básico, (MinhaClasse)classe de
    teste da nomeclatura das variáveis e métodos

```

> [!NOTE]

> consulta na árvore de trabalho após o commit

```
joao@Megatron MINGW64 ~/git/repository (master)
$ git status
On branch master
Untracked files:
(use "git add <file>..." to include in what will be committed)
.gitignore

nothing added to commit but untracked files present (use "git add" to track)

```

**OBS 1: O GIT ignora repositórios(pastas) vazios, para reconhecer crie um arquivo .gitkeep dentro do repositório que vc quer adicionar.**

**OBS 2 : área de preparação é onde selecionamos e salvamos arquivos, "empacotando" para um commit**
