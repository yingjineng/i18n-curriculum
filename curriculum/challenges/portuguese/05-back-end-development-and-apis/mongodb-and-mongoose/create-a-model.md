---
id: 587d7fb6367417b2b2512c07
title: Criar um modelo
challengeType: 2
forumTopicId: 301535
dashedName: create-a-model
---

# --description--

**C**RUD Part I - CREATE

Em primeiro lugar, precisamos de um schema. Cada schema mapeia para uma coleção do MongoDB. Ele define a forma dos documentos dentro daquela coleção. Os schemas são os blocos que compõem os modelos. Eles podem ser aninhados para criar modelos complexos, mas, neste caso, vamos simplificar as coisas. Um modelo permite que você crie instâncias de seus objetos, chamados documentos.

In servers, the interactions with the database happen in handler functions. Estas funções são executadas quando algum evento acontece (por exemplo, alguém atinge um endpoint na sua API). We'll follow the same approach in these exercises. A função `done()` é um callback que nos diz que podemos prosseguir após concluir uma operação assíncrona, como inserir, pesquisar, atualizar ou excluir. Ela segue a convenção do Node e deve ser chamada como `done(null, data)` quando houver sucesso, ou `done(err)` quando houver erro.

Aviso - Ao interagir com serviços remotos, podem ocorrer erros!

```js
/* Example */

const someFunc = function(done) {
  //... do something (risky) ...
  if (error) return done(error);
  done(null, result);
};
```

# --instructions--

Crie um schema de pessoa chamado `personSchema` com o seguinte formato:

* A required `name` field of type `String`
* Um campo `age` do tipo `Number`
* Um campo `favoriteFoods` do tipo `[String]`

Use os tipos de schemas básicos de Mongoose. Se você quiser, também pode adicionar mais campos, usar validadores simples, como required ou unique, e definir valores padrão. Veja nosso <a href="https://www.freecodecamp.org/news/introduction-to-mongoose-for-mongodb-d2a7aa593c57/" target="_blank" rel="noopener noreferrer nofollow">artigo sobre o Mongoose</a>.

Agora, crie um modelo a partir de `personSchema` e atribua-o à variável `Person` existente.

# --hints--

Você deve criar uma instância de um esquema mongoose com sucesso

```js
  $.post(code + '/_api/mongoose-model', {
    name: 'Mike',
    age: 28,
    favoriteFoods: ['pizza', 'cheese']
  }).then(
    (data) => {
      assert.equal(data.name, 'Mike', '"model.name" is not what expected');
      assert.equal(data.age, '28', '"model.age" is not what expected');
      assert.isArray(
        data.favoriteFoods,
        '"model.favoriteFoods" is not an Array'
      );
      assert.include(
        data.favoriteFoods,
        'pizza',
        '"model.favoriteFoods" does not include the expected items'
      );
      assert.include(
        data.favoriteFoods,
        'cheese',
        '"model.favoriteFoods" does not include the expected items'
      );
    },
    (xhr) => {
      throw new Error(xhr.responseText);
    }
  );
```

