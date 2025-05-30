---
id: 56533eb9ac21ba0edf2244ae
title: Trovare un resto in JavaScript
challengeType: 1
forumTopicId: 18184
dashedName: finding-a-remainder-in-javascript
---

# --description--

The <dfn>remainder</dfn> operator `%` gives the remainder of the division of two numbers.

**Esempio**

<pre>
5 % 2 = 1
5 / 2 = 2 remainder 1
2 * 2 = 4
5 - 4 = 1
</pre>

**Uso**  
In matematica si può verificare se un numero è pari o dispari controllando il resto della divisione del numero per `2`. I numeri pari hanno un resto di `0`, mentre i numeri dispari un resto di `1`.

<pre>
17 % 2 = 1
48 % 2 = 0
</pre>

**Nota:** L'operatore <dfn>resto</dfn> è a volte erroneamente indicato come l'operatore del modulo. Esso è molto simile al modulo, ma non funziona correttamente con numeri negativi.

# --instructions--

Imposta `remainder` pari al resto di `11` diviso per `3` utilizzando l'operatore <dfn>resto</dfn> (`%`).

# --hints--

La variabile `remainder` dovrebbe essere inizializzata

```js
assert(/(const|let|var)\s+?remainder/.test(__helpers.removeJSComments(code)));
```

Il valore di `remainder` dovrebbe essere `2`

```js
assert(remainder === 2);
```

Dovresti utilizzare l'operatore `%`

```js
assert(/\s+?remainder\s*?=\s*?.*%.*;?/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function (y) {
  return 'remainder = ' + y;
})(remainder);
```

## --seed-contents--

```js
const remainder = 0;
```

# --solutions--

```js
const remainder = 11 % 3;
```
