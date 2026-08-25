# Curso de Git e GitHub: Do Básico ao Avançado

Repositório dedicado ao armazenamento de anotações, resumos e comandos práticos realizados durante o curso de Git e GitHub. O objetivo deste projeto é servir como um guia de consulta rápida e profissional para fluxos de trabalho com controle de versão.

---

## 📚 Sumário das Anotações

1. [Introdução e Instalação](./01-introducao-e-instalacao-de-dependencias.md)
2. [Git Fundamental](./02-git-fundamental.md)
3. [Trabalhando com Branches](./03-branches.md)
4. [Compartilhamento e Atualização](./04-compartilhamento-e-atualizacao-de-repositorio.md)
5. [Análise e Inspeção](./05-analise-e-inspecao-de-repositorio.md)
6. [Administração de Repositório](./06-administrando-repositorio.md)
7. [Melhorando Commits e Rebase](./07-melhorando-commits-do-projeto.md)
8. [GitHub (Issues, PRs, Actions)](./08-github.md)
9. [Markdown](./09-markdown.md)
10. [GitHub Pages](./10-github-pages.md)
11. [Deploy de Sites Estáticos](./11-como-hospedar-site-fazendo-deploy.md)
---
99. [Extra: Renomear Commits](./99-extra-renomear-commits.md)
99.1. [Extra: Divergências e Push Force](./99.1-extra-verificando-divergencias-e-forcando-push.md)

---

# Padronização do projeto


## Branches

| Prefixo     | Uso                                 |
| ----------- | ----------------------------------- |
| `feature/`  | Nova funcionalidade                 |
| `fix/`      | Correção de bug                     |
| `docs/`     | Documentação                        |
| `refactor/` | Refatoração sem mudar comportamento |
| `test/`     | Testes                              |
| `chore/`    | Manutenção/configuração             |

### Exemplo

```bash
git checkout -b feature/user-login
```

## Commits

Formato:

```text
tipo: descrição curta
```

| Tipo       | Quando usar             |
| ---------- | ----------------------- |
| `feat`     | Nova funcionalidade     |
| `fix`      | Correção de bug         |
| `docs`     | Documentação            |
| `refactor` | Refatoração             |
| `test`     | Testes                  |
| `chore`    | Manutenção/configuração |

### Regras

* Usar letras minúsculas
* Não usar ponto final
* Usar verbo no presente
* Manter a descrição curta

### Exemplos

```text
feat: adiciona autenticação
fix: corrige validação de email
docs: adiciona anotações sobre branches
refactor: reorganiza serviço de usuários
```
