# ADS — estudos

Material de estudo da graduação em Análise e Desenvolvimento de Sistemas (cursando, início em 2026.4).

Aqui fica só trabalho próprio feito a partir de fontes públicas: pré-estudos, notas de versão e
prática. Material da instituição, anotações de aula e atividades avaliadas ficam fora deste repositório.

## Organização

Regras do repositório (o que entra, nomes, commits): [`CONVENCOES.md`](CONVENCOES.md).

```
disciplinas/
├── _comum/
│   ├── ambiente.md        ← setup de desenvolvimento usado por várias disciplinas
│   └── projetos/          ← projetos que cruzam disciplinas
└── periodo-N/<modulo>-<disciplina>/
    ├── pre/               ← pré-estudo
    └── pratica/           ← exercícios próprios
```

## Depois de clonar

```sh
git config core.hooksPath .githooks
```

O git não ativa hooks versionados sozinho. Sem esse comando, o pre-commit abaixo não roda.

**Proteções contra publicar material privado**, da mais forte para a mais fraca:
1. **`.gitignore` em lista branca:** só entra o que está em `pre/`, `pratica/` e `_comum/`, além dos READMEs.
   Vale em qualquer clone, sem instalar nada.
2. **`.githooks/pre-commit`:** recusa PDF, Office e as pastas `fontes/`, `avaliacoes/`, `anotacoes/`,
   `turma/` e `ingresso/`, mesmo com `git add -f`. Precisa do comando acima e pode ser pulado
   com `--no-verify`.

## Pré-estudos

- [Bootstrap 4.5.2 → 5.3.8](disciplinas/periodo-1/a-desenvolvimento-frontend/pre/bootstrap-4.5.2-para-5.3.8.md): o que mudou entre a versão usada no material e a atual
- [XMLHttpRequest → fetch](disciplinas/periodo-1/a-desenvolvimento-dinamico/pre/xhr-para-fetch.md): o mesmo código em três estilos

## Projetos

_Nenhum ainda._
