# Seção 11: Como hospedar um site e fazer deploy

## Hospedagem

**Hospedagem** é o serviço que mantém os arquivos e/ou aplicações do site em servidores acessíveis pela internet.

Fluxo simplificado:

```text
Usuário
   ↓
Domínio
   ↓
DNS
   ↓
Servidor / Hospedagem
   ↓
Site / Aplicação
   ↓
Navegador
```

O DNS associa o domínio ao endereço do servidor; a requisição chega ao servidor web, que entrega os recursos necessários ao navegador.

---

## Artigo para consulta

> **Artigo completo:** [Hospedagem de Sites: Guia Completo para Escolher a Melhor Opção](https://app.horadecodar.com.br/melhor-hospedagem-de-sites)

O artigo aborda funcionamento, tipos de hospedagem, performance, segurança, suporte, recursos, escalabilidade e comparação de provedores.

---

# Tipos de hospedagem

### Compartilhada

Vários sites utilizam os mesmos recursos de um servidor.

```text
Servidor
├── Site A
├── Site B
└── Site C
```

**Vantagens:** barata e simples.
**Desvantagens:** menos controle e recursos compartilhados.

Boa para:

* Portfólio
* Blog
* Site institucional
* Projetos pequenos

### VPS

Servidor físico dividido em máquinas virtuais com recursos e maior controle por projeto.

**Mais controle + mais responsabilidade.**

Boa quando o projeto precisa de:

* Mais desempenho
* Configuração própria
* SSH
* Firewall
* Ambiente mais controlado

### Dedicada

Servidor físico exclusivo para o projeto.

**Muito controle + maior custo e responsabilidade operacional.**

Adequada para cargas altas ou necessidades específicas de isolamento e controle.

### Cloud

Infraestrutura distribuída e elástica, permitindo escalar recursos conforme a demanda.

**Flexibilidade + escalabilidade + maior complexidade.**

---

# O que avaliar em uma hospedagem?

```text
Performance
Segurança
Estabilidade
Suporte
Recursos
Preço
Escalabilidade
```

### Performance

Observar:

* CPU / RAM
* SSD / NVMe
* Cache
* CDN
* Localização do servidor

O artigo também cita TTFB, LCP e INP como métricas úteis de desempenho.

### Estabilidade

**Uptime** = porcentagem de tempo em que o serviço permanece disponível.

Um SLA define compromissos de disponibilidade e possíveis compensações.

### Segurança

Observar recursos como:

```text
HTTPS / SSL
Backups
WAF
Proteção contra DDoS
Monitoramento
```

### Recursos

Dependendo do projeto, verificar:

```text
Domínio
SSL
Backups
Banco de dados
E-mail
SSH / SFTP
Staging
CDN
Logs
```

Também observar limites reais do plano: CPU, memória, inodes, armazenamento, e-mail e processos.

---

# Como escolher?

Não escolha apenas pelo menor preço.

Use:

```text
Necessidade do projeto
        ↓
Recursos necessários
        ↓
Performance / estabilidade
        ↓
Suporte
        ↓
Segurança
        ↓
Preço
        ↓
Possibilidade de upgrade
```

> **Boa hospedagem = atende o projeto atual e permite crescer sem uma migração desnecessariamente difícil.**

---

# Configurando a hospedagem

Fluxo geral:

```text
Contratar hospedagem
        ↓
Configurar domínio
        ↓
DNS → servidor
        ↓
Configurar ambiente
        ↓
Enviar arquivos
        ↓
Testar
        ↓
Site online
```

> Os passos exatos dependem do provedor e do tipo de hospedagem.

---

# Enviando arquivos

Dependendo da hospedagem, podemos utilizar:

```text
Painel de arquivos
FTP / FTPS
SFTP
SSH
Git / CI-CD
```

Para desenvolvimento profissional, **Git + automação de deploy** é preferível quando o ambiente suporta esse fluxo.

---

# Deploy

**Deploy = colocar uma versão do projeto em um ambiente onde ela será executada/publicada.**

Fluxo simples:

```text
Código local
   ↓
Commit
   ↓
Push
   ↓
Servidor
   ↓
Deploy
   ↓
Site atualizado
```

---

# Atualizando o site

Uma atualização pode ser:

```text
Alterar código
     ↓
Testar
     ↓
Commit
     ↓
Push
     ↓
Deploy
     ↓
Validar produção
```

Em projetos profissionais, o deploy pode ser automatizado:

```text
Push
 ↓
CI
 ↓
Testes
 ↓
Build
 ↓
Deploy
```

---

# Staging × Produção

### Staging

Ambiente para testar alterações antes de disponibilizá-las ao público.

### Produção

Ambiente utilizado pelos usuários reais.

```text
Desenvolvimento
      ↓
Staging
      ↓
Produção
```

O artigo destaca staging como forma de testar mudanças antes de afetar o site de produção.

---

# Projeto pequeno × profissional

### Projeto pequeno

```text
Código
 ↓
Push
 ↓
Hospedagem
 ↓
Deploy
```

### Projeto profissional

```text
Issue
 ↓
Branch
 ↓
Commit
 ↓
Pull Request
 ↓
Review
 ↓
CI
 ↓
Merge
 ↓
Deploy
 ↓
Produção
```

---

# Regra mental

```text
Domínio     → nome do site
DNS         → aponta para o servidor
Hospedagem  → infraestrutura
Deploy      → publicar uma versão
Staging     → testar antes
Produção    → ambiente real
```

### O que realmente preciso lembrar?

> **Hospedar = disponibilizar o projeto em um servidor.**
> **Deploy = enviar/publicar uma versão do projeto nesse ambiente.**

### Para estudar depois

```text
[ ] DNS
[ ] Domínio
[ ] HTTP / HTTPS
[ ] FTP / SFTP / SSH
[ ] Servidor web
[ ] Banco de dados
[ ] SSL/TLS
[ ] Reverse proxy
[ ] CI/CD
[ ] Docker
[ ] Cloud / VPS
```

> **Aprofundamento:** consulte o artigo completo quando precisar escolher uma hospedagem ou entender melhor infraestrutura. O guia cobre também performance, suporte, recursos, escalabilidade e particularidades do mercado brasileiro.
