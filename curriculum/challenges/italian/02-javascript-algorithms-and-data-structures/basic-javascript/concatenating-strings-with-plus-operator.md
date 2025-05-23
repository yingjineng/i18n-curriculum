---
id: 56533eb9ac21ba0edf2244b7
title: Concatenare le stringhe con l'operatore +
challengeType: 1
forumTopicId: 16802
dashedName: concatenating-strings-with-plus-operator
---

# --description--

In JavaScript, when the `+` operator is used with a `String` value, it is called the <dfn>concatenation</dfn> operator. You can build a new string out of other strings by <dfn>concatenating</dfn> them together.

**Esempio**

```js
'My name is Alan,' + ' I concatenate.'
```

**Nota:** Attenzione agli spazi. La concatenazione non aggiunge spazi tra le stringhe concatenate, quindi dovrai aggiungerli tu stesso.

Esempio:

```js
const ourStr = "I come first. " + "I come second.";
```

La stringa `I come first. I come second.` sarebbe visualizzata nella console.
# --instructions--

Costruisci `myStr` dalle stringhe `This is the start.` e `This is the end.` usando l'operatore `+`. Assicurati di includere uno spazio tra le due stringhe.

# --hints--

`myStr` dovrebbe avere un singolo spazio tra le due stringhe.

```js
assert(/start\. This/.test(myStr));
```

`myStr` should have a value of the string `This is the start. This is the end.`

```js
assert(myStr === 'This is the start. This is the end.');
```

Dovresti usare l'operatore `+` per costruire `myStr`.

```js
assert(__helpers.removeJSComments(code).match(/(["']).*\1\s*\+\s*(["']).*\2/g));
```

`myStr` dovrebbe essere creato usando la parola chiave `const`.

```js
assert(/const\s+myStr/.test(__helpers.removeJSComments(code)));
```

Dovresti assegnare il risultato alla variabile `myStr`.

```js
assert(/myStr\s*=/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
(function(){
  if(typeof myStr === 'string') {
    return 'myStr = "' + myStr + '"';
  } else {
    return 'myStr is not a string';
  }
})();
```

## --seed-contents--

```js
const myStr = ""; // Change this line
```

# --solutions--

```js
const myStr = "This is the start. " + "This is the end.";
```
