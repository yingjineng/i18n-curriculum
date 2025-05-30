---
id: bad87fee1348bd8aedf06756
title: Überschreibe Klassendeklarationen durch Styling von ID-Attributen
challengeType: 0
videoUrl: 'https://scrimba.com/c/cRkpDhB'
forumTopicId: 18251
dashedName: override-class-declarations-by-styling-id-attributes
---

# --description--

We just proved that browsers read CSS from top to bottom in order of their declaration. That means that, in the event of a conflict, the browser will use whichever CSS declaration came last. Notice that if we even had put `blue-text` before `pink-text` in our `h1` element's classes, it would still look at the declaration order and not the order of their use!

Aber wir sind noch nicht fertig. Es gibt noch weitere Möglichkeiten, um CSS zu überschreiben. Erinnerst du dich an die ID-Attribute?

Lass uns deine Klassen `pink-text` und `blue-text` überschreiben und dein `h1`-Element orange färben, indem wir dem `h1`-Element eine ID geben und dann diese ID stylen.

# --instructions--

Gib deinem `h1`-Element das `id`-Attribut von `orange-text`. Erinnere dich daran, dass ID-Stile so aussehen:

```html
<h1 id="orange-text">
```

Belasse die Klassen `blue-text` und `pink-text` bei deinem `h1` Element.

Erstelle eine CSS-Deklaration für deine ID `orange-text` in deinem `style`-Element. Hier ist ein Beispiel dafür, wie das aussieht:

```css
#brown-text {
  color: brown;
}
```

**Hinweis:** Es spielt keine Rolle, ob du dieses CSS über oder unter der Klasse `pink-text` deklarierst, da das Attribut `id` immer Vorrang hat.

# --hints--

Dein `h1`-Element sollte die Klasse `pink-text` haben.

```js
assert.isTrue(document.querySelector('h1').classList.contains('pink-text'));
```

Dein `h1`-Element sollte die Klasse `blue-text` haben.

```js
assert.isTrue(document.querySelector('h1').classList.contains('blue-text'));
```

Dein `h1`-Element sollte die ID `orange-text` haben.

```js
assert.strictEqual(document.querySelector('h1').getAttribute('id'),'orange-text');
```

Es sollte nur ein `h1`-Element geben.

```js
assert.lengthOf(document.querySelectorAll('h1'), 1);
```

Dein ID `orange-text` sollte eine CSS-Deklaration haben.

```js
assert.match(__helpers.removeCssComments(code), /#orange-text\s*{/gi);
```

Dein `h1` sollte keine `style`-Attribute haben.

```js
assert.notMatch(__helpers.removeHtmlComments(code), /<h1.*style.*>/gi);
```

Dein `h1`-Element sollte orange sein.

```js
const h1Element = document.querySelector('h1');
const color = window.getComputedStyle(h1Element)['color']; 
assert.strictEqual(color, 'rgb(255, 165, 0)');
```

# --seed--

## --seed-contents--

```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  .pink-text {
    color: pink;
  }
  .blue-text {
    color: blue;
  }
</style>
<h1 class="pink-text blue-text">Hello World!</h1>
```

# --solutions--

```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  .pink-text {
    color: pink;
  }
  .blue-text {
    color: blue;
  }
  #orange-text {
    color: orange;
  }  
</style>
<h1 id="orange-text"  class="pink-text blue-text">Hello World!</h1>
```
