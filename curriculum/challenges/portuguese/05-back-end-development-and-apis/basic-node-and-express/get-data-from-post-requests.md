---
id: 587d7fb2367417b2b2512bf8
title: Obter dados de solicitações de POST
challengeType: 2
forumTopicId: 301511
dashedName: get-data-from-post-requests
---

# --description--

Mount a POST handler at the path `/name`. It’s the same path as before. We have prepared a form in the html frontpage. It will submit the same data of exercise 10 (Query string). If the body-parser is configured correctly, you should find the parameters in the object `req.body`. Have a look at the usual library example:

<blockquote>route: POST '/library'<br>urlencoded_body: userId=546&#x26;bookId=6754 <br>req.body: {userId: '546', bookId: '6754'}</blockquote>

Responda com o mesmo objeto JSON usado antes: `{name: 'firstname lastname'}`. Teste se seu endpoint (URL) funciona usando o formulário html que fornecemos na página inicial do aplicativo.

Dica: existem vários outros métodos http além de GET e POST. Por convenção, existem correspondências entre o verbo http e a operação que você vai executar no servidor. O mapeamento convencional é:

POST (às vezes, PUT) – Cria um novo recurso usando a informação enviada com a requisição,

GET - Lê um recurso existente sem modificá-lo,

PUT ou PATCH (às vezes, POST) – Atualiza um recurso usando os dados enviados,

DELETE - Exclui um recurso.

Existem também alguns outros métodos que são usados para estabelecer uma conexão com o servidor. Exceto para o GET, todos os outros métodos listados acima podem ter uma carga (por exemplo, os dados no corpo da solicitação). O middleware body-parser também funciona com esses métodos.

# --hints--

Teste 1 : O endpoint (URL) da API deve responder com o nome correto

```js
  $.post(code + '/name', { first: 'Mick', last: 'Jagger' }).then(
    (data) => {
      assert.equal(
        data.name,
        'Mick Jagger',
        'Test 1: "POST /name" route does not behave as expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

Teste 2: O endpoint da API deve responder com o nome correto

```js
  $.post(code + '/name', {
    first: 'Keith',
    last: 'Richards'
  }).then(
    (data) => {
      assert.equal(
        data.name,
        'Keith Richards',
        'Test 2: "POST /name" route does not behave as expected'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

