## GERAR CHAVE SSH
- Em caso de acesso ssh
> $ ssh-keygen -t rsa -b 4096 -C "{seu email}"

## CONFIGURAÇÕES DE USUÁRIO

- Ver arquivo das Configurações.
> $ cat C:/Users/{usuario}/.gitconfig

- Listar Configurações
> $ git config --list

- Alterar Nome
> $ git config --global user.name "{seu nome}"

- Alterar E-mail
> $ git config --global user.email "{seu e-mail}"



## PRIMEIROS PASSOS

- Criando um repositório (.git)
> $ git init

- Status dos arquivos
> $ git status


## GIT COMMIT

Fazer um commit
> $ git commit -m "<descrição>"

Incluir alteração no último commit
> $ git commit -m "<descricao>" --amend


## BRANCH

Criar nova branch:
> $ git branch <name_branch>

Criar nova branch - Vazia:
> $ git checkout --orphan <name_branch>

Acessar uma branch:
> $ git checkout <name_branch>

Criar e acessar uma branch
> $ git checkout -b <name_branch>

Renomear (Dentro da branch)
> $ git branch -m <new_branch_name>

Remover (Dentro da branch) (uma ou mais)
> $ git branch -D <name_branch, name_branch> 

Criar uma branch baseada em uma outra branch especifica
> $ git checkout <branch_base> -b <branch_new>

Delete branche remota
> $ git push origin <branch> --delete
> $ git push origin :<branch>

Criar branch apartir de um upstream 
> $ git fetch <upstream>
> $ git checkout upstream/dev -b <branch>

** Branch são criadas com base na branch Atual
(master)

## FETCH

- Verificar se a alterações no repositório remoto
> $ git fetch <name_remote>

## MERGE

Fazer um merge (Dentro da branch)
> $ git merge <name_branch>

Fazer um merge de um remote local
> $ git merge upstream/master

Abortar O Merge
> $ git merge --abort


## REPOSITÓRIO

Adicionar Repositório Remoto:
> $ git remote add <origin>

Sincronizar ambiente local com repositório
> $ git push <origin> <branch>

Pegar dados do repositório:
> $ git pull 

Listar Repositórios remotos
> $ git remote -v

Alterar URL de origin
> $ git remote set-url <origin> <url>

Adicionando Repositório upstream
> $ git remote add upstream <url>

Alterar nome do repositorio
> $ git remote rename <old> <name>


## Git Log
Todos as informações
> $ git log

Hahs, branch, Mensagem
> $ git log --oneline

Os últimos dois commit, com suas alterações
> $ git log -p -2


# OUTROS 

- Remover arquivo(s) do Area Staging
> $ git rm --cached <file>


Voltar alterações que não ja foram trancked (git add)
> $ git checkout <file>
> $ git restore <file>

Voltar alterações que ja foram trancked (git add)
> $ git restore --staged <file>
> $ git reset HEAD <file>

## Voltar no tempo

- Voltar para o um determinado commit:
> $ git checkout <hash_commit>

Criar uma branch para voltar naquele commit
> $  git switch -c <new-branch-name>
> $  git checkout -b <new-branch-name>

Criar uma branch direto, apertir do hash do commit 
> $  git checkout <hash_commit> -b <new-branch-name>


# STASH

- Criar um stash
> $ git stash

- Listar os stash
> $ git stash list


Voltar para o ultimo stash, ou um especifico (não apaga o stash)
> $ git stash apply [<name_stash>] opcional

Remover stash 
> $ git stash drop <name_stash>

Aplica o ultimo stash e remover ele, ou um especifico 
> $ git stash pop [<name_stash>] opcional

# REVERSE
Faz um commit semo commit do hash
> $ git reverse <hash_commit>

# Diff
Diferença entre os arquivos locais, e o ultimo snapshot
> $ git diff

Verificar alterações sem Espaços
> $ git diff -w

Alterações entre os commits
> $ git diff <hash_commit>..<hash_commit>

# TAG
Cria uma tag, opcional deixa uma mensagem
> $ git tag -a <version_name> [ -m "mesngaem" ] opcional

Ver Tags
> $ git tag

# squasd

- Selecionar commits para junta-los
> $ git rebase -i HEAD~<number>
> $ git rebase -i <hash_commit> // a partir desse commit sera selecionado

# cherry-pick
git cherry-pick <hash_commit>

# GIT SHOW 
- Mostra Arquivos a serem 
> $ git show <hash_commit>

# MOSTRAR USUÁRIO QUE A ALTERAÇÃO
> $ git blame 
