# Seção 6: Administração de repositórios

### Git clean

```bash
git clean -f
```

Remove arquivos **untracked** do **working tree**.

> ⚠️ Não remove arquivos commitados. Use `git clean -n` para visualizar o que será removido antes.

```bash
git clean -fd
```

Também remove diretórios untracked.

> **Atua no working tree, não em uma branch específica.**

---

### Git garbage collection

```bash
git gc
```

Faz manutenção no repositório, otimizando objetos Git e podendo remover objetos que não são mais necessários.

> **Atua no repositório Git, não apenas na branch atual.**

**GC** = *Garbage Collection*.

---

### Git fsck

```bash
git fsck
```

Verifica a **integridade e conectividade dos objetos Git**, identificando problemas ou objetos inacessíveis.

**FSCK** = *File System Consistency Check*.

> **Atua no banco de objetos do repositório.**

---

### Git reflog

```bash
git reflog
```

Registra movimentos das **referências locais**, como `HEAD` e branches.

Útil para recuperar commits após operações como `reset`, `rebase` ou mudanças de branch.

> O reflog é **local** e suas entradas expiram conforme as configurações do Git.

---

### Git archive

```bash
git archive --format=zip --output=main_files.zip main
```

Cria um arquivo compactado com o **snapshot da referência `main`**.

> Não inclui o diretório `.git` nem o histórico de commits.

---

### Regra mental

```text
git clean   → limpar working tree
git gc      → manutenção dos objetos
git fsck    → verificar integridade
git reflog  → recuperar movimentos das referências
git archive → exportar snapshot
```

### Branch × Repositório

```text
git clean
    ↓
Working tree atual

git gc
git fsck
    ↓
Repositório / objetos Git

git reflog
    ↓
Referências locais

git archive main
    ↓
Snapshot da main
```
