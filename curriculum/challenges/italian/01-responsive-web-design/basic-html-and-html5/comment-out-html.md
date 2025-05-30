---
id: bad87fee1348bd9aedf08804
title: Commentare l'HTML
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cGyGbca'
forumTopicId: 16782
dashedName: comment-out-html
---

# --description--

Remember that in order to start a comment, you need to use `<!--` and to end a comment, you need to use `-->`

Qui dovrai terminare il commento prima dell'inizio del tuo elemento `h2`.

# --instructions--

Commenta il tuo elemento `h1` e il tuo elemento `p`, ma non il tuo elemento `h2`.

# --hints--

Il tuo elemento `h1` dovrebbe essere commentato in modo da non essere visibile nella pagina.

```js
assert.isEmpty(document.querySelectorAll('h1'));
```

Il tuo elemento `h2` non dovrebbe essere commentato in modo da essere visibile nella pagina.

```js
assert.isNotEmpty(document.querySelectorAll('h2'));
```

Il tuo elemento `p` dovrebbe essere commentato in modo che non sia visibile sulla pagina.

```js
assert.isEmpty(document.querySelectorAll('p'));
```

Ciascuno dei tuoi commenti dovrebbe essere chiuso con `-->`.

```js
assert.isAbove(code.match(/[^fc]-->/g).length, 1);
```

Non dovresti modificare l'ordine degli elementi `h1` `h2` o `p` nel codice.

```js
assert.strictEqual(code.match(/<([a-z0-9]){1,2}>/g)[0],'<h1>');
assert.strictEqual(code.match(/<([a-z0-9]){1,2}>/g)[1],'<h2>');
assert.strictEqual(code.match(/<([a-z0-9]){1,2}>/g)[2],'<p>');
```

# --seed--

## --seed-contents--

```html
<!--
<h1>Hello World</h1>

<h2>CatPhotoApp</h2>

<p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
-->
```

# --solutions--

```html
<!--<h1>Hello World</h1>-->
<h2>CatPhotoApp</h2> 
<!--<p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p> -->
```
