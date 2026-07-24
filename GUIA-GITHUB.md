# Guia de publicação do Prevya no GitHub

Use dois repositórios separados:

- `prevya-app`: privado, com o código real.
- `prevya-showcase`: público, somente com apresentação, imagens e PDF.

## 1. Repositório privado

### Criar no GitHub

Crie um repositório chamado `prevya-app`, marque como **Private** e não adicione README, .gitignore ou licença.

### Verificar o projeto local

No PowerShell:

```powershell
cd F:\PREVYA
npm.cmd run build

git check-ignore .env.local
git check-ignore node_modules
git check-ignore dist
```

Os três caminhos precisam aparecer como ignorados.

### Publicar

```powershell
cd F:\PREVYA

git init -b main
git add .
git status

git commit -m "feat: publica versao inicial do Prevya"
git branch -M main
git remote add origin https://github.com/VictorVInny/prevya-app.git
git push -u origin main
```

Confira no GitHub se o repositório aparece como **Private** e se `.env.local`, `node_modules` e `dist` não foram publicados.

## 2. Repositório público

Extraia o pacote do showcase para uma pasta separada, por exemplo:

```text
F:\PREVYA-SHOWCASE
```

Crie no GitHub um repositório chamado `prevya-showcase`, marque como **Public** e não adicione README, .gitignore ou licença.

No PowerShell:

```powershell
cd F:\PREVYA-SHOWCASE

git init -b main
git add .
git status

git commit -m "docs: publica apresentacao do projeto Prevya"
git branch -M main
git remote add origin https://github.com/VictorVInny/prevya-showcase.git
git push -u origin main
```

O repositório público deve conter somente:

```text
.gitignore
README.md
NOTICE.md
COMO-PUBLICAR.md
GUIA-GITHUB.md
assets\
docs\
```

Não publique `src`, `.env`, SQL, funções do banco, credenciais ou regras de cobrança.

## 3. Finalização do showcase

Na página do repositório público:

- adicione a descrição: `Plataforma web de organização financeira pessoal desenvolvida com React, TypeScript e Supabase.`
- adicione os tópicos: `react`, `typescript`, `supabase`, `postgresql`, `fintech`, `personal-finance`, `portfolio`.
- confira se o README mostra as imagens.
- abra `docs/Prevya-Portfolio.pdf` e confirme que as 13 páginas aparecem.
- fixe `prevya-showcase` no perfil do GitHub.

## 4. Atualizações futuras

### Projeto privado

```powershell
cd F:\PREVYA
git add .
git commit -m "feat: descreva a alteracao"
git push
```

### Showcase público

```powershell
cd F:\PREVYA-SHOWCASE
git add .
git commit -m "docs: atualiza apresentacao do Prevya"
git push
```
