# Git & GitHub - Guia Completo para Desenvolvedores

> Um guia prático e detalhado para aprender Git e GitHub do zero até um nível profissional.

---

# Sumário

- O que é Git
- O que é GitHub
- Instalação
- Configuração Inicial
- Conceitos Fundamentais
- Criando um Repositório
- Commits
- Histórico
- Trabalhando com GitHub
- Clonando Repositórios
- Atualizando Projetos
- Branches
- Merge
- Pull Requests
- Git Flow
- Corrigindo Erros
- Git Ignore
- Boas Práticas
- Fluxo de Trabalho Profissional
- Comandos Mais Importantes

---

# O que é Git?

Git é um sistema de controle de versão distribuído criado para rastrear alterações em arquivos e permitir que várias pessoas trabalhem no mesmo projeto sem perder histórico.

Com Git você pode:

✅ Salvar versões do projeto

✅ Voltar para versões anteriores

✅ Trabalhar em equipe

✅ Comparar alterações

✅ Criar novas funcionalidades isoladas

✅ Recuperar código perdido

---

# O que é GitHub?

GitHub é uma plataforma que hospeda repositórios Git na nuvem.

Pense da seguinte forma:

```text
Git
↓
Controla versões

GitHub
↓
Hospeda projetos Git
```

O Git funciona sem o GitHub.

O GitHub utiliza Git.

---

# Instalação

## Verificar Instalação

```bash
git --version
```

Exemplo:

```bash
git version 2.50.1
```

---

# Configuração Inicial

## Configurar Nome

```bash
git config --global user.name "Seu Nome"
```

Exemplo:

```bash
git config --global user.name "Gadiel Caminos"
```

---

## Configurar E-mail

```bash
git config --global user.email "seuemail@gmail.com"
```

---

## Ver Configurações

```bash
git config --list
```

---

# Conceitos Fundamentais

## Repositório

Pasta controlada pelo Git.

Exemplo:

```text
bereiando/
```

Transformar em repositório:

```bash
git init
```

---

## Working Directory

São os arquivos que estão sendo editados.

```text
index.html
style.css
script.js
```

---

## Staging Area

Área intermediária onde os arquivos ficam preparados para commit.

Adicionar arquivos:

```bash
git add .
```

---

## Commit

Um commit é uma fotografia do estado atual do projeto.

```bash
git commit -m "Cria página inicial"
```

Visualização:

```text
Commit 1
    ↓
Commit 2
    ↓
Commit 3
```

---

# Criando um Projeto do Zero

Criar pasta:

```bash
mkdir meu-projeto
```

Entrar na pasta:

```bash
cd meu-projeto
```

Inicializar Git:

```bash
git init
```

Adicionar arquivos:

```bash
git add .
```

Criar commit:

```bash
git commit -m "Primeiro commit"
```

---

# Verificando Alterações

## Status do Projeto

```bash
git status
```

Resultado:

```text
modified: index.html
new file: style.css
```

---

# Adicionando Arquivos ao Stage

Adicionar tudo:

```bash
git add .
```

Adicionar arquivo específico:

```bash
git add index.html
```

---

# Criando Commits

Exemplo:

```bash
git commit -m "Adiciona sistema de busca"
```

Outro exemplo:

```bash
git commit -m "Corrige layout mobile"
```

---

# Histórico de Commits

Completo:

```bash
git log
```

Resumido:

```bash
git log --oneline
```

Exemplo:

```text
a8b913f Corrige layout mobile
5d9f221 Adiciona sistema de busca
1f324ab Primeiro commit
```

---

# Criando Repositório no GitHub

1. Entrar no GitHub
2. Clicar em New Repository
3. Escolher o nome
4. Criar repositório

---

# Conectando Projeto ao GitHub

```bash
git remote add origin https://github.com/usuario/repositorio.git
```

Verificar:

```bash
git remote -v
```

---

# Primeiro Push

```bash
git branch -M main

git push -u origin main
```

