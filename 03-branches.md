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
git branch -m <novo-nome>
```

Renomeia a branch **atual**.

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