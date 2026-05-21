# 🔐 Como configurar as chaves de API (modo seguro)

As chaves ficam nos **GitHub Secrets** — nunca expostas no código.

## Passo 1 — Adicionar os Secrets no GitHub

1. Acesse seu repositório no GitHub
2. Clique em **Settings** (engrenagem)
3. No menu lateral: **Secrets and variables → Actions**
4. Clique em **New repository secret** e adicione:

| Nome do Secret | Valor |
|---|---|
| `ANTHROPIC_KEY` | sua chave `sk-ant-api03-...` |
| `BRAPI_TOKEN` | seu token da brapi.dev |

## Passo 2 — Ativar GitHub Actions

1. Vá na aba **Actions** do repositório
2. Se aparecer aviso, clique em **"I understand my workflows, enable them"**

## Passo 3 — Ativar GitHub Pages na branch correta

1. Vá em **Settings → Pages**
2. Em "Source" selecione: **Deploy from a branch**
3. Branch: **gh-pages** → pasta: **/ (root)**
4. Clique em **Save**

## Passo 4 — Disparar o deploy

1. Vá em **Actions → Inject API Keys & Deploy**
2. Clique em **Run workflow → Run workflow**
3. Aguarde ~1 minuto
4. Acesse: `https://wilianpds.github.io/value-advisor2`

## Por que esse método é seguro?

- ✅ As chaves ficam criptografadas nos Secrets do GitHub
- ✅ Nunca aparecem no código-fonte público
- ✅ São injetadas apenas durante o build (processo automatizado)
- ✅ O arquivo final fica na branch `gh-pages` (separada do código)
- ✅ Ninguém que ver seu repositório consegue ver as chaves

## Atualizando as chaves

Se precisar trocar uma chave:
1. Vá em Settings → Secrets → edite o secret
2. Rode o workflow novamente (Actions → Run workflow)
