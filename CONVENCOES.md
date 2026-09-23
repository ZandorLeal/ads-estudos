# Convenções

Regras deste repositório. Poucas, e todas verificáveis.

## O que entra aqui

Só **trabalho próprio a partir de fontes públicas**:

| Pasta | Conteúdo |
|---|---|
| `disciplinas/periodo-N/<m>-<disciplina>/pre/` | estudo antes/além da aula |
| `disciplinas/periodo-N/<m>-<disciplina>/pratica/` | exercícios e código próprios que não valem nota |
| `disciplinas/_comum/` | ambiente e projetos que cruzam disciplinas |

**Nunca entra:** material da instituição, anotação de aula, atividade avaliada. Na dúvida, fica de fora.
O `.gitignore` em lista branca e o hook de pre-commit reforçam isso (ver [README](README.md#depois-de-clonar)).

## Marcação

Toda afirmação é **Fato** (com fonte), **Ideia** (hipótese, sem comprovação) ou **Pendência** (a confirmar).

## Nomes

- `kebab-case`, sem acento, em português.
- Disciplina: `<modulo>-<nome>`, com módulo `a` ou `b` (`a-desenvolvimento-frontend`).
- Pastas só quando houver conteúdo.

## Commits

Conventional Commits em português: `tipo(escopo): descrição`.
Tipos: `feat` (conteúdo novo) · `docs` · `fix` · `chore`. Escopo: a disciplina (`frontend`, `logica`…),
`ambiente` ou `regras`.

Exemplo: `feat(dinamico): pré-estudo de fetch com async/await`.
