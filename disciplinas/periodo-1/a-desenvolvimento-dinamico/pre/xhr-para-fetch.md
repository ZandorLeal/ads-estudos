# XMLHttpRequest → fetch

Referência para estudar pelo jeito atual (`fetch` + `async/await`) sabendo o que o material do curso usa
(`XMLHttpRequest`, Módulo 14).

Aqui não existe "versão" como no Bootstrap. São recursos da plataforma web e da linguagem que foram
surgindo ao longo do tempo. O XHR **não foi deprecado** e continua funcionando; o `fetch` é o jeito moderno.

**Fontes (fato):**
- Compatibilidade de navegadores: [MDN browser-compat-data](https://github.com/mdn/browser-compat-data) (`api/_globals/fetch.json`, `api/XMLHttpRequest.json`), consultado em 23/09/2026.
- Node.js: [docs oficiais, globals → fetch](https://nodejs.org/api/globals.html#fetch), histórico de mudanças.
- Código do curso: [`Módulo 14 - Consumo de API/api.js`](https://github.com/FaculdadeDescomplica/DesenvolvimentoDinamico).

## Linha do tempo

| Marco | Quando | Observação |
|---|---|---|
| `XMLHttpRequest` | Chrome 1, Firefox 1, Safari 1.2, IE 7 | base do "AJAX"; baseado em callbacks (`onload`, `onerror`) |
| Promises (ES2015) | 2015 | base do `fetch`; o Módulo 10 do curso ("Promessas") cobre |
| `fetch` nos navegadores | Chrome 42 · Firefox 39 · Edge 14 · Safari 10.1 | retorna uma Promise |
| `async/await` (ES2017) | 2017 | escrever código com Promise como se fosse sequencial |
| `fetch` global no Node | **v18.0.0** sem flag · **estável desde v21.0.0** | antes precisava de `node-fetch` ou `axios` |

Sua máquina tem Node v22.14.0, então `fetch` já roda direto (ver `../../../_comum/ambiente.md`).

## O mesmo código, três jeitos

O exemplo do curso (resumido):

```js
// Curso (XMLHttpRequest, callbacks)
function fetchPosts() {
    var xmlHttpRequest = new XMLHttpRequest();
    xmlHttpRequest.open('GET', 'https://jsonplaceholder.typicode.com/posts', true);
    xmlHttpRequest.onload = function () {
        if (xmlHttpRequest.status >= 200 && xmlHttpRequest.status < 300) {
            var posts = JSON.parse(xmlHttpRequest.responseText);
            displayPosts(posts);
        } else {
            console.error('Failed to fetch posts:', xmlHttpRequest.statusText);
        }
    };
    xmlHttpRequest.onerror = function () {
        console.error('Failed to fetch posts');
    };
    xmlHttpRequest.send();
}
```

```js
// fetch com .then()
function fetchPosts() {
    fetch('https://jsonplaceholder.typicode.com/posts')
        .then(resposta => {
            if (!resposta.ok) throw new Error(`HTTP ${resposta.status}`);
            return resposta.json();
        })
        .then(posts => displayPosts(posts))
        .catch(erro => console.error('Failed to fetch posts:', erro.message));
}
```

```js
// fetch com async/await (o jeito atual)
async function fetchPosts() {
    try {
        const resposta = await fetch('https://jsonplaceholder.typicode.com/posts');
        if (!resposta.ok) throw new Error(`HTTP ${resposta.status}`);
        const posts = await resposta.json();
        displayPosts(posts);
    } catch (erro) {
        console.error('Failed to fetch posts:', erro.message);
    }
}
```

Testado em 23/09/2026 no Node v22.14.0: a versão `async/await` buscou os 100 posts.

## Diferenças que pegam

| Ponto | XMLHttpRequest | fetch |
|---|---|---|
| Estilo | callbacks (`onload`, `onerror`) | Promise (`.then` / `await`) |
| Corpo da resposta | `JSON.parse(xhr.responseText)` | `await resposta.json()` |
| Erro HTTP (404, 500) | cai no `onload`; você checa `status` | **não rejeita**: checar `resposta.ok` |
| Erro de rede | `onerror` | Promise rejeita → `catch` |
| Cancelar | `xhr.abort()` | `AbortController` + `signal` |
| Progresso de upload | `xhr.upload.onprogress` | sem equivalente direto |
| Node.js | não existe nativo | global desde o Node 18 |

**A armadilha principal:** `fetch` só rejeita em falha de rede. Um 404 chega como resposta
"bem-sucedida" com `ok === false`. Por isso todos os exemplos acima checam `resposta.ok`.

## Outras diferenças do material, fora da API

O material do curso usa `var` em alguns lugares. O atual é `const`/`let` (ES2015), e o próprio curso já
usa os dois no mesmo arquivo. Vale a mesma lógica: estudar pelo atual e reconhecer o antigo.
