---
id: 587d7fb6367417b2b2512c07
title: Crea un modelo
challengeType: 2
forumTopicId: 301535
dashedName: create-a-model
---

# --description--

**C**RUD Part I - CREATE

En primer lugar, necesitamos un esquema. Cada esquema asigna a una colección de MongoDB. Define la forma de los documentos dentro de esa colección. Los esquemas son bloques de construcción para los modelos. Pueden ser anidados para crear modelos complejos, pero en este caso las cosas serán sencillas. Un modelo te permite crear instancias de tus objetos, llamados documentos.

In servers, the interactions with the database happen in handler functions. Estas funciones se ejecutan cuando ocurre algún evento (por ejemplo, alguien golpea un endpoint en tu API). We'll follow the same approach in these exercises. La función `done()` es un callback que nos dice que podemos proceder después de completar una operación asincrónica como insertar, buscar, actualizar o eliminar. Sigue la convención de Node, y debe ser llamado como `done(null, data)` en caso de éxito, o `done(err)` en caso de error.

Advertencia: ¡Al interactuar con servicios remotos, pueden ocurrir errores!

```js
/* Example */

const someFunc = function(done) {
  //... do something (risky) ...
  if (error) return done(error);
  done(null, result);
};
```

# --instructions--

Crea un esquema de persona llamado `personSchema` con la siguiente forma:

* Un campo `name` obligatorio de tipo `String`
* Un campo `age` de tipo `Number`
* Un campo `favoriteFoods` de tipo `[String]`

Usa los tipos básicos de esquemas de Mongoose. Si quieres también puedes añadir más campos, utilizar validadores sencillos como required o unique, y establecer valores por defecto. Mira nuestro <a href="https://www.freecodecamp.org/news/introduction-to-mongoose-for-mongodb-d2a7aa593c57/" target="_blank" rel="noopener noreferrer nofollow">artículo sobre Mongoose </a>.

Ahora, crea un modelo a partir del `personSchema` y asígnalo a la variable existente `Person`.

# --hints--

La creación de una instancia a partir de un esquema mongoose debe ser exitosa

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

