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
