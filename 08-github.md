# Seção 08: GitHub

GitHub é a plataforma que reúne **código, colaboração, planejamento, revisão e automação** do projeto.

### Modelo mental

```text
Code       → código
Issues     → trabalho a fazer
Pull Request → mudança proposta
Projects   → organização do trabalho
Actions    → automação
Wiki       → documentação complementar
Insights   → métricas e informações
Settings   → configuração
```

---

# Code

É a área principal do repositório: código, branches, commits, arquivos e histórico.

## Boas práticas

* `main` deve representar código estável.
* Evitar trabalhar diretamente na `main` quando houver revisão.
* Usar branches para mudanças isoladas.
* Commits pequenos e com propósito claro.
* README deve explicar o projeto.
* `.gitignore` deve evitar arquivos desnecessários ou sensíveis.

### Fluxo profissional

```text
Issue
  ↓
Branch
  ↓
Alterações
  ↓
Commit
  ↓
Push
  ↓
Pull Request
  ↓
Review / CI
  ↓
Merge
  ↓
Main
```

### Padronização

**Branches**

```text
feature/<nome>
fix/<nome>
docs/<nome>
refactor/<nome>
test/<nome>
chore/<nome>
```

**Commits**

```text
tipo: descrição curta
```

Exemplo:

```text
feat: adiciona autenticação
fix: corrige validação de email
docs: atualiza readme
```

---

# Issues

Issue representa **algo que precisa ser feito, discutido ou acompanhado**.

Pode representar:

* Bug
* Nova funcionalidade
* Tarefa
* Melhoria
* Ideia
* Investigação

GitHub permite também usar assignees, labels, milestones, sub-issues, dependências e Projects para organizar o trabalho.

## Preciso de Issues em projeto solo?

**Não é obrigatório.**

Para projetos muito pequenos:

```text
ideia → código → commit
```

pode ser suficiente.

Para projetos que precisam de organização:

```text
Issue → desenvolvimento → PR → fechamento
```

é mais útil.

### Vale usar Issue quando:

* o trabalho tem mais de uma etapa;
* existe uma tarefa futura;
* você quer registrar um bug;
* você quer acompanhar uma funcionalidade;
* você quer deixar histórico do motivo de uma mudança.

### Não use Issue para:

* registrar cada alteração mínima;
* substituir commits;
* criar burocracia sem necessidade.

---

## Como criar uma boa Issue

### Estrutura

```markdown
## Objetivo

Descrever o que precisa ser feito.

## Contexto

Por que isso é necessário?

## Critérios de conclusão

- [ ] Item 1
- [ ] Item 2
- [ ] Item 3
```

### Exemplo

```markdown
# Adicionar validação de login

## Objetivo

Impedir login quando email ou senha forem inválidos.

## Critérios de conclusão

- [ ] Validar email
- [ ] Validar senha
- [ ] Exibir mensagem de erro
- [ ] Criar testes
```

### Regra mental

```text
Issue → o que precisa acontecer
Commit → o que foi alterado
Pull Request → como a alteração será integrada
```

---

# Pull Requests

Pull Request (PR) é uma **proposta para integrar alterações de uma branch em outra**.

Normalmente:

```text
feature/login
      ↓
Pull Request
      ↓
main
```

GitHub usa Pull Requests para propor, discutir, revisar e mesclar alterações.

## Quando usar?

Principalmente quando:

* existe outra pessoa revisando;
* a mudança precisa ser validada;
* o projeto usa CI;
* a alteração deve passar por aprovação antes do merge.

Em projeto solo, também pode ser útil para praticar o fluxo profissional.

---

## Bom Pull Request

Um PR deve responder:

```text
O que mudou?
Por que mudou?
Como foi testado?
```

### Exemplo

```markdown
## O que foi alterado?

Adicionada autenticação de usuários.

## Por quê?

Permitir acesso somente a usuários autenticados.

## Testes

- Login válido
- Senha inválida
- Email inválido
```

### Boas práticas

* PR pequeno o suficiente para ser revisado.
* Uma finalidade principal por PR.
* Relacionar Issue quando existir.
* Descrever testes realizados.
* Não misturar refatoração gigantesca com feature sem necessidade.
* Corrigir feedback no próprio PR.

### Fluxo

```text
Issue
  ↓
Branch
  ↓
Commit
  ↓
Push
  ↓
PR
  ↓
Review / CI
  ↓
Correções
  ↓
Merge
```

### Regra mental

