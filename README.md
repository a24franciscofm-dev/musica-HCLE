# Aplicações para o Ensino da Música

Página web educativa que reproduce 4 faixas de áudio sincronizadas e permite
ativar/desativar cada instrumento individualmente.

**Site publicado:** https://a24franciscofm-dev.github.io/musica-HCLE/
**Repositório:** https://github.com/a24franciscofm-dev/musica-HCLE

## Estrutura

| Ficheiro | Descrição |
| --- | --- |
| `index.html` | Página principal (obrigatório que se chame `index.html` para o GitHub Pages a servir na raiz) |
| `faixa1.wav` … `faixa4.wav` | Faixas de áudio (Melodia, Harmonia, Baixo, Ritmo) |
| `.github/workflows/pages.yml` | Workflow que publica o site automaticamente a cada push em `main` |
| `.nojekyll` | Impede o processamento Jekyll (por segurança) |
| `Website educativo com música.pdf` / `Aplicações para o ensino da música.ods` | Documentação do trabalho |

Os caminhos dos áudios em `index.html` são relativos (`src="faixa1.wav"`), pelo
que funcionam tanto na raiz como em `https://usuario.github.io/repositorio/`.

## Como está configurado

- O repositório remoto é `git@github.com:a24franciscofm-dev/musica-HCLE.git`
  (autenticação por chave SSH).
- GitHub Pages está com **Source: GitHub Actions**; o workflow
  `Deploy a GitHub Pages` faz o build e a publicação a cada push em `main`.
- O passo `configure-pages` usa `enablement: true`, por isso ativa o Pages
  sozinho se for desativado no futuro.

## Atualizar o site

```bash
git add -A
git commit -m "Descrição da mudança"
git push
```

Cada push em `main` publica a nova versão automaticamente (1–2 minutos). Também
se pode forçar em **Actions → Deploy a GitHub Pages → Run workflow**.

## Ligar um clone novo

```bash
git clone git@github.com:a24franciscofm-dev/musica-HCLE.git
```

## Notas

- O repositório ocupa ~56 MB (os 4 WAV de 14 MB). Está dentro do limite do
  GitHub Pages (100 MB por ficheiro / 1 GB por site), mas cada visitante
  descarrega esses 56 MB. Se for necessário, os WAV podem ser convertidos para
  MP3 (~1 MB cada) e `index.html` atualizado nas linhas `<audio>`.
- Ficheiros/diretórios que comecem por `_` não são servidos pelo Jekyll; o
  `.nojekyll` presente evita esse problema.
