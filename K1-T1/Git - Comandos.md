# K1-T1 - GIT

[](K1-T1%20-%20GIT%20af1583e9dbda4701ac389b56d269d42d/Untitled%2012ac205321074b8cba7f656fe8fac74a.md)

Versionamento de Código + Anotações.

- ----------------------Comando usados até agora:---------------------------

# [git init](https://github.com/joaocanuto/Repositorio-GetStarted--K1-T1-)

```
inicializa o repositório.

```

# git add

```
adiciona uma pasta/arquivo ao git.
Serve para trackear as ações de modificação da pasta.

## git add .. // git add --all // git add -A
	adiciona todos os arquivos sobre o guarda chuva do git

```

# git diff

```
mostra as alterações nos arquivos, antes do staged.
## git diff --cached // git diff --staged
	mostra as alterações nos arquvis, antes do commit.

```

# git log

```
mostra as alterações da mais recente pra mais antiga.
o id de cada commit é um sha.
HEAD -> aponta sempre para a ultima modificação em uma branch.

## git log --oneline
	mostra as modificações em apenas uma linha.

```

# git checkout 'chave_sha'

```
ele ira retornar os arquivos para aquela versao
para voltar para a principal basta:

## git checkout master
	aqui ele volta o head para a ultima alteração do projeto.

## git checkout 'arquivo'
	volta para a ultima versão do arquivo antes de ser modified.

## git reset --hard
	volta ao estado inicial, no seu ultimo commit, desfazendo todas as mudanças.

```

# git clean -f

```
ele força a remoção de arquivos adicionados ao repositorio.
se jogarmos paa a area de preparação, usamos o:

## git reset --hard
	ele ira apagar a modificação ate o staged.

```

