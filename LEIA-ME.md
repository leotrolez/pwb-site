# Landing page do Poke World Bot

Site estático (1 HTML, sem dependências externas, carrega rápido). Para publicar, suba a pasta inteira em qualquer hospedagem
estática grátis (Cloudflare Pages, Netlify, GitHub Pages) e aponte seu domínio.

## Antes de publicar
1. Troque `https://SEU-DOMINIO.com.br` pelo endereço real em: `index.html` (canonical, og:url, og:image, twitter:image, JSON-LD),
   `robots.txt` e `sitemap.xml`.
2. Os botões de download baixam `download/PWB-Instalador.exe` (~170 KB). É um instalador leve: ele baixa o instalador completo do app direto das releases do GitHub (a versão mais nova; se a consulta falhar, usa a 1.0.2), confere o hash e abre. Se a versão for mais antiga, o próprio app se atualiza sozinho na primeira abertura. Código em `tools/downloader/` do repositório do app; para recompilar: `powershell -File tools/downloader/build.ps1` e copie `dist/PWB-Instalador.exe` para `download/`.

## SEO (o que fazer depois de publicar)
- Cadastre o site no Google Search Console e envie o `sitemap.xml`; faça o mesmo no Bing Webmaster Tools.
- Ranquear em 1º depende de domínio próprio, links vindos de outros sites (Discord/fóruns/YouTube/comunidade do jogo) e tempo.
  Nada na página garante a posição; ela já está preparada (título, descrição, dados estruturados, FAQ, velocidade, mobile).
- Vídeo curto do app rodando (YouTube) e prints reais no lugar da ilustração aumentam conversão e dão mais links.

## Prints do bot nos cards
Coloque os prints na pasta `assets/prints/` com estes nomes (`.webp`, `.png` ou `.jpg`). Não precisa mexer no código:
o print aparece sozinho no topo do card, abre ampliado ao clicar, e o card que não tiver arquivo continua normal, sem espaço vazio.

| Arquivo | Onde aparece |
|---|---|
| `auto-hunt` | Card Auto Hunt |
| `auto-seller` | Card Auto Seller |
| `auto-refill` | Card Auto Refill |
| `analise-cacada` | Card Análise da caçada |
| `auto-pesca` | Card Auto Pesca |
| `poke-analyzer` | Card Poke Analyzer |
| `breeding` | Card Breeding Advisor |
| `quests` | Card Quests |
| `game-pass` | Card Game Pass |
| `auto-gym` | Card Auto Gym |
| `pokedex` | Card Pokédex |
| `anti-congelamento` | Card Detector de congelamento |

Dica: proporção 16:10 (ex.: 1280×800), recorte só o painel do módulo, e prefira `.webp` (leve, ajuda no SEO).

## Vídeo tutorial
Na seção "Tutorial em vídeo" (`id="vid"` no `index.html`), preencha `data-youtube="ID_DO_VIDEO"` (o trecho depois de `v=` na URL do YouTube).
Sem o ID, aparece "Vídeo em breve". Com o ID, a página mostra a miniatura e só carrega o player ao clicar (mais rápido e privado),
libera o botão "Assistir no YouTube" e cria os dados de vídeo para o Google. Se quiser apontar o botão para o canal, use `data-url`.

A imagem da seção "Controle 4 contas simultaneamente" é `assets/prints/contas.webp` (print real do app com 4 contas; nomes de personagens e de jogadores no chat ocultados).
