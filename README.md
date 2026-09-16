# Acervo de Stalk

Painel único do acervo de native ads. Substitui os HTMLs por coleta
(`painel.html` 23 MB, `painel_transicao.html` 14 MB, etc.) que se contradiziam.

| Arquivo | O que é |
|---|---|
| `acervo.json` | todas as coletas acumuladas, uma oferta por ID estável `OF-NNNN` — **o ativo** |
| `decisoes.jsonl` | append-only: toda decisão com motivo e data — **o ativo** |
| `produtos.json` | espinha dos produtos: nicho, termos, categorias AdPlexity, advs, sfunnel |
| `index.html` | a view — **descartável** |

O painel não guarda estado de verdade. Ele lê o acervo, você clica, ele monta uma
linha, você cola no Claude, e o Claude escreve em `decisoes.jsonl`. Página estática
não pode guardar credencial sem expor — por isso não há backend, e por isso não há
nada para manter.

Regenerar depois de uma coleta nova:

```
node acervo.js && git -C painel commit -am "coleta" && git -C painel push
```

IDs nunca são reciclados: `OF-0503` é a mesma peça daqui a seis meses.
