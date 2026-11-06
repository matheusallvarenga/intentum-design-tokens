# @intentum/design-tokens

> **Arquivado em 06/11/2026; todos os consumidores migraram para `@intentum/design-system`.** Congelado na v1.0.0 desde 05/11/2026. A v2 do design system INTENTUM™ vive no repositório privado `matheusallvarenga/intentum-design-system`, porque passou a incluir fontes, logos e ativos de uso interno que não podem ser públicos.
>
> - **Consumidores migrados:** `itm-legendary-infinity-os` (v2.0.1, 06/11) e `itm-social-media-dashboard` (v2.0.2, 06/11). Nenhum `package.json` ou lockfile de branch principal depende mais daqui.
> - **A tag `v1.0.0` (commit `3a9acec`) continua existindo** e não será movida nem apagada: branches antigas que ainda apontam para ela seguem instalando.
> - **Somente leitura.** Mudanças de tokens vão para o repositório novo. Detalhes em [`docs/STATUS.md`](docs/STATUS.md).

Fonte única de verdade dos design tokens INTENTUM™ DNA-OS (cores, box-shadow, transition duration/timing).

## Origem

Extraído de `intentum-infinity` em 2026-07-03 para resolver um débito de acoplamento cross-repo: `itm-legendary-infinity-os/tailwind.config.ts` importava um artefato **gitignored** de `intentum-infinity` via caminho relativo (`../intentum-infinity/dist/tokens/legendary-tokens.cjs`), o que quebrava build em qualquer ambiente sem os dois repos clonados lado a lado com o build já rodado (CI, Vercel, clone fresco). Detalhe completo: `docs/governance/DEBT-cross-repo-token-coupling-2026-07-02.md` em `itm-legendary-infinity-os`.

## Estrutura

```
registry/tokens.registry.yml   # fonte (DTCG-compliant, v1.2.0)
scripts/build.config.cjs       # pipeline Style Dictionary 4.4.0
dist/tokens/                   # artefatos gerados — COMMITADOS (não gitignored)
  ├── tokens.css
  ├── tokens-oklch.css
  ├── tailwind-v4.css
  ├── tailwind-v3.cjs
  ├── tokens.dtcg.json
  ├── tokens.scss
  └── legendary-tokens.cjs
```

`dist/` é commitado propositalmente (diferente do padrão usual de gitignorar artefatos de build) — consumidores instalam este pacote via dependência git tag-pinned e usam os arquivos já buildados diretamente, sem precisar rodar `style-dictionary` como dependência de runtime.

## Uso (consumidores)

```jsonc
// package.json de um consumidor
{
  "dependencies": {
    "@intentum/design-tokens": "github:matheusallvarenga/intentum-design-tokens#v1.0.0"
  }
}
```

```js
// tailwind.config.ts / .cjs
const dnaOsTokens = require('@intentum/design-tokens/dist/tokens/legendary-tokens.cjs');
```

## Consumidores conhecidos

- `itm-legendary-infinity-os` (migrado em 2026-07-03)
- `intentum-infinity` (fonte original — migração para consumir deste pacote é um débito separado, ver DEBT doc)
- `itm-infinity-aios-studio` (consumidor do design system, ainda não migrado)

## Atualizando os tokens

1. Editar `registry/tokens.registry.yml`
2. `npm install && npm run tokens:build`
3. Commitar `registry/` + `dist/` juntos
4. Criar uma tag semver (`git tag v1.x.0 && git push --tags`)
5. Atualizar a referência de tag nos `package.json` dos consumidores que devem receber a mudança
