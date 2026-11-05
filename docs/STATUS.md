# Estado deste repositório

**Situação:** congelado na v1.0.0 desde 05/11/2026. Somente leitura na prática; será arquivado quando nenhum consumidor usar mais a v1.0.0.

## O que aconteceu

| Data | Evento |
|---|---|
| 03/07/2026 | Tokens extraídos do `intentum-infinity` para este repositório (débito HK.8 do Legendary: o Legendary importava um arquivo gerado de outro repositório pelo caminho relativo). Tag `v1.0.0` no commit `3a9acec`, registry 1.2.0. |
| jul–out/2026 | O registry de origem, no `intentum-infinity`, evoluiu para 1.3.0. Este pacote não acompanhou. |
| 27/10–05/11/2026 | Pesquisa e decisões do design system (documento-mestre em `intentum-infinity/docs/design/ds-intentum/README.md`). Aprovado um pacote único de design system, privado. |
| 05/11/2026 | v2.0.0 construída e publicada como `@intentum/design-system` no repositório privado `matheusallvarenga/intentum-design-system`. Este repositório foi congelado para não quebrar os consumidores da v1.0.0. |

## Quem ainda depende daqui

| Consumidor | Dependência |
|---|---|
| `itm-legendary-infinity-os` | `"@intentum/design-tokens": "github:matheusallvarenga/intentum-design-tokens#v1.0.0"` |
| `itm-social-media-dashboard` | idem |

## O que vai acontecer

1. Cada consumidor migra para `"@intentum/design-system": "github:matheusallvarenga/intentum-design-system#v2.0.0"` num PR próprio, depois de configurar o acesso autenticado ao repositório privado.
2. Quando os dois tiverem migrado, este repositório é arquivado no GitHub (somente leitura). A tag `v1.0.0` continua existindo.

## Regras até lá

- Não mova, apague nem reescreva a tag `v1.0.0`.
- Não adicione fontes, logos ou qualquer ativo de marca: o repositório é público.
- Correções de tokens vão para o repositório novo.
