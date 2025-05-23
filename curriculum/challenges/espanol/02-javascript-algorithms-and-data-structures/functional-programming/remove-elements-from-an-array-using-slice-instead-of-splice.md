---
id: 9d7123c8c441eeafaeb5bdef
title: Remueve elementos de un arreglo usando slice en lugar de splice
challengeType: 1
forumTopicId: 301236
dashedName: remove-elements-from-an-array-using-slice-instead-of-splice
---

# --description--

Un patrón común al trabajar con arreglos es cuando deseas eliminar elementos y conservar el resto del arreglo. JavaScript ofrece el método `splice` para esto, que toma argumentos para el índice de dónde comenzar a eliminar elementos, luego la cantidad de elementos para eliminar. Si no se proporciona el segundo argumento, el valor predeterminado es eliminar elementos hasta el final. Sin embargo, el método `splice` muta el arreglo original en el que se llama. Aquí hay un ejemplo:

```js
const cities = ["Chicago", "Delhi", "Islamabad", "London", "Berlin"];
cities.splice(3, 1);
```

Aquí `splice` devluelve la "string" `London` y la elimina del arreglo `cities`. `cities` tendrá el valor de `["Chicago", "Delhi", "Islamabad", "Berlin"]`.

Como vimos en el último desafío, el método `slice` no muta el arreglo original, pero devuelve uno nuevo que puede ser guardado en una variable. Recuerda que el método `slice` recibe dos argumentos para indicar el comienzo y el final del segmento (el final es no inclusivo) y retorna estos elementos en un nuevo arreglo. Usar el método `slice` en lugar de `splice` ayuda a prevenir cualquier efecto colateral de mutar un arreglo.

# --instructions--

Reescribe la función `nonMutatingSplice` usando `slice` en lugar de `splice`. Debe limitar el arreglo proporcionado `cities` a una longitud de 3 y devolver un nuevo arreglo con solo los primeros tres elementos.

No modifiques el arreglo original proporcionado en la función.

# --hints--

Tu código debe usar el método `slice`.

```js
assert(__helpers.removeJSComments(code).match(/\.slice/g));
```

Tu código no debe usar el método `splice`.

```js
assert(!__helpers.removeJSComments(code).match(/\.?[\s\S]*?splice/g));
```

No debes mutar el array original pasado a la función.

```js
assert.deepEqual(_inputCities, ["Chicago", "Delhi", "Islamabad", "London", "Berlin"]);
```

`nonMutatingSplice(["Chicago", "Delhi", "Islamabad", "London", "Berlin"])` debe devolver `["Chicago", "Delhi", "Islamabad"]`.

```js
assert.deepEqual(nonMutatingSplice(_inputCities), ["Chicago", "Delhi", "Islamabad"]);
```

# --seed--

## --seed-contents--

```js
function nonMutatingSplice(cities) {

  return cities.splice(3);
}
```

## --after-user-code--

```js
const _inputCities = ["Chicago", "Delhi", "Islamabad", "London", "Berlin"];
```

# --solutions--

```js
function nonMutatingSplice(cities) {
  return cities.slice(0,3);
}
```
