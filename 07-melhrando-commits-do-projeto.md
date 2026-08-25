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