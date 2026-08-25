# Seção 10: GitHub Pages

GitHub Pages é um serviço de **hospedagem de sites estáticos** integrado ao GitHub.

```text
GitHub
  ↓
repositório
  ↓
Pages
  ↓
site publicado
```

> **Site estático** → HTML, CSS, JavaScript e arquivos estáticos.
> O GitHub Pages não é, por si só, um servidor tradicional para executar um backend.

---

## Tipos de site

### User / Organization Site

Usado para criar o site principal de uma conta.

O repositório deve seguir:

```text
<usuario>.github.io
```

Exemplo:

```text
M0NTGN.github.io
```

A URL padrão será:

```text
https://<usuario>.github.io
```

Cada conta pode ter um único site de usuário/organização.

### Project Site

Usado para um projeto específico.

Exemplo:

```text
repositório:
meu-projeto
```

URL padrão:

```text
https://<usuario>.github.io/meu-projeto
```

Um repositório pode ter seu próprio site de Pages.

---

# Publicação

O GitHub Pages pode usar diferentes fontes de publicação.

### Branch + pasta

Pode publicar a partir:

```text
main → /
```

ou:

```text
main → /docs
```

Quando houver alterações na fonte configurada e elas forem enviadas por `push`, o conteúdo da fonte é publicado.

### GitHub Actions

Também pode usar um workflow para:

```text
código
  ↓
build
  ↓
GitHub Actions
  ↓
deploy
  ↓
GitHub Pages
```

Essa abordagem é recomendada quando existe um processo de build próprio ou quando você usa um gerador diferente do Jekyll.

---

# Arquivo de entrada

O GitHub Pages procura um arquivo de entrada no topo da fonte publicada:

```text
index.html
index.md
README.md
```

No caso mais comum de um site HTML:

```text
index.html
```

> `index.html` diferencia maiúsculas de minúsculas.

---

# Fluxo básico

### Site de usuário

```text
Criar repositório
      ↓
<usuario>.github.io
      ↓
Clonar
      ↓
Criar index.html
      ↓
git add
      ↓
git commit
      ↓
git push
      ↓
GitHub Pages publica
      ↓
https://<usuario>.github.io
```

A publicação pode levar alguns minutos após o `push`.

---

# Estrutura mínima

```text
meu-site/
├── index.html
├── style.css
├── script.js
└── assets/
```

O GitHub Pages publica os arquivos estáticos disponíveis na fonte configurada.

---

# Jekyll

GitHub Pages possui suporte integrado ao **Jekyll**, um gerador de sites estáticos.

```text
Markdown / HTML
      ↓
Jekyll
      ↓
Site estático
      ↓
GitHub Pages
```

Ao publicar diretamente de um branch, o GitHub Pages usa Jekyll por padrão em determinados fluxos. Para outros geradores, é recomendável usar GitHub Actions ou configurar o processo de acordo com a ferramenta utilizada.

> **Não preciso aprender Jekyll agora** para entender o básico de GitHub Pages.

---

# Configuração no GitHub

No repositório:

```text
Settings
  ↓
Pages
  ↓
Build and deployment
  ↓
Source
```

É possível definir a fonte de publicação e o branch/pasta usados pelo site.

---

# Domínio personalizado

O GitHub Pages pode usar:

```text
https://usuario.github.io
```

ou um domínio próprio:

```text
https://meusite.com
```

Nesse caso, é necessário configurar o domínio no GitHub e o DNS do provedor.

---

# Boas práticas

* `index.html` como entrada principal quando o site for HTML.
* Separar HTML, CSS e JavaScript quando fizer sentido.
* Manter assets organizados.
* Não publicar informações sensíveis.
* Usar branch/source de publicação de forma clara.
* Automatizar build/deploy com Actions quando o projeto exigir.
* Testar o site após o deploy.

> ⚠️ GitHub Pages publica o site na internet. Não coloque senhas, tokens, chaves de API ou outras informações sensíveis no repositório/site.

---

# Limitações importantes

GitHub Pages é voltado para **sites estáticos**.

Não é a escolha adequada para executar diretamente:

```text
Backend
Banco de dados
Servidor Node/Python/PHP
API própria
```

Nesse cenário:

```text
Frontend estático → GitHub Pages
Backend/API       → outro serviço
```

---

# Uso profissional

GitHub Pages é útil para:

* Portfólio
* Documentação
* Landing pages
* Sites de projetos
* Documentação técnica
* Páginas pessoais
* Demonstrações de projetos

Exemplo:

```text
Código
  ↓
GitHub Repository
  ↓
GitHub Actions
  ↓
Build
  ↓
GitHub Pages
```

---

# Projeto pessoal × projeto profissional

### Projeto pequeno

```text
HTML/CSS/JS
    ↓
main
    ↓
push
    ↓
Pages
```

### Projeto com build

```text
Código
  ↓
Branch
  ↓
Pull Request
  ↓
CI
  ↓
Merge
  ↓
GitHub Actions
  ↓
Build
  ↓
Deploy
  ↓
Pages
```

> Comece simples. Só adicione Actions/build automatizado quando o projeto precisar.

---

# Regra mental

```text
GitHub Pages
→ hospedar site estático

User site
→ <usuario>.github.io

Project site
→ <usuario>.github.io/<repositorio>

index.html
→ entrada comum do site

Branch/Folder
→ fonte de publicação

Actions
→ build/deploy automatizado
```

# Fluxo completo

```text
Código
  ↓
Commit
  ↓
Push
  ↓
Fonte do Pages
  ↓
Build / Deploy
  ↓
Site publicado
```

### O que preciso saber agora?

```text
GitHub Pages
      ↓
hospedagem estática
      ↓
branch ou Actions
      ↓
index.html
      ↓
deploy automático
      ↓
site online
```

> **HTML/CSS/JS são a construção do site.
> GitHub Pages é a publicação/hospedagem.**
