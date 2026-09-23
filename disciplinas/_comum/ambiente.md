# Ambiente de desenvolvimento

Configurado uma vez e usado por várias disciplinas. Verificado em 23/09/2026.

## Meu ambiente

**Ubuntu 24.04.4 LTS** (x86_64), shell **zsh 5.9**.

| Ferramenta | Instalado | Referência atual | Situação |
|---|---|---|---|
| Node.js (via nvm) | v22.14.0 (default do nvm: 22) | LTS **v24.21.0** "Krypton" (07/09/2026) · current v26.10.0 | atende o 1º período; LTS 24 é opcional |
| npm | 10.9.2 | vem com o Node | — |
| Java (JDK) | **não instalado** | LTS **25** · feature 27 | **necessário** para os exemplos em Java |
| Git | 2.43.0 (pacote do Ubuntu 24.04) | 2.55.0 | atende; a versão do Ubuntu é mais antiga, mas suficiente |
| VSCode | 1.134.0 | 1.139.0 | atualizar quando quiser |
| Navegadores | Chrome 151, Chromium 153 (snap), Firefox | — | ok |
| Python | 3.13.2 | — | não é usado no 1º período |

Fontes das versões atuais: [nodejs.org/dist](https://nodejs.org/dist/index.json),
[Adoptium](https://api.adoptium.net/v3/info/available_releases),
[VSCode releases](https://update.code.visualstudio.com/api/releases/stable),
[tags do git/git](https://github.com/git/git/tags).

### Pendências

- [ ] **Instalar um JDK** (LTS 25 roda o código de 17/21 que o curso usou). Como instalar no
      Ubuntu 24.04 ainda não foi decidido (apt, pacote Temurin da Adoptium ou SDKMAN); conferir
      qual oferece a 25 antes de escolher.
- [ ] Opcional: Node LTS 24 com `nvm install 24`. O nvm já está instalado, com v22.12.0 e v22.14.0.
- [ ] Opcional: atualizar o VSCode.

## Depois de clonar este repositório

O hook de pre-commit fica versionado em `.githooks/`, mas o git **não ativa hooks sozinho**.
Em cada clone, rode uma vez:

```sh
git config core.hooksPath .githooks
```

Conferir: `git config core.hooksPath` deve responder `.githooks`.

## O que o curso usou (referência)

Pelos READMEs dos repositórios oficiais das disciplinas (turmas de 2024):

| Item | Usado em aula | Disciplinas |
|---|---|---|
| Editor | VSCode (+ extensão Code Runner) | FrontEnd, Dinâmico, Programação II |
| Runtime JS | Node.js ("versão mais recente") | Dinâmico, Programação II |
| Navegador | Google Chrome | todas de front |
| Mais tarde | IntelliJ, Java 17+, MySQL, MongoDB Compass, Postman | Framework, Programação II |

O instrutor usou Windows 10/11. Isso **não é requisito**: todas essas ferramentas rodam no Linux.
A extensão Code Runner é opcional, porque `node arquivo.js` no terminal faz o mesmo.
