---
id: 587d78aa367417b2b2512aec
title: Head und Body eines HTML-Dokuments definieren
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cra9bfP'
forumTopicId: 301096
dashedName: define-the-head-and-body-of-an-html-document
---

# --description--

You can add another level of organization in your HTML document within the `html` tags with the `head` and `body` elements. Any markup with information about your page would go into the `head` tag. Then any markup with the content of the page (what displays for a user) would go into the `body` tag.

Metadatenelemente, wie `link`, `meta`, `title` und `style`, gehören typischerweise in das `head`-Element.

Hier ist ein Beispiel für das Layout einer Seite:

```html
<!DOCTYPE html>
<html>
  <head>
   <meta charset="utf-8">
   <title>Example title</title>
  </head>
  <body>
    <div>
    </div>
  </body>
</html>
```

# --instructions--

Bearbeite das Markup, damit es einen `head` und einen `body` gibt. Das `head`-Element sollte nur den `title` enthalten, und das `body`-Element sollte nur `h1` und `p` enthalten.

# --hints--

Es sollte nur ein `head`-Element geben.

```js
const headElems = code.replace(/\n/g, '').match(/\<head\s*>.*?\<\/head\s*>/g);
assert.exists(headElems); 
assert.lengthOf(headElems,1);
```

Es sollte nur ein `body`-Element auf der Seite vorhanden sein.

```js
const bodyElems = code.replace(/\n/g, '').match(/<body\s*>.*?<\/body\s*>/g);
assert.exists(bodyElems); 
assert.lengthOf(bodyElems,1);
```

Das `head`-Element sollte ein Kind des `html`-Elements sein.

```js
const htmlChildren = code
  .replace(/\n/g, '')
  .match(/<html\s*>(?<children>.*)<\/html\s*>/);
let foundHead;
if (htmlChildren) {
  const { children } = htmlChildren.groups;

  foundHead = children.match(/<head\s*>.*<\/head\s*>/);
}
assert.exists(foundHead);
```

Das `body`-Element sollte ein Kind des `html`-Elements sein.

```js
const htmlChildren = code
  .replace(/\n/g, '')
  .match(/<html\s*>(?<children>.*?)<\/html\s*>/);
let foundBody;
if (htmlChildren) {
  const { children } = htmlChildren.groups;
  foundBody = children.match(/<body\s*>.*<\/body\s*>/);
}
assert.exists(foundBody);
```

Das `head`-Element sollte das `title`-Element umschließen.

```js
const headChildren = code
  .replace(/\n/g, '')
  .match(/<head\s*>(?<children>.*?)<\/head\s*>/);
let foundTitle;
if (headChildren) {
  const { children } = headChildren.groups;
  foundTitle = children.match(/<title\s*>.*?<\/title\s*>/);
}
assert.exists(foundTitle);
```

Das `body`-Element sollte sowohl das `h1` als auch das `p`-Element umschließen.

```js
const bodyChildren = code
  .replace(/\n/g, '')
  .match(/<body\s*>(?<children>.*?)<\/body\s*>/);
let foundElems;
if (bodyChildren) {
  const { children } = bodyChildren.groups;
  const h1s = children.match(/<h1\s*>.*<\/h1\s*>/g);
  const ps = children.match(/<p\s*>.*<\/p\s*>/g);
  const numH1s = h1s ? h1s.length : 0;
  const numPs = ps ? ps.length : 0;
  foundElems = numH1s === 1 && numPs === 1;
}
assert.exists(foundElems);
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html>
  <title>The best page ever</title>

  <h1>The best page ever</h1>
  <p>Cat ipsum dolor sit amet, jump launch to pounce upon little yarn mouse, bare fangs at toy run hide in litter box until treats are fed. Go into a room to decide you didn't want to be in there anyway. I like big cats and i can not lie kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff. Meow i could pee on this if i had the energy for slap owner's face at 5am until human fills food dish yet scamper. Knock dish off table head butt cant eat out of my own dish scratch the furniture. Make meme, make cute face. Sleep in the bathroom sink chase laser but pee in the shoe. Paw at your fat belly licks your face and eat grass, throw it back up kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>

</html>
```

# --solutions--

```html
<!DOCTYPE html>
<html>
 <head>
  <title>The best page ever</title>
 </head>
 <body>
  <h1>The best page ever</h1>
  <p>Cat ipsum dolor sit amet, jump launch to pounce upon little yarn mouse, bare fangs at toy run hide in litter box until treats are fed. Go into a room to decide you didn't want to be in there anyway. I like big cats and i can not lie kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff. Meow i could pee on this if i had the energy for slap owner's face at 5am until human fills food dish yet scamper. Knock dish off table head butt cant eat out of my own dish scratch the furniture. Make meme, make cute face. Sleep in the bathroom sink chase laser but pee in the shoe. Paw at your fat belly licks your face and eat grass, throw it back up kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
 </body>
</html>
```
