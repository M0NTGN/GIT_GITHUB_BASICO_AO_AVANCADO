# Seção Extra: Alterando mensagens e reescrevendo histórico

## Alterar a mensagem do último commit

```bash
git commit --amend -m "nova mensagem"
```

Altera a mensagem do **último commit**.

> Também pode alterar o conteúdo do último commit.

---

## Alterar mensagens de commits anteriores

```bash
git rebase -i HEAD~N
```

Abre os últimos `N` commits para edição.

Exemplo:

```text
pick abc123 primeiro commit
reword def456 segunda mensagem
pick ghi789 terceira mensagem
```

Troque `pick` por `reword` no commit cuja mensagem deseja alterar.

> `reword` = alterar apenas a mensagem do commit.

---

## Alterar também o primeiro commit

O primeiro commit não possui um commit anterior (`HEAD~N`), então use:

```bash
git rebase -i --root
```

Permite editar o histórico desde o **primeiro commit**.

---

## Histórico após o rebase

O Git **reescreve os commits**, criando novos commits com novos identificadores.

```text
Antes:
A → B → C

Depois:
A' → B' → C'
```

> ⚠️ Mesmo alterando apenas a mensagem, o hash do commit muda.

---

## Enviar o histórico reescrito

Se os commits já foram enviados ao GitHub, um `git push` normal pode ser rejeitado.

Use:

```bash
git push --force-with-lease
```

Atualiza o repositório remoto substituindo o histórico antigo pelo novo.

> ⚠️ `--force-with-lease` pode sobrescrever histórico remoto. Evite fazer isso em branches compartilhadas sem verificar antes.

---

## Fluxo completo

```text
Alterar mensagem
      ↓
git rebase -i HEAD~N
      ↓
reword
      ↓
Salvar nova mensagem
      ↓
Histórico local reescrito
      ↓
git push --force-with-lease
```

### Regra mental

```text
Último commit
→ git commit --amend

Commits anteriores
→ git rebase -i HEAD~N

Primeiro commit
→ git rebase -i --root

Histórico já enviado
→ git push --force-with-lease
```
