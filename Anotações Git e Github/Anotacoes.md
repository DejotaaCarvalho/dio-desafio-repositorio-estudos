## O que é git  
O Git é um sistema de controle de revisão distribuído rápido, escalável e com um conjunto de comandos extraordinariamente ricos que fornecem operações de alto nível e acesso total aos internos.


## Entender o conceito do git  
Sistema de controle de revisão distribuído

## Comandos mais utilizados no dia a dia  


Este comando é usado para criar um novo repositório GIT.
```bash
git init
```

Efetua um clone (cria uma pasta na sua máquina com todos os arquivos que estão no servidor).
```bash
git clone 
```

Lista todos os arquivos que foram alterados.
```bash
git status
```

git rm pode ser usado para remover arquivos do índice e do diretório de trabalho.
```bash
git rm filename.txt
```

Exibe as modificações de um arquivo especifico, no caso do exemplo abaixo o `README.md`
```bash
git diff README.md
```

Envia todos os arquivos modificados para o stage.
```bash
git add .
```

Remove todos os arquivos que estão stage.
```bash
git reset 
```

Efetuar o commit das alterações que estão no stage.
```bash
git commit -m"Update variable STORE_PASS in .example.env" 
```

Envia para o repositório remoto os commits efetuados.
```bash
git push
```

Exibe todos os commits em ordem decrescente.
```bash
git log
```

Puxa toda as alterações que estão no repositório remoto.
```bash
git pull
```

Informa a branch atual com um (*), e lista todas que estão na sua maquina (repositório local).
```bash
git branch 
```

Limpa/Exclui todos as alterações efetuadas nos arquivos já existentes, alterando para o estado inicial da branch atual.
```bash
git checkout .
```

Cria uma branch (por default a partir da master), e aponta para ela.
```bash
git checkout -b feature/delete-user
```

Exclui uma branch local. (Não pode estar na mesma branch no ato da exclusão)
```bash
git branch -D feature/delete-user
```

Exclui uma branch remota.
```bash
git push origin --delete feature/delete-user
```

Acessar a branch master, e efetuar o merge utilizando squash
```bash
git checkout master 
git merge --squash feature/delete-user
```

Jogar os arquivos em uma branch temporaria
```bash
git stash
```

Recuperar os arquivos desta branch
```bash
git stash pop
```

Remover TODOS os arquivos desta branch temporaria
```bash
git stash clear
```
