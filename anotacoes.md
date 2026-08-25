# Git e GitHub

# Seção 1: Introdução e instalação das dependências

### Git

Sistema de **controle de versão**: registra alterações no código e permite recuperar versões anteriores.

- Open Source
    
- Mantém histórico das alterações
    
- Facilita trabalho em equipe
    

### Instalação — Fedora

```bash
sudo dnf install git
git --version
```

---

# Seção 2: Git fundamental

### Repositório local

```bash
git init
```

Inicializa o Git na pasta e cria o diretório oculto `.git`.

```bash
git status
```

Mostra o estado atual dos arquivos.

Estados principais:

- **Untracked** → arquivo ainda não rastreado
    
- **Modified** → arquivo rastreado, mas alterado
    
- **Staged** → arquivo preparado para commit
    

### Staging

```bash
git add <arquivo>
git add .
```

Move arquivos para a **staging area**, preparando-os para o commit.

### Commit

```bash
git commit -m "mensagem"
```

Cria um ponto no histórico com as alterações staged.

```bash
git commit -a -m "mensagem"
```

Faz commit dos arquivos já rastreados que foram modificados/excluídos.

> `git commit` não envia nada para o GitHub. Apenas salva no histórico local.

---

## GitHub ↔ Repositório local

### Conectar repositório remoto

```bash
git remote add origin <URL>
```

Define o repositório do GitHub como remoto chamado `origin`.

### Enviar alterações

```bash
git push
```

Envia commits locais para o repositório remoto.

### Receber alterações

```bash
git pull
```

Baixa e integra alterações do repositório remoto.

### Clonar repositório

```bash
git clone <URL>
```

Cria uma cópia local de um repositório existente.

---

## Manipulação de arquivos

### Remover arquivo

```bash
git rm <arquivo>
```

Remove o arquivo e registra a remoção para o próximo commit.

### Mover / renomear

```bash
git mv <antigo> <novo>
```

Move ou renomeia um arquivo.

### Histórico

```bash
git log
```

Exibe o histórico de commits.

---

## Desfazer alterações

### Descartar alterações locais de um arquivo

```bash
git checkout -- <arquivo>
```

Restaura o arquivo para a versão do **último commit local**.

> Não significa necessariamente “versão atual do GitHub”.

### Resetar para o remoto

```bash
git reset --hard origin/main
```

Faz o branch local voltar exatamente ao estado de `origin/main`.

⚠️ **Cuidado:** descarta alterações locais não commitadas.

---

## .gitignore

Arquivo usado para informar ao Git quais arquivos/pastas devem ser ignorados.

Exemplo:

```gitignore
.env
node_modules/
pasta/*
```

- `.env` → ignora o arquivo `.env`
    
- `node_modules/` → ignora a pasta
    
- `pasta/*` → ignora o conteúdo da pasta
    

---

## Fluxo básico

```text
Modificar arquivo
      ↓
git status
      ↓
git add
      ↓
git commit
      ↓
git push
```

### Regra mental

**`add` → preparar**  
**`commit` → salvar no histórico**  
**`push` → enviar para o GitHub**  
**`pull` → trazer do GitHub**

# Seção 3: Trabalhando com branches

### Branch

Uma **branch é uma linha de desenvolvimento**, representada por uma referência a um commit.

- Permite desenvolver funcionalidades isoladamente.
    
- É comum criar uma branch para cada feature/fix.
    
- Depois, ela pode ser integrada à `main` com `merge`.
    

```bash
git branch
```

Lista as branches locais.

```bash
git branch <nome>
```

Cria uma branch, mas **não muda para ela**.

```bash
git checkout -b <nome>
```

Cria a branch e muda para ela.

> Alterações não commitadas pertencem ao **working tree**, não a uma branch específica. Ao trocar de branch, o Git pode levar essas alterações junto, desde que não haja conflito.

```bash
git branch -d <nome>
```

Deleta uma branch local já integrada.

```bash
git branch -D <nome>
```

Força a exclusão da branch.

```bash
git merge <branch>
```

Integra a branch indicada à **branch atual**.

---

### Git stash

```bash
git stash
```

Temporariamente guarda alterações não commitadas e limpa o working tree, permitindo trocar de branch sem fazer commit.

```bash
git stash list
```

Lista as stashes existentes.

```bash
git stash apply <stash>
```

Recupera uma stash **sem removê-la** da lista.

```bash
git stash pop
```

Recupera a stash mais recente e a remove da lista.

```bash
git stash show -p <stash>
```

Mostra as alterações armazenadas na stash.

```bash
git stash drop <stash>
```

Remove uma stash específica.

```bash
git stash clear
```

Remove todas as stashes.

> **Modelo mental:** `stash` = guardar temporariamente alterações para poder trabalhar em outro lugar.

---

## Tags

Uma **tag marca um commit específico**, normalmente para identificar versões ou pontos importantes do projeto.

```bash
git tag
```

Lista as tags.

```bash
git show <tag>
```

Mostra informações do commit marcado pela tag.

```bash
git tag -a <nome> -m "mensagem"
```

Cria uma **tag anotada** apontando para o commit atual (`HEAD`).

Exemplo:

```bash
git add .
git commit -m "Adiciona página inicial"
git tag -a v1.0 -m "Primeira versão"
```

> ⚠️ **Tag não salva alterações.** Ela apenas marca um commit que já existe.

### Trocar para uma tag

```bash
git checkout <tag>
```

Coloca o repositório no estado daquele commit.

> ⚠️ Ao fazer checkout diretamente de uma tag, você fica em **detached HEAD**. Não está em uma branch.

### Enviar tags para o GitHub

```bash
git push origin <tag>
```

Envia uma tag específica.

```bash
git push origin --tags
```

Envia todas as tags.

---

## Regra mental

```text
Branch → linha de desenvolvimento
Stash  → guardar alterações temporariamente
Tag    → marcar um commit
```