- --- arquivos que eu quero que o git ignore ----
1. criando a .gitignore.txt
2. já nela podemos:
¨teste.bmp
-> ignora apenas o arquivo teste.bmp
¨*.bmp
-> ignora todos os arquivos .bmp
¨pasta/*.bmp
-> todos os arquivos .bmp, dentro do caminho pasta.
3. [https://github.com/github/gitignore](https://github.com/github/gitignore)
- ---- clonando repositorios ----
1. clonar os repositorios
2. fazer modificações

#git clone /caminho-da-pasta pasta-de-destino

ou

#git clone URL-GitHub

- ----- Modificações no GitHub ---------

#git push
envia para o servidor
#git pull
recebe do servidor

- ----- GitHub - Star, Folk e Pull Request -------

Star - favoritar um projeto, ele ficara no seu acesso rápido.

Watch - Notifica as alterações do projeto.

Fork - Clona um projeto de outro perfil, para o seu.

~ Podemos clonar projetos de outras pessoas, mas nao poderemos dar push's
~ Apos clonarmos o projeto de terceiro para o nosso github poderemos fazer push normalmente.

Pull Request - ( Fazer uma contribuição e Contribuir para o projeto principa )
- fiz um Fork
- Clonei o projeto do meu perfil
- Fiz modificações
- Fiz um Push para o meu repositorio
- Apos isso, posso sugerir as mudanças que eu fiz no repositorio clonado, para o repositorio original.
~Isso so acontece se eu posso fazer um Merge(União) entre as modificações.

- ---------- GitHub : Issues, milestones, labels -----

~ Na aba Issues dos projetos, você pode sugerir erros dentro dos arquivos.

Labels - Pra voce conseguir marcar (tag'ar) as Issues do projeto. (Isso só os proprietários do projeto pode marcar).

Milestones - Planejamento para resolver os erros. Você pode selecionar pra qual versão o seu projeto irá corrigir o problema.

~Quando você tenta dar um pull request que resolve um problema voce pode usar palavras chaves para associar seu commit ao issue usando a 'Close #(numero do issue)'.
~~Quando voce dar um pull request resolvendo o problema, e o proprietário aceita a pull, o problema issue já sai da lista de issues.

~ [Readme.md](http://readme.md/) : [https://dillinger.io/](https://dillinger.io/)

- ----- Branch -------
- Ramificações do projeto.
Permite que voce crie funcionalidades para o projeto sem interferir nas funcionalidades que já existem.

# git branch

```
lista as branchs existentes

```

# git branch 'nome-da-branch'

```
cria uma branch com o nome desejado.

```

# git checkout develop

```
muda para a branch develop

```

# git chechout -b TASK-1

```
cria e acessa a branch TASK-1

```

~ Enviando branch's para o servidor:

#git push -u origin develop

~ Com isso podemos trabalhar em projetos com varias pessoas, criando nossas ramificações e realizando apenas as alterações necessárias ao projeto.

~ Removendo branch's locais

#git branch -d 'Nome da branch'

~ Forçando a remoção

#git branch -D 'Nome da branch'

~ Remoção de uma branch do servidor

#git push --delete origin 'Nome da branch'

~ Renomeando uma branch

#git branch -m 'Novo nome' (se voce já estiver na branch que voce quer trocar de nome)

#git branch -m 'Nome-da-branch' 'Novo-nome-da-branch'

$$$$ Renomeando no servidor $$$$--------------------------

1. Recebendo as ultimas mudanças do código

# git pull

1. enviando a branch pro servidor ( caso ela ainda nao exista)

#git push -u origin TESTE

1. Pegando as ultimas alterações do servidor

#git pull

1. Alterando o nome da branch

#git branch -m TESTE TESTE-NOVO

1. Apago a branch TESTE do servidor

#git push --delete origin TESTE

1. Envio a TESTE-NOVO pro servidor

#git push -u origin TESTE-NOVO

- --------- MESCLANDO ALTERAÇÕES ----------
~ Aqui voce vai mesclar as alterações de branchs diferentes

~ Sempre mesclamos para a branch que eu estou

#git merge 'develop'

~ Ele executa se acontesse sem erros.

- -- Se Der erro ? -----

Ele ira dar conflito quando ?
Você alterar no servidor e no seu, 'coisas iguais' (linhas, etc) e quando voce der um push para o servidor. Logo apos isso, voce precisara dar um:

# git pull

Arrumar o arquivo e em seguido seguir os passos naturais para dar um git push novamente.

#git add .
#git commit -m ''
#git push

~Se voce for começar uma alteração, git pull
~Se voce for enviar alterações, git pull

Por exemplo: Voce tem no seu pc 2 clones do servidor um que é igual ao que esta lá e outro que é o que voce esta trabalhando.
Quando voce vai dar up nas suas modificações, voce primeiro as acrescenta no seu servidor(local) antes de ir pro servidor mesmo. E é ai onde pode dar erro.

# kdiff3 - Resolução de conflitos Graficamente

### Instalation:

```bash
sudo apt-get install kdiff3
```

### Como usar:

1) Configurar o comando Mergetool

<aside>
💡 Mergetool : Ferramenta do git pra visualizar suas ferramentas gráficas

</aside>

```bash
git mergetoll
#faz com que as ferramentas gráficas sejam abertas baseadas nas config do git
#visualizando as ferramentas já configuradas:
git config --global --list
#configurando a ferramenta:
git config --global --add merge.tool kdiff3
git config --global --add merge.tool.kdiff3.path /usr/bin/kdiff3
git config --global --add merge.tool.kdiff3.trustExitCode false
```

2) Testando : Criaremos um erro: 

```bash
# a situação que temos um que mergiar e da erro:
git merge develop # aqui estamos na master
git mergetool #ira abrir o kdiff3 
# apos aplicarmos as alterações que precisamos, basta fazer o padrão 
git add .
git commit -m 'Resolvendo conflitos' 
```

## Pull Request

1) Pra começar eu preciso primeiro ter uma mudança no meu site.

2) Requisição de mudanças que você cria. Você pede que mudança de uma branch, seja integrada em outra branch.

3) Ele acontece quando você faz uma alteração no projeto, por uma branch diferent , e resolve commitar para o servidor. A partir dai, ok. O que acontece posteriormente é que é permitido que servidor incremente as alterações do seu commit para a branch principal.  Você pode deletar a branch apos o pull request.

## Tag : um ponteiro que marcar um dos commits.

<aside>
💡 Ela pode marcar qualquer commit. Alguns commit são chave durante o projeto. Você precisa marcar versões que serão uteis ao longo do tempo.

</aside>

1) Quando você estiver com diversos commits feitos, e for necessário voltar a commits fundamentais, as tagss ajudarão.

```bash
git tag -a 'nome-da-tag' -m "mensagem-da-tag" 
#criando a tag
git tag 
#lista a tag
git push origin "nome-da-tag" 
#enviando para o servidor
```

2) Usando Tags : 

```bash
git checkout v0.1
#entrando na v0.1
## modifico o arquivo
git status 
git add .
git commit -m 'Modificações a partir da tag'
# aqui eu modifiquei o arquivo, commitei, na tag v0.1.
#se eu sair dela as alterações serao perdidas: 
git checkout main
git branch 
git tag 
git status 
#você vera que as atualizações sumiram

```

3) A gente pode usar commits anteriores e usar branchs a partir deles:

4) Quando você fez esses passos, você ira notar que aós o git checkout main, você ira receber um codigo sha do seu commit na tag e você pode criar uma branch a partir dele.

```bash
git checkout -b teste 69b475b 
```

5) Você pode sair dessa branch teste e apaga-lá

```bash
git branch -D teste
```

Então você pode criar uma branch e desenvolver a partir dela.

### Removendo tags locais e no servidor

```bash
git tag -d 'nome-da-tag'
#removendo local
git push --delete origin 'nome-da-tag'
#removendo no servidor
```

### Tags em commits específicos:

1) 1º maneira: 

```bash
git log --online
git checkout e8e51dd
#aqui você vai pro commit desse sha
git tag -a v0 -m "versão inicial" 
#voce cria uma tag v0 no commit que você esta.
git push origin v0
#envio pro servidor
```

2) 2º maneira:

```bash
git tag -a v1 369b496 
#voce precisara escrever uma mensagem para a tag.
```

## Stash

### Como usar :

Quando voce esta trabalhando em algo e precisa verificar alterações em outras branch’s e outras verificações, e fazer até um merge.

```bash
#salva as mudanças que você fez:
git stash
#visualiza as mudanças salvas
git stash list
#voce pode acrescentar alguma mensagem ao stash
git stash save "testando stash" 
```

```bash
git stash apply
#sempre pega o primeiro e executa a alteração no meu projeto
git stash pop
#aplica o stash mais recente e já remove da lista
```

Se você quiser remover stash anteriores ao último, sem perder o último,  basta: 

```bash
git stash drop stash@{1}
#Aqui ele apaga um stash específico
git stash pop stash@{0} 
#Aqui ele já aplica e remove o stash especifico
```

## Reverter commits:

```bash
git reset --hard HEAD~*N
#N = numero de commits que voce ira perder as alterações.
# N = 1 : desfaz o ultimo commit*
git reset --hard HEAD~1
**
```

No servidor nos teriamos que versionar uma alteração por cima. 

Se você desejar alterar apenas um detalhe, apos já ter feito um commit.

<aside>
💡 Caso voce precise adicionar uma alteração a algo que você ja commitou: (na area local)

</aside>

```bash
git add .
#aqui o commit ainda esta na sua área local:
git commit --amend
#aqui ele adiciona as alterações ao seu ultimo commit
```

## Fetch

Ele é executo junto com o comando merge, na execução do git pull:

O comando git pull  = git fetch + git merge.

Ele verifica as atualizações encontradas no servidor. 

Aqui a ideia é a seguinte: 

Existe uma branch no seu repositório que nao existo no seu local, e então voce quer agrega-lá ao seu local sem trazer as alterações do repositorio. Voce quer simplesmente as a branch, sem aplicar as alterações do seu repositorio. 

```bash
git fetch 
git checkout "nome-da-branch-que-atualizou"
```

Quando você realiza alguma alteração no servidor e usa o git fetch pra trazer as alterações elas ficaram localizadas na branch : ***origin/”nome-da-branch-que-voce-atualizou”***

Para voce aplicar essa alteração:

```bash
git merge
```

Basicamente você realizou um git pull

### Em que situações você pode usar:

Caso você queira ver as alterações que serão feitas, o git fetch é mais recomendado. (Em projetos mais sensiveis e delicados) 

## Rebase

![Untitled](K1-T1%20-%20GIT%20af1583e9dbda4701ac389b56d269d42d/Untitled.png)

![Untitled](K1-T1%20-%20GIT%20af1583e9dbda4701ac389b56d269d42d/Untitled%201.png)

### Conceitos:

Fast Foward - É quando ele consegue pegar os commits de uma branch e ja implementar diretamente na que ta fazendo merge. 

Rebase - É quando você quer tornar uma arvore linear. Ele pega os commits de uma branch e aplica em outra.  

Como usar: 

1) Vá para a branch secundaria:

```bash
git checkout second 
git rebase main
#aplicando na second os commits que tem na main. 
git checkout main
git rebase second
#aplicando na main os commits que tem na second.
#Isso é basicamente fazer um merge! 
```

 

## Alias : Abreviação de comandos

*git status = git s*

```bash
git config --global alias.s status
#como deletar ? 
git config --global --unset alias.s
```

## Verificando aonde esse repositório ta apontando ?

Quando voce quer saber aonde seu projeto ta linkado.

```bash
git remote -v
```

## Grep : Quais branchs/tags posso remover ?

Listando/Filtrando branchs.

```bash
git branch | grep feature
#ele ira listar todas as branchs com feature no nome 
git tag | grep 1
#ele ira listar todas as tags com 1 no nome
```
