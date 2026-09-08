# Anima — Site institucional

Site estático de página única (HTML/CSS/JS embutidos, zero dependências de build).

## Deploy na Vercel

### Opção A — mais rápida (sem Git), pelo navegador
1. Acesse https://vercel.com/new
2. Escolha "Deploy" > arraste esta pasta (ou o zip `anima-site.zip`) na área de upload.
3. Como é um site estático puro, não é preciso configurar build command nem output directory — a Vercel detecta e serve o `index.html` na raiz.

### Opção B — via CLI (permite atualizar depois com um comando)
```bash
npm i -g vercel      # instala a CLI da Vercel (uma vez só)
cd anima-site
vercel               # primeiro deploy (preview) — pede login/link do projeto
vercel --prod        # publica em produção
```

### Opção C — via GitHub (recomendado para manter histórico e deploys automáticos)
1. Crie um repositório no GitHub e suba esta pasta:
   ```bash
   cd anima-site
   git init
   git add .
   git commit -m "Site Anima — primeira versão"
   git branch -M main
   git remote add origin <URL_DO_SEU_REPO>
   git push -u origin main
   ```
2. Em https://vercel.com/new, escolha "Import Git Repository" e selecione o repositório.
3. A Vercel detecta que é estático — não precisa mexer em nada, é só confirmar o deploy.
4. Todo novo `git push` para `main` gera um deploy automático.

## Depois de publicado

Com o conector MCP da Vercel conectado no Claude, dá para eu consultar deployments, status e logs
diretamente por aqui (`list_projects`, `list_deployments`, `get_deployment`, etc.) — mas a criação do
projeto/primeiro deploy precisa ser feita por uma das opções acima (painel, CLI ou GitHub).

## Pendências do site (ver documento de design do projeto)

- Trocar placas de projetos geradas por fotos reais
- Trocar monogramas dos depoimentos por fotos (quando houver clientes reais autorizados)
- Conectar o formulário de contato a um endpoint real (hoje só valida, não envia)
- Revisar conteúdo fictício com dados reais do estúdio
