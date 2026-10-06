# livup-lps-midias

Mídias (imagens, variantes responsivas, capas e vídeos) usadas pelos blocos de HTML do CMS das páginas
**Baixa Caloria** e **Performance** (projeto `livup-lps`). Repositório **só de arquivos estáticos**.

URL base dos arquivos (GitHub raw):

    https://raw.githubusercontent.com/Eroscv/livup-lps-midias/main/lp/

## Arquivos (`lp/`)
- `bc-*` / `perf-*` / `linha-*` `.webp`: imagens otimizadas; sufixos `-320/-384/-480/-640/-720` são variantes menores (srcset).
- `*-hero-poster.webp`: capa do vídeo do topo.
- `bc-hero*` e `perf-hero*`: vídeo do topo em três formatos: `-av1.mp4` (AV1), `.webm` (VP9) e `.mp4` (H.264).

Os blocos escolhem o primeiro formato que o navegador souber tocar. **Não renomeie os arquivos**: os blocos dependem dos nomes.

## Atualizar uma mídia
Substitua o arquivo em `lp/` mantendo o nome, faça commit e push. O raw guarda cache por ~5 minutos.
