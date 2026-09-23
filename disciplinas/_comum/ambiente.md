# Ambiente de desenvolvimento (comum)

Configurado uma vez, usado por várias disciplinas. A organização do repo está no [`README`](../../README.md).

## O que o curso usou (fato, pelos READMEs dos repos oficiais de 2024)

| Item | Usado em aula | Disciplinas |
|---|---|---|
| Editor | VSCode (+ extensão Code Runner) | FrontEnd, Dinâmico, Programação II |
| Runtime JS | Node.js ("versão mais recente") | Dinâmico, Programação II |
| Navegador | Google Chrome | todas de front |
| SO | Windows 10/11 | — (não é requisito) |
| Mais tarde | IntelliJ, Java 17+, MySQL, MongoDB Compass, Postman | Framework, Programação II |

## Sua máquina (verificado em 23/09/2026)

| Item | Instalado | Referência atual |
|---|---|---|
| VSCode | 1.134.0 | — |
| Node.js | v22.14.0 | LTS atual: **v24.21.0 "Krypton"** (07/09/2026); mais recente: v26.10.0 ([nodejs.org](https://nodejs.org/dist/index.json)) |
| npm | 10.9.2 | — |
| Git | 2.43.0 | — |
| Java (JDK) | **não instalado** | LTS atual: **25**; mais recente: 27 ([Adoptium](https://api.adoptium.net/v3/info/available_releases)). O curso usou 17, 21 e 23 |
| Navegadores | Chrome, Chromium, Firefox | — |

**Ideia:** o Node 22 atende o 1º período (o `fetch` global está disponível desde o Node 18 e é estável
desde o 21). Atualizar para a LTS 24 é opcional e fica como **pendência sua**. Não mexi em nada.

## Pendências

- [ ] **Instalar um JDK** (necessário para os exemplos em Java da Lógica). Ideia: LTS 25, que roda código de 17/21 do curso
- [ ] Decidir se atualiza o Node para a LTS 24
- [ ] Instalar a extensão Code Runner no VSCode (opcional; o curso usa, mas `node arquivo.js` no terminal faz o mesmo)