---

# Push Futuro

Após o primeiro envio:

```bash
git push
```

---

# Clonando Repositórios

Baixar repositório existente:

```bash
git clone https://github.com/usuario/repositorio.git
```

Exemplo:

```bash
git clone https://github.com/cdgadielsantos-stack/Bereiando.git
```

---

# Atualizando Projeto Local

Buscar alterações do GitHub:

```bash
git pull
```

---

# Branches

Branch é uma linha independente de desenvolvimento.

Exemplo:

```text
main
 │
 ├── login
 ├── busca
 └── cadastro
```

---

# Criar Branch

```bash
git checkout -b login
```

ou

```bash
git switch -c login
```

---

# Ver Branches

```bash
git branch
```

---

# Trocar de Branch

```bash
git checkout main
```

ou

```bash
git switch main
```

---

# Merge

Une alterações de uma branch.

Exemplo:

```bash
git checkout main

git merge login
```

Resultado:

```text
main + login
```

---

# Pull Request

Fluxo profissional:

```text
Criar Branch
      ↓
Fazer Alterações
      ↓
Push
      ↓
Pull Request
      ↓
Revisão
      ↓
Merge
```

---

# Git Flow

Modelo utilizado por equipes.

```text
main
 │
 ├── develop
 │
 ├── feature/login
 ├── feature/cadastro
 ├── feature/busca
 │
 ├── release
 │
 └── hotfix
```

---

# Corrigindo Erros

## Remover Alterações Não Salvas

```bash
git restore .
```

---

## Remover Arquivo do Stage

```bash
git restore --staged arquivo.txt
```

---

## Ver Diferenças

```bash
git diff
```

---

## Voltar para Commit Específico

Ver commits:

```bash
git log --oneline
```

Voltar:

```bash
git reset --hard HASH
```

Exemplo:

```bash
git reset --hard a8b913f
```

⚠ Atenção: remove alterações posteriores.

---

# Arquivo .gitignore

Serve para ignorar arquivos.

Exemplo:

```gitignore
node_modules
.env
.next
dist
coverage
.vscode
```

---

# Estrutura Recomendada para Projetos

```text
projeto/
│
├── assets
│
├── src
│
├── docs
│
├── tests
│
├── README.md
│
├── LICENSE
│
└── .gitignore
```

---

# Boas Práticas

## Commits Pequenos

Ruim:

```bash
git commit -m "mudanças"
```

Bom:

```bash
git commit -m "Implementa busca por livros"

git commit -m "Cria página de autores"

git commit -m "Corrige menu mobile"
```

---

## Commite com Frequência

Não espere finalizar tudo.

Faça commits sempre que concluir uma tarefa.

---

## Sempre Verifique Antes

```bash
git status
```

---

## Mantenha README Atualizado

Explique:

- O projeto
- Tecnologias
- Como instalar
- Como executar

---

# Fluxo de Trabalho Diário

Antes de começar:

```bash
git pull
```

Depois das alterações:

```bash
git status

git add .

git commit -m "Descrição da alteração"

git push
```

---

# Fluxo Completo Profissional

```text
Git Pull
    ↓
Criar Branch
    ↓
Desenvolver
    ↓
Git Add
    ↓
Git Commit
    ↓
Git Push
    ↓
Pull Request
    ↓
Code Review
    ↓
Merge
```

---

# Comandos Mais Importantes

```bash
git init

git status

git add .

git commit -m "mensagem"

git log --oneline

git branch

git checkout

git checkout -b

git switch

git merge

git remote -v

git clone

git pull

git push

git diff

git restore

git reset
```

---

# Resumo para Decorar

O fluxo mais importante do Git é:

```bash
git status

git add .

git commit -m "Descrição da alteração"

git push
```

Se você dominar esse fluxo e entender branches, commits e pull requests, já terá conhecimento suficiente para trabalhar em projetos pessoais, colaborar em equipes e manter aplicações profissionais como o projeto Bereiando.
