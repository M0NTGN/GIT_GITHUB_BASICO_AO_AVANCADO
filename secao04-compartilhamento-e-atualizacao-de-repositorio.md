# Seção 4: Compartilhamento e atualização de repositórios

### Git fetch

```bash
git fetch --all
```

Atualiza as referências dos repositórios remotos sem alterar a branch atual.

Exemplo:

```text
GitHub
  ↓
git fetch
  ↓
origin/main
origin/feature-x
```

> **`fetch` baixa informações; não integra automaticamente na branch atual.**

### Git pull

```bash
git pull
```

Atualiza a branch atual com alterações do remoto.

> **`pull` = `fetch` + integração**

### Fluxo de trabalho

```text
Dev 1 → Branch A
   ↓
Commit + Push
   ↓
Merge → Main
   ↓
Dev 1 volta para Main
   ↓
git pull
```

### Git push

```bash
git push
```

Envia **commits locais** para o repositório remoto.

### Git remote

```bash
git remote add origin <URL>
```

Conecta o repositório local a um repositório remoto.

```bash
git remote rm origin
```

Remove o remoto chamado `origin`.

### Git submodule

```bash
git submodule add <URL>
```

Adiciona outro repositório dentro do projeto como um **submódulo independente**.

```bash
git push --recurse-submodules=on-demand
```

Faz o push dos submódulos necessários caso seus commits ainda não estejam disponíveis no remoto.

---

### Regra mental

```text
fetch   → atualizar referências
pull    → trazer + integrar
push    → enviar commits
remote  → gerenciar conexão com remoto
submodule → projeto dentro de outro projeto
```
