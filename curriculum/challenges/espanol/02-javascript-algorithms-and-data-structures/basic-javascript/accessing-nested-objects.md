---
id: 56533eb9ac21ba0edf2244cc
title: Accede a objetos anidados
challengeType: 1
forumTopicId: 16161
dashedName: accessing-nested-objects
---

# --description--

Se puede acceder a las sub propiedades de objetos encadenando la notación de puntos o corchetes.

Aquí hay un objeto anidado:

```js
const ourStorage = {
  "desk": {
    "drawer": "stapler"
  },
  "cabinet": {
    "top drawer": { 
      "folder1": "a file",
      "folder2": "secrets"
    },
    "bottom drawer": "soda"
  }
};

ourStorage.cabinet["top drawer"].folder2;
ourStorage.desk.drawer;
```

`ourStorage.cabinet["top drawer"].folder2` sería la cadena `secrets` y `ourStorage.desk.drawer` sería la cadena `stapler`.

# --instructions--

Accede al objeto `myStorage` y asigna el contenido de la propiedad `glove box` a la variable `gloveBoxContents`. Utiliza la notación de puntos para todas las propiedades cuando sea posible, de lo contrario utiliza la notación de corchetes.

# --hints--

`gloveBoxContents` debe ser igual a la cadena `maps`.

```js
assert(gloveBoxContents === 'maps');
```

Tu código debe utilizar la notación por puntos, siempre que sea posible, para acceder a `myStorage`.

```js
assert.match(code, /myStorage\.car\.inside/);
```

`gloveBoxContents` debe ser declarado como `const`.

```js
assert.match(code, /const\s+gloveBoxContents\s*=/);
```

No debes cambiar el objeto `myStorage`.

```js
const expectedMyStorage = {
  "car":{
    "inside":{
      "glove box":"maps",
      "passenger seat":"crumbs"
    },
    "outside":{
      "trunk":"jack"
    }
  }
};
assert.deepStrictEqual(myStorage, expectedMyStorage);
```

# --seed--

## --after-user-code--

```js
(function(x) { 
  if(typeof x != 'undefined') { 
    return "gloveBoxContents = " + x;
  }
  return "gloveBoxContents is undefined";
})(gloveBoxContents);
```

## --seed-contents--

```js
const myStorage = {
  "car": {
    "inside": {
      "glove box": "maps",
      "passenger seat": "crumbs"
     },
    "outside": {
      "trunk": "jack"
    }
  }
};

const gloveBoxContents = undefined;
```

# --solutions--

```js
const myStorage = {
  "car":{
    "inside":{
      "glove box":"maps",
      "passenger seat":"crumbs"
    },
    "outside":{
      "trunk":"jack"
    }
  }
};
const gloveBoxContents = myStorage.car.inside["glove box"];
```
