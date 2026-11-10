# links

Página de links (estilo Linktree/Beacons) de Samuel Bernardo, no mesmo visual do `portfolio-v3`: fundo `#141414`, iA Writer Mono, sublinhados coloridos sorteados.

Sem build, sem dependências, sem framework: um `index.html` com CSS embutido, duas fontes locais e a foto. ~93 KB no total, ~1,9 KB de HTML comprimido.

## Editar

Tudo em `index.html`:

| O que | Onde |
| --- | --- |
| Nome e cargo | `<h1>` e `<p class="cargo">` |
| Links | os três `<li>` dentro de `<nav>` |
| Foto | `profile.jpg` (240×240, 14 KB) |
| Cores | variáveis no `:root` do `<style>` |
| Rodapé | `<footer>` |

Para adicionar um link, copie um `<li>` inteiro e ajuste `href`, `.rotulo` e `.destino`. As cores do sublinhado são distribuídas automaticamente entre as linhas.

## Rodar local

```bash
python3 -m http.server 4174
# http://localhost:4174
```

## Publicar no Cloudflare Pages

1. Suba este diretório para um repositório no GitHub.
2. **Workers & Pages → Create → Pages → Connect to Git** e escolha o repositório.
3. Build command: **vazio**. Build output directory: **`/`** (é site estático puro).
4. Em **Custom domains**, adicione o subdomínio (ex.: `links.seudominio.com`). Como o DNS já está no Cloudflare, a verificação é imediata.

O arquivo `_headers` já configura cache longo para fontes e foto e revalidação para o HTML.

## Estrutura

```
index.html    página única (CSS embutido)
profile.jpg   foto 240×240
favicon.svg   "sb" minúsculo
fonts/        iA Writer Mono 400 e 700 (woff2, subset latino)
_headers      cache do Cloudflare Pages
```
