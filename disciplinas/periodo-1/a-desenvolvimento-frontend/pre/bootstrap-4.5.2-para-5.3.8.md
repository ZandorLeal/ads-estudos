# Bootstrap 4.5.2 → 5.3.8

Referência para estudar pela versão atual (5.3.8) sabendo o que muda no material do curso (4.5.2).

**Fontes (fato):**
- Versões e datas: [GitHub releases do twbs/bootstrap](https://github.com/twbs/bootstrap/releases), consultado em 23/09/2026.
- Mudanças: [guia oficial de migração v5.3](https://getbootstrap.com/docs/5.3/migration/), lido em 23/09/2026.
- Uso no curso: busca nos 113 arquivos do [repo de FrontEnd](https://github.com/FaculdadeDescomplica/Desenvolvimento-FrontEnd) e no do Dinâmico.

## Linha do tempo

| Versão | Data | Marco |
|---|---|---|
| **4.5.2** | 06/08/2020 | **versão usada no curso** (via CDN, com jQuery 3.5.1 slim + Popper) |
| 4.6.0 → 4.6.2 | 01/2021 → 07/2022 | últimas da linha 4 (manutenção) |
| **5.0.0** | 05/05/2021 | **major:** remove jQuery, muda classes, dropa IE |
| 5.1.0 | 04/08/2021 | CSS Grid experimental, offcanvas no navbar, placeholders, `.hstack`/`.vstack` |
| 5.2.0 | 19/07/2022 | componentes com CSS variables, novo `_maps.scss`, offcanvas responsivo |
| **5.3.0** | 30/05/2023 | **dark mode** (`data-bs-theme`), paleta estendida |
| 5.3.1 → 5.3.8 | 07/2023 → 26/08/2025 | correções; 5.3.6 migrou a doc para Astro |
| **5.3.8** | 26/08/2025 | **versão atual estável** (não há v6 publicada nos releases) |

## Impacto no material do curso

O que o código do curso usa e **quebra ou muda** na v5 (contagem de ocorrências nos repos):

| Uso no curso (v4) | Ocorr. | Na v5 | Desde |
|---|---|---|---|
| jQuery + Popper v1 via CDN | 13 páginas | jQuery removido; Popper v2 (já incluso no `bootstrap.bundle`) | 5.0 |
| `data-toggle`, `data-target`, `data-dismiss` | 12 | `data-bs-toggle`, `data-bs-target`, `data-bs-dismiss` | 5.0 |
| `.form-group` | 21 | removido; usar utilitários de espaçamento (`.mb-3`) | 5.0 |
| `.ml-*` / `.mr-*` | 3 | `.ms-*` / `.me-*` (start/end, por causa do RTL) | 5.0 |
| `.text-left` / `.text-right` | 2 | `.text-start` / `.text-end` | 5.0 |
| `.sr-only` | 2 | `.visually-hidden` | 5.0 |
| `.close` | 1 | `.btn-close` (ícone vira SVG, sem `&times;`) | 5.0 |
| `.card-deck` | 1 | removido; usar grid com `.row-cols-*` | 5.0 |
| `.thead-light` / `.thead-dark` | 1 | `.table-light` / `.table-dark` | 5.0 |
| `.text-muted` | 1 | deprecado; `.text-body-secondary` (sai na v6) | 5.3 |

Classes de v4 que **não** aparecem no material: `jumbotron`, `badge-*`, `custom-select`/`custom-control`,
`form-row`, `form-inline`, `btn-block`, `float-left/right`, `font-weight-*`, `no-gutters`,
`input-group-append/prepend`, `embed-responsive`, `media`.

## Mudanças por versão (resumo do guia oficial)

### 5.0.0 (a grande)
- **Dependências:** sem jQuery; Popper v1 → v2; Sass compilado com Dart Sass.
- **Navegadores:** dropa IE 10/11 e Edge legado.
- **Grid:** novo breakpoint `xxl` (≥1400px); gutters em rem (1.5rem); classes `.g-*`, `.gx-*`, `.gy-*`; `.no-gutters` → `.g-0`.
- **RTL / propriedades lógicas:** `left/right` → `start/end` (`.ms-*`, `.me-*`, `.ps-*`, `.pe-*`, `.float-start`, `.text-end`, `.border-start`…).
- **Formulários:** `.custom-*` unificados (`.form-check`, `.form-select`, `.form-range`, `.form-switch`); `.form-group`, `.form-row` e `.form-inline` removidos; label pede `.form-label`; *floating labels*; `.input-group-append/prepend` removidos.
- **Componentes novos:** Accordion, Offcanvas.
- **Componentes removidos:** Jumbotron, `.media`, `.card-deck`, `.card-columns`.
- **Renomeados:** `.close` → `.btn-close`; `.badge-primary` → `.bg-primary`; `.badge-pill` → `.rounded-pill`; `.btn-block` → `.d-grid` + `.gap-*`; `.sr-only` → `.visually-hidden`; `.font-weight-*` → `.fw-*`; `.font-italic` → `.fst-italic`; `.embed-responsive-16by9` → `.ratio-16x9`.
- **Utilitários novos:** `.fs-*`, `.lh-*`, `.d-grid` + `.gap`, posição (`.top-0`, `.start-50`…), `.translate-middle`.
- **Conteúdo:** links sublinhados por padrão; RFS (tipografia responsiva) ligado por padrão; tabelas refeitas com CSS variables.
- **JavaScript:** plugins em JS puro; atributos `data-bs-*`; `new bootstrap.Modal('#id')` aceita seletor CSS.

### 5.1.0
CSS Grid experimental (opt-in via Sass), offcanvas dentro do navbar, componente *placeholder*,
collapse horizontal, `.hstack`/`.vstack`/`.vr`, CSS variables no `:root`, utilitários de opacidade de texto e fundo.

### 5.2.0
Visual refinado (border-radius), **todos os componentes com CSS variables**, `_maps.scss` separado,
`.fw-semibold`, `.rounded-4/5`, offcanvas responsivo (`.offcanvas-lg`…), `.text-bg-{cor}`,
`.table-striped-columns`, `.table-group-divider`, Scrollspy reescrito com Intersection Observer.

### 5.3.0
**Color modes:** `data-bs-theme="light|dark"` no `<html>` ou em qualquer elemento. Deprecados
`.navbar-dark`, `.dropdown-menu-dark`, `.btn-close-white` e `.carousel-dark`.
Paleta estendida (`-subtle`, `-emphasis`, `body-secondary`/`tertiary`); `.text-muted` → `.text-body-secondary`.
Novos: `.nav-underline`, `.icon-link`, `.focus-ring`, utilitários de link, `.z-*`, `.object-fit-*`,
`.overflow-x/y`, `.fw-medium`, `.d-inline-grid`, `.progress-stacked`. Progress bar com `role` no elemento externo.

## Como carregar a v5.3.8 (para os exercícios)

Sem jQuery e sem Popper separado, porque o `bundle` já inclui o Popper:

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
```

Testado em 23/09/2026: os dois respondem HTTP 200. O [Quick start oficial](https://getbootstrap.com/docs/5.3/getting-started/introduction/)
traz a versão com hash de integridade (`integrity`).