```text
Branch → onde desenvolvo
PR     → proponho a mudança
Review → verifico a mudança
Merge  → integro a mudança
```

---

# GitHub Actions

GitHub Actions permite automatizar tarefas através de **workflows** acionados por eventos do repositório. Pode ser usado para build, testes, lint, segurança, deploy e outras automações.

## Workflow

Um workflow define:

```text
Quando executar?
      ↓
Qual máquina?
      ↓
Quais passos?
```

Exemplo conceitual:

```text
Push / Pull Request
        ↓
Instalar dependências
        ↓
Rodar lint
        ↓
Rodar testes
        ↓
Build
```

## CI

**Continuous Integration**

Integração contínua: alterações são verificadas automaticamente através de processos como build, testes, lint e verificações de segurança.

Exemplo:

```text
Pull Request
    ↓
GitHub Actions
    ↓
Testes
    ↓
✅ passou
❌ falhou
```

## CD

**Continuous Deployment**

Automatiza a publicação/deploy da aplicação após os critérios definidos serem atendidos. CI/CD geralmente conecta build, testes e implantação automatizados.

Exemplo:

```text
Push
 ↓
Build
 ↓
Testes
 ↓
Deploy
 ↓
Produção
```

### Projeto solo

Comece simples:

```text
Pull Request
     ↓
testes
     ↓
build
```

Depois adicione deploy.

### Regra mental

```text
Actions → fazer o computador executar tarefas automaticamente
CI      → verificar alterações
CD      → entregar/publicar alterações
```

---

# Projects

GitHub Projects é usado para **planejar e acompanhar o trabalho**, podendo conectar Issues e Pull Requests. GitHub recomenda usar campos, visualizações, automações e uma fonte central de acompanhamento.

## Kanban

Uma estrutura simples:

```text
Backlog
   ↓
Todo
   ↓
In Progress
   ↓
Review
   ↓
Testing
   ↓
Done
```

### Seu fluxo sugerido

```text
Backlog
↓
Desenvolvimento
↓
Revisão
↓
Testes
↓
Homologado
↓
Finalizado
```

> Use apenas os estados que realmente ajudam. Mais colunas não significam mais organização.

## Conexão com Issues

```text
Issue #10
   ↓
Project
   ↓
Branch
   ↓
Pull Request
   ↓
Merge
   ↓
Done
```

## Projeto solo

Sim, pode usar.

Mas mantenha simples:

```text
Backlog
Todo
Doing
Done
```

Não crie um processo corporativo para um projeto pequeno.

### Quando usar Projects?

Use quando houver:

* várias tarefas;
* funcionalidades futuras;
* bugs;
* prioridades;
* necessidade de acompanhar progresso.

Para um projeto muito pequeno, Issues sozinhas podem ser suficientes.

### Regra mental

```text
Issue   → trabalho individual
Project → visão do conjunto
```

---

# Wiki

Wiki é uma área para **documentação complementar do projeto**, organizada em páginas.

Pode conter:

* Guias
* Tutoriais
* Procedimentos
* Explicações
* Documentação extensa

### README × Wiki

```text
README
→ apresentação e início rápido

Wiki
→ documentação mais extensa
```

### Boa prática

Não duplicar informações sem necessidade.

Use:

```text
README → "como começar"
Wiki   → "como funciona em detalhes"
```

---

# Insights

Insights fornece métricas e gráficos sobre o repositório, como atividade, commits, contribuidores, tráfego, forks e rede, dependendo do repositório e dos recursos disponíveis.

## Informações úteis

### Pulse

Visão resumida da atividade recente.

### Contributors

Mostra contribuições por usuário.

### Commits

Ajuda a analisar o histórico de commits.

### Traffic

Pode mostrar informações sobre acesso e tráfego do repositório.

### Dependencies

Mostra projetos que dependem do seu repositório quando aplicável.

### Network

Mostra o histórico de branches da **rede de repositórios**, incluindo forks.

---

# Dependências

Uma dependência é um software que seu projeto precisa para funcionar.

Exemplo:

```text
Meu projeto
   ↓
React
   ↓
Outras bibliotecas
```

Ou:

```text
Projeto A
   ↓ depende de
Projeto B
```

Dependências podem ser bibliotecas, pacotes ou outros componentes necessários ao projeto.

---

# Fork

Fork é uma **cópia de um repositório na sua própria conta/namespace**, usada principalmente para desenvolver mudanças sem alterar diretamente o repositório original. Depois, você pode propor essas mudanças ao projeto original através de um Pull Request.

