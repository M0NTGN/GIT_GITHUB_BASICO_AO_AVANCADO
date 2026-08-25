# Seção 07: Melhorando commits do projeto

### Git rebase interativo

```bash
git rebase -i HEAD~N
```

Permite **reorganizar, juntar, renomear ou remover** commits recentes antes de compartilhá-los.

Ações principais:

```text
pick   → mantém o commit
reword → altera a mensagem
squash → junta ao commit anterior
fixup  → junta ao anterior e descarta a mensagem
drop   → remove o commit
```

Exemplo:

```text
pick a1b2c3 adiciona login
squash d4e5f6 corrige login
reword g7h8i9 ajusta mensagem
```

> Usado principalmente para **limpar o histórico da própria branch** antes de compartilhá-la.

### Regra mental

```text
rebase -i → organizar commits
merge     → integrar branches
```

> ⚠️ Rebase reescreve o histórico. Evite usá-lo em branches compartilhadas sem saber o impacto.

---

### Git cherry-pick

```bash
git cherry-pick <hash-do-commit>
```

Copia um commit específico de uma branch e o aplica na branch atual. Útil para trazer correções urgentes sem fazer o merge de toda a branch original.

---

### Tipos de Merge

O Git decide como integrar as branches baseando-se no histórico:

- **Fast-forward:** Quando a branch de destino não tem novos commits. O ponteiro apenas "anda para frente".
- **3-way merge:** Quando ambas as branches divergiram. O Git cria um **Merge Commit** para unir os históricos.

#### Forçar merge commit
```bash
git merge --no-ff <branch>
```
Garante que um commit de merge seja criado, mesmo que um fast-forward seja possível (mantém o histórico da branch mais visível).

#### Permitir apenas fast-forward
```bash
git merge --ff-only <branch>
```
O merge falha se não for possível apenas "adiantar" o ponteiro (ajuda a manter histórico linear).