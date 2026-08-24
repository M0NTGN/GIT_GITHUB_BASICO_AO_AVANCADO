# Git e GitHub

## Seção 1: Introdução e instalação

### Git

Sistema de **controle de versão**: registra alterações no código e permite recuperar versões anteriores.

* Open Source
* Mantém histórico das alterações
* Facilita trabalho em equipe

### Instalação — Fedora

```bash
sudo dnf install git
git --version
```

---

## Seção 2: Git fundamental

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

* **Untracked** → arquivo ainda não rastreado
* **Modified** → arquivo rastreado, mas alterado
* **Staged** → arquivo preparado para commit

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

* `.env` → ignora o arquivo `.env`
* `node_modules/` → ignora a pasta
* `pasta/*` → ignora o conteúdo da pasta

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
