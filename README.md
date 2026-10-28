# Aplicações para o Ensino da Música

Página web educativa que reproduce 4 faixas de áudio sincronizadas e permite
ativar/desativar cada instrumento individualmente.

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

## Desplegar no GitHub Pages

### 1. Criar o repositório no GitHub

Cria um repositório vazio (sem README nem `.gitignore`) chamado, por exemplo,
`Paxina_Fran`, em https://github.com/new.

### 2. Ligar o repositório local e enviar

```bash
git remote add origin git@github.com:UTILIZADOR/Paxina_Fran.git
git push -u origin main
```

> Substitui `UTILIZADOR` pelo teu nome de usuário do GitHub. O `origin` já deve
> funcionar se a chave SSH estiver configurada (`ssh -T git@github.com`).

### 3. Ativar o GitHub Pages

No repositório: **Settings → Pages → Build and deployment → Source** e escolhe
**GitHub Actions** (não "Deploy from a branch").

O workflow corre automaticamente no próximo push (ou manualmente em
**Actions → Deploy a GitHub Pages → Run workflow**).

### 4. URL do site

```
https://UTILIZADOR.github.io/Paxina_Fran/
```

Demora 1–2 minutos após o primeiro deploy. Se o repositório se chamar
`UTILIZADOR.github.io`, a URL será apenas `https://UTILIZADOR.github.io/`.

## Atualizar o site

```bash
git add -A
git commit -m "Descrição da mudança"
git push
```

Cada push em `main` publica a nova versão automaticamente.

## Notas

- O repositório ocupa ~56 MB (os 4 WAV de 14 MB). Está dentro do limite do
  GitHub Pages (100 MB por ficheiro / 1 GB por site), mas cada visitante
  descarrega esses 56 MB. Se for necessário, os WAV podem ser convertidos para
  MP3 (~1 MB cada) e `index.html` atualizado nas linhas `<audio>`.
- Ficheiros/diretórios que comecem por `_` não são servidos pelo Jekyll; o
  `.nojekyll` presente evita esse problema.