### Fluxo

```text
Repositório original
       ↓
      Fork
       ↓
Seu repositório
       ↓
Alterações
       ↓
Pull Request
       ↓
Projeto original
```

### Modelo mental

```text
Clone → cópia para sua máquina
Fork  → cópia para sua conta no GitHub
```

---

# Network

Network mostra o histórico de desenvolvimento de uma **rede de repositórios**, incluindo branches de forks. É útil para visualizar como diferentes cópias do projeto se relacionam.

```text
Projeto original
   ├── fork A
   ├── fork B
   └── fork C
```

---

# Settings

Settings concentra as configurações do repositório.

Áreas importantes:

* Access
* Branches
* Actions
* Secrets
* Webhooks
* Pages
* Security

### Cuidados

Configurações importantes podem afetar:

* quem pode alterar o projeto;
* quais branches podem receber push;
* execução de Actions;
* deploy;
* acesso a informações sensíveis.

> **Settings é administração do repositório, não parte do desenvolvimento cotidiano.**

---

# Gists

Gist serve para armazenar e compartilhar **pequenos trechos de código, arquivos ou anotações**.

Exemplo:

```text
script para corrigir problema
configuração pequena
comando útil
exemplo de código
```

### Gist × Repository

```text
Gist
→ pequeno trecho / solução específica

Repository
→ projeto completo + histórico + estrutura
```

### Quando usar?

Use Gist para:

* snippets;
* scripts pequenos;
* exemplos rápidos;
* compartilhar soluções.

Evite usar Gist como substituto de um projeto completo.

---

# Encontrando bons repositórios

GitHub também pode ser usado como ferramenta de aprendizado.

## Analisar código de outros desenvolvedores

Procure projetos que tenham:

* README bem escrito;
* estrutura clara;
* commits compreensíveis;
* Issues;
* Pull Requests;
* testes;
* CI;
* documentação;
* histórico ativo.

### Como estudar um repositório

```text
README
  ↓
Estrutura
  ↓
Código
  ↓
Tests
  ↓
Issues
  ↓
Pull Requests
  ↓
Actions
  ↓
Histórico
```

Não olhe apenas o código final.

Observe **como o projeto evoluiu**.

---

# Stars

⭐ **Star** é uma forma de marcar um repositório como interessante/favorito.

Use para:

* guardar referências;
* encontrar projetos posteriormente;
* acompanhar projetos que você quer estudar.

> Star não é o mesmo que Fork.

---

# Fork × Star × Clone

```text
Star
→ salvar/acompanhar interesse

Fork
→ criar uma cópia do projeto no GitHub

Clone
→ copiar o repositório para sua máquina
```

---

# Fluxo profissional completo

```text
Planejamento
     ↓
Issue
     ↓
Project
     ↓
Branch
     ↓
Desenvolvimento
     ↓
Commit
     ↓
Push
     ↓
Pull Request
     ↓
Review
     ↓
GitHub Actions
     ↓
Testes / CI
     ↓
Merge
     ↓
Main
     ↓
Deploy / CD
     ↓
Done
```

### Fluxo para projeto solo

```text
Issue
  ↓
Branch
  ↓
Commit
  ↓
Push
  ↓
Pull Request
  ↓
Actions
  ↓
Merge
  ↓
Main
```

### Fluxo mínimo

Para projetos pequenos:

```text
Branch
  ↓
Commit
  ↓
Push
  ↓
Main
```

> **Ferramenta deve resolver um problema. Não crie processo apenas para parecer profissional.**

---

# Regra mental da Seção

```text
Code       → construir
Issue      → planejar
Branch     → isolar
Commit     → registrar
PR         → revisar
Actions    → automatizar
Project    → acompanhar
Wiki       → documentar
Insights   → analisar
Settings   → administrar
Fork       → colaborar externamente
Star       → guardar referência
Gist       → compartilhar snippet
```

# Padrão profissional

```text
Problema
   ↓
Issue
   ↓
Branch
   ↓
Commits
   ↓
Pull Request
   ↓
Review + CI
   ↓
Merge
   ↓
Main
   ↓
CD / Deploy
```

### Princípio principal

> **Código mostra o que foi construído.
> Issues mostram o que precisa ser feito.
> PRs mostram como foi integrado.
> Actions mostram o que pode ser automatizado.
> Projects mostram o que está acontecendo.**
