# livup-lps-midias

Mídias (imagens, variantes responsivas, capas e vídeos) usadas pelos blocos de HTML do CMS das páginas
**Baixa Caloria** e **Performance** (projeto `livup-lps`). Repositório **só de arquivos estáticos**.

URL base dos arquivos (CDN jsDelivr, **fixada numa versão/tag**):

    https://cdn.jsdelivr.net/gh/Eroscv/livup-lps-midias@v3/lp/

Os blocos usam `@v3` (a versão atual), e não `@main`: o conteúdo de uma tag não muda, então um commit novo aqui nunca altera as páginas
publicadas sem querer. (Não use o GitHub raw: serve `.mp4` como `application/octet-stream` e `.webm` como `audio/webm`
e o vídeo travava no Safari do iPhone.)

## Arquivos (`lp/`)
- `bc-*` / `perf-*` / `linha-*` `.webp`: imagens otimizadas; sufixos `-320/-384/-480/-640/-720` são variantes menores (srcset).
- `*-hero-poster.webp`: capa do vídeo do topo (Baixa Caloria).
- `perf-hero.webp` (1920×1080) + `-480`/`-720`/`-960`/`-1440`: imagem do topo da Performance (colagem de atletas), no lugar do vídeo a partir da `v2`; em alta resolução a partir da `v3`.
- `bc-hero*`: vídeo do topo da Baixa Caloria em três formatos (`perf-hero*.mp4/.webm` e `perf-hero-poster.webp` são o vídeo antigo da Performance, usado só na `v1`): `-av1.mp4` (AV1), `.webm` (VP9) e `.mp4` (H.264).

Os blocos escolhem o primeiro formato que o navegador souber tocar. **Não renomeie os arquivos**: os blocos dependem dos nomes.

## Publicar uma mídia nova ou trocada (nova versão)
1. Coloque/substitua o arquivo em `lp/` (mantendo o nome se for troca), faça commit e push em `main`.
2. Crie a tag da próxima versão (a atual é `v3`) e envie: `git tag v4 && git push origin v4`.
3. Nos blocos do CMS, localize e substitua `livup-lps-midias@v3` por `livup-lps-midias@v4` e republique.

Não mova nem reescreva uma tag que já foi usada: a jsDelivr guarda o conteúdo de tags por muito tempo (não dá para limpar).
Versões anteriores continuam disponíveis, então dá para voltar atrás trocando `@v4` por `@v3`.
O repositório precisa continuar **público**.
