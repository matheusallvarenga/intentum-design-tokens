# Estado deste repositório

**Situação:** arquivado em 06/11/2026; todos os consumidores migraram para `@intentum/design-system`. Congelado na v1.0.0 desde 05/11/2026; somente leitura.

## O que aconteceu

| Data | Evento |
|---|---|
| 03/07/2026 | Tokens extraídos do `intentum-infinity` para este repositório (débito HK.8 do Legendary: o Legendary importava um arquivo gerado de outro repositório pelo caminho relativo). Tag `v1.0.0` no commit `3a9acec`, registry 1.2.0. |
| jul–out/2026 | O registry de origem, no `intentum-infinity`, evoluiu para 1.3.0. Este pacote não acompanhou. |
| 27/10–05/11/2026 | Pesquisa e decisões do design system (documento-mestre em `intentum-infinity/docs/design/ds-intentum/README.md`). Aprovado um pacote único de design system, privado. |
| 05/11/2026 | v2.0.0 construída e publicada como `@intentum/design-system` no repositório privado `matheusallvarenga/intentum-design-system`. Este repositório foi congelado para não quebrar os consumidores da v1.0.0. |
| 06/11/2026 | `itm-legendary-infinity-os` migra para a v2.0.1 (PRs #29/#30) e `itm-social-media-dashboard` para a v2.0.2 (PR #9). PRs do Dependabot daqui fechados (#2, #3, #4). Repositório arquivado no GitHub. |

## Quem dependia daqui

| Consumidor | Hoje |
|---|---|
| `itm-legendary-infinity-os` | `"@intentum/design-system": "git+https://github.com/matheusallvarenga/intentum-design-system.git#v2.0.1"` (06/11/2026) |
| `itm-social-media-dashboard` | `"@intentum/design-system": "git+https://github.com/matheusallvarenga/intentum-design-system.git#v2.0.2"` (06/11/2026) |

Nenhum `package.json` ou lockfile de branch principal em `~/projects` referencia mais `@intentum/design-tokens` (varredura de 06/11/2026). Branches antigas, anteriores às migrações, ainda apontam para `#v1.0.0`; elas continuam instalando porque um repositório público arquivado segue legível.

## Regras

- Não mova, apague nem reescreva a tag `v1.0.0`.
- Não adicione fontes, logos ou qualquer ativo de marca: o repositório é público.
- Correções de tokens vão para o repositório novo.
