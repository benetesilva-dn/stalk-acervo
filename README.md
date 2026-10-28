# Acervo de Stalk

Site do acervo de native ads (GitHub Pages, repo `stalk-acervo`). Desde 28/10/2026 é um **índice por
produto**: a capa tem um cartão por stalk, e cada cartão abre o catálogo daquele produto no modelo atual
(`catalogo_stalk.py` da skill `native-ads-stalk`: abas, ✓ feito, ▶ aprovado, ★ sugestão, marcar e copiar seleção).

| Arquivo | O que é |
|---|---|
| `index.html` | a capa: um cartão por produto, feita à mão |
| `bbpet.html` | catálogo BBPet (cópia de `notas/2026-10-13_bbpet-stalk/stalk-bbpet.html`) |
| `nanomag.html` | catálogo NanoMag de 08/10 (sem abas de empresa/funil/ângulo, sem 90 dias, sem sugestões) |
| `h50-adv108.html` | pack de ads da renovação do adv108 (cópia de `native-ads-stalk/saida_h50-adv108_2026-10-11/bruto/ads-adv108-h50.html`) |
| `arquivo.html` | o painel antigo (modelo de 21/09), lê `acervo.json` |
| `acervo.json` | as coletas acumuladas até 13/10, uma oferta por ID estável `OF-NNNN` — **o ativo** |
| `decisoes.jsonl` | append-only: toda decisão com motivo e data — **o ativo** |
| `produtos.json` | espinha dos produtos: nicho, termos, categorias AdPlexity, advs, sfunnel |

## Stalk novo ou catálogo atualizado

1. Gerar o catálogo do produto (`catalogo_stalk.py ... --html`) e rodar `testar_catalogo.mjs` nele.
2. Copiar o HTML para cá como `<produto>.html` (mesmo nome de sempre: a marcação fica no navegador, por título).
3. Criar ou atualizar o cartão do produto em `index.html` (data, nº de páginas, feitos, sugestões).
4. `git -C painel add -A && git -C painel commit -m "<produto> <data>" && git -C painel push`

Coleta de portal antiga (o `node acervo.js` da raiz) continua alimentando `acervo.json` e o `arquivo.html`.

IDs nunca são reciclados: `OF-0503` é a mesma peça daqui a seis meses.
