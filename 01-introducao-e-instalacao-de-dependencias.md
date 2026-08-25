# Seção 1: Introdução e instalação das dependências

### Git

Sistema de **controle de versão**: registra alterações no código e permite recuperar versões anteriores.

- Open Source
    
- Mantém histórico das alterações
    
- Facilita trabalho em equipe
    

### Instalação

#### Fedora
```bash
sudo dnf install git
git --version
```

#### Debian / Ubuntu
```bash
sudo apt update
sudo apt install git
```

#### macOS (Homebrew)
```bash
brew install git
```

#### Windows
Baixar o instalador oficial em [git-scm.com](https://git-scm.com/) e seguir o passo a passo.

---

### Configuração Inicial (Identidade)

Antes do primeiro commit, é obrigatório configurar quem você é.

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
```

Para conferir as configurações atuais:

```bash
git config --list
```