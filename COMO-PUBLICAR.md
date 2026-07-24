# Como publicar o Prevya sem expor o código-fonte

## Estrutura recomendada

Use dois repositórios separados:

### 1. Repositório privado: `prevya-app`

Conteúdo:

- código-fonte;
- arquivos do Supabase e migrations;
- regras de negócio;
- configurações de deploy;
- documentação técnica interna.

Visibilidade: **Private**.

### 2. Repositório público: `prevya-showcase`

Conteúdo:

- `README.md`;
- `NOTICE.md`;
- pasta `assets` com imagens;
- pasta `docs` com o PDF de apresentação.

Visibilidade: **Public**.

O repositório público não deve conter `src`, `.env`, SQL, funções do banco, regras de cobrança ou qualquer código da aplicação.

## Publicação do showcase

Crie um repositório público vazio chamado `prevya-showcase`. Depois, no PowerShell, dentro da pasta extraída deste pacote:

```powershell
git init -b main
git add .
git commit -m "Publica apresentacao do projeto Prevya"
git remote add origin https://github.com/VictorVInny/prevya-showcase.git
git push -u origin main
```

## Repositório privado do produto

O código real deve ser enviado para um repositório separado e privado, por exemplo:

```text
https://github.com/VictorVInny/prevya-app
```

Antes do envio, confirme que `.env.local`, `node_modules` e `dist` estão ignorados.

## Proteção de propriedade

O arquivo `NOTICE.md` deixa claro que o material público é apenas demonstrativo e que o código-fonte permanece privado. Não adicione uma licença open source, pois esse tipo de licença normalmente concede direitos de uso, modificação e distribuição.

Mesmo assim, qualquer imagem ou documento publicado pode ser copiado tecnicamente. Por isso, o pacote público contém apenas material de apresentação, nunca o código ou as regras internas do produto.
