# GitHub Setup - Guia de Recuperação

Este documento descreve como configurar ou recuperar seus repositórios GitHub se precisar deletar e refazer.

---

## Informações da Conta

- **GitHub Account:** aneliseschiavo-ia
- **Git Name:** Anelise Schiavo
- **Git Email:** aneliseschiavo-ia@users.noreply.github.com

---

## Repositórios Principais

1. **cohort_fundamentals** (público)
   - URL: https://github.com/aneliseschiavo-ia/cohort_fundamentals
   - Descrição: CoHort Fundamentals - curso e exercícios

2. **aios-core** (público - fork)
   - URL: https://github.com/aneliseschiavo-ia/aios-core
   - Descrição: Fork do Synkra AIOS

---

## Passo a Passo: Se Precisar Refazer

### Prerequisitos
- GitHub CLI instalado (`gh`)
- Git instalado
- Token gerado no GitHub Settings > Developer settings > Personal access tokens

### 1. Autenticar GitHub CLI

Se a autenticação foi perdida:

```bash
gh auth login --web
```

Ou com token (se tiver um salvo):

```bash
# Colar o token quando solicitado
gh auth login --with-token
```

Verificar autenticação:
```bash
gh auth status
```

### 2. Refazer Fork do aios-core

Se deletou o fork:

```bash
gh repo fork SynkraAI/aios-core --clone=false
```

Isso cria: https://github.com/aneliseschiavo-ia/aios-core

### 3. Refazer cohort_fundamentals

Se deletou o repositório, vá para a pasta do projeto:

```bash
cd "C:\Users\aneli\aios\Documentos\cohort_fundamentals"
```

Crie o repositório novamente:

```bash
gh repo create cohort_fundamentals --public --source=. --remote=origin --push
```

Se houver erro de email privado, desabilite a proteção:
1. Vá para: https://github.com/settings/emails
2. Desmarque "Keep my email addresses private"

### 4. Deletar Repositório (se necessário)

1. Vá para o repositório no navegador
   - Ex: https://github.com/aneliseschiavo-ia/cohort_fundamentals

2. Clique em **Settings** (engrenagem no topo direito)

3. Scroll para baixo até **"Danger Zone"**

4. Clique em **"Delete this repository"**

5. Digite o nome exato do repositório para confirmar

6. Clique em **"I understand the consequences, delete this repository"**

---

## Recuperação Rápida (Cheat Sheet)

```bash
# Verificar autenticação
gh auth status

# Listar seus repositórios
gh repo list aneliseschiavo-ia

# Refazer fork do aios-core
gh repo fork SynkraAI/aios-core --clone=false

# Refazer cohort_fundamentals
cd "C:\Users\aneli\aios\Documentos\cohort_fundamentals"
gh repo create cohort_fundamentals --public --source=. --remote=origin --push

# Verificar remote do projeto
git remote -v

# Verificar commits
git log --oneline
```

---

## Troubleshooting

### Erro: "Your push would publish a private email address"
**Solução:** Desabilite a proteção de email privado em https://github.com/settings/emails

### Erro: "gh: command not found"
**Solução:** GitHub CLI não está instalado. Instale em https://cli.github.com/

### Erro: "Not authenticated"
**Solução:** Execute `gh auth login --web` para autenticar

### Erro: "Repository already exists"
**Solução:** O repositório já existe no GitHub. Delete-o primeiro (veja seção "Deletar Repositório")

---

## Arquivos Importantes

- `.gitignore` - Arquivos que não devem ser commitados
- `CLAUDE.md` - Documentação do projeto
- `links/` - Referências e materiais do curso

---

**Data de criação:** 13 de fevereiro de 2026
**Última atualização:** 13 de fevereiro de 2026
