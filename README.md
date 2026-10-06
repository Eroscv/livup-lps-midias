# livup-lps-midias

Mídias (imagens, variantes responsivas, capas e vídeos) usadas pelos blocos de HTML do CMS das páginas
**Baixa Caloria** e **Performance** (projeto `livup-lps`). Repositório **só de arquivos estáticos**.

URL base dos arquivos (CDN jsDelivr, **fixada numa versão/tag**):

    https://cdn.jsdelivr.net/gh/Eroscv/livup-lps-midias@v1/lp/

Os blocos usam `@v1`, e não `@main`: o conteúdo de uma tag não muda, então um commit novo aqui nunca altera as páginas
publicadas sem querer. (Não use o GitHub raw: serve `.mp4` como `application/octet-stream` e `.webm` como `audio/webm`
e o vídeo travava no Safari do iPhone.)

## Arquivos (`lp/`)
- `bc-*` / `perf-*` / `linha-*` `.webp`: imagens otimizadas; sufixos `-320/-384/-480/-640/-720` são variantes menores (srcset).
- `*-hero-poster.webp`: capa do vídeo do topo.
- `bc-hero*` e `perf-hero*`: vídeo do topo em três formatos: `-av1.mp4` (AV1), `.webm` (VP9) e `.mp4` (H.264).

Os blocos escolhem o primeiro formato que o navegador souber tocar. **Não renomeie os arquivos**: os blocos dependem dos nomes.

## Publicar uma mídia nova ou trocada (nova versão)
1. Coloque/substitua o arquivo em `lp/` (mantendo o nome se for troca), faça commit e push em `main`.
2. Crie a tag da próxima versão e envie: `git tag v2 && git push origin v2`.
3. Nos blocos do CMS, localize e substitua `livup-lps-midias@v1` por `livup-lps-midias@v2` e republique.

Não mova nem reescreva uma tag que já foi usada: a jsDelivr guarda o conteúdo de tags por muito tempo (não dá para limpar).
Versões anteriores continuam disponíveis, então dá para voltar atrás trocando `@v2` por `@v1`.
O repositório precisa continuar **público**.
