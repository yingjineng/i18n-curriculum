---
id: cf1111c1c11feddfaeb9bdef
title: Gerar frações aleatórias com JavaScript
challengeType: 1
forumTopicId: 18185
dashedName: generate-random-fractions-with-javascript
---

# --description--

Números aleatórios são úteis para criar comportamento aleatório.

JavaScript tem a função `Math.random()` que gera um número decimal aleatório entre `0` (incluso) e `1` (excluso). Assim, `Math.random()` pode retornar um `0` mas nunca retornará `1`.

**Observação:** de modo semelhante ao que usamos ao <a href="/portuguese/learn/javascript-algorithms-and-data-structures/basic-javascript/storing-values-with-the-assignment-operator" target="_blank" rel="noopener noreferrer nofollow">armazenar valores com operador de atribuição</a>, todas as chamadas de função serão resolvidas antes da execução da instrução `return`. Assim, poderemos usar a instrução `return` para devolver o valor da função `Math.random()`.

# --instructions--

Altere `randomFraction` para retornar um número aleatório ao invés de retornar `0`.

# --hints--

`randomFraction` deve retornar um número aleatório.

```js
assert(typeof randomFraction() === 'number');
```

O número retornado por `randomFraction` deve ser um decimal.

```js
assert((randomFraction() + '').match(/\./g));
```

Você deve estar usando `Math.random` para gerar o número decimal aleatório.

```js
assert(__helpers.removeJSComments(code).match(/Math\.random/g).length >= 0);
```

# --seed--

## --after-user-code--

```js
(function(){return randomFraction();})();
```

## --seed-contents--

```js
function randomFraction() {

  // Only change code below this line

  return 0;

  // Only change code above this line
}
```

# --solutions--

```js
function randomFraction() {
  return Math.random();
}
```
