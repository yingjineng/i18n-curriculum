---
id: bad87fee1348bd9aedf08808
title: Festlegen, in welcher Reihenfolge Schriftarten ersatzweise verwendet werden sollen
challengeType: 0
videoUrl: 'https://scrimba.com/c/cpVKBfQ'
forumTopicId: 18304
dashedName: specify-how-fonts-should-degrade
---

# --description--

There are several default fonts that are available in all browsers. These generic font families include `monospace`, `serif` and `sans-serif`.

Wenn eine Schriftart nicht verfügbar ist, kannst du dem Browser sagen, dass er zu einer anderen Schriftart "herabstufen" soll.

Wenn du z. B. möchtest, dass ein Element die Schriftart `Helvetica` verwendet, aber zur Schriftart `sans-serif` gewechselt werden soll, wenn `Helvetica` nicht verfügbar ist, gibst du es wie folgt an:

```css
p {
  font-family: Helvetica, sans-serif;
}
```

Bei generischen Schriftfamiliennamen wird nicht zwischen Groß- und Kleinschreibung unterschieden. Außerdem benötigen sie keine Anführungszeichen, da es sich um CSS-Schlüsselwörter handelt.

# --instructions--

Wende zunächst die Schriftart `monospace` auf das `h2`-Element an, so dass es jetzt zwei Schriftarten hat - `Lobster` und `monospace`.

In der letzten Aufgabe hast du die Schriftart `Lobster` mit dem `link`-Tag importiert. Kommentiere nun den Import der Schriftart `Lobster` (mit den HTML-Kommentaren, die du vorher gelernt hast) aus Google Fonts aus, damit sie nicht mehr verfügbar ist. Beachte wie dein `h2`-Element zur Schriftart `monospace` wechselt.

**Hinweis:** Wenn du die Schriftart `Lobster` auf deinem Computer installiert hast, wirst du die Veränderung nicht sehen, weil dein Browser die Schriftart finden kann.

# --hints--

Dein h2-Element sollte die Schriftart `Lobster` verwenden.

```js
const h2Element = document.querySelector('h2');
const fontFamily = window.getComputedStyle(h2Element)['font-family']; 
assert.match(fontFamily, /^"?lobster/i);
```

Dein h2-Element sollte zur Schriftart `monospace` wechseln, wenn `Lobster` nicht verfügbar ist.

```js
assert.match(__helpers.removeCssComments(code), /\s*h2\s*\{\s*font-family\s*\:\s*(\'|"|)Lobster\1\s*,\s*monospace\s*;?\s*\}/gi);
```

Du solltest deinen Abruf bei Google für die Schriftart `Lobster` auskommentieren, indem du `<!--` voranstellst.

```js
assert.match(code, /<!--[^fc]/gi);
```

Du solltest deinen Kommentar durch Hinzufügen von `-->` abschließen.

```js
assert.match(code, /[^fc]-->/gi);
```

# --seed--

## --seed-contents--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster;
  }

  p {
    font-size: 16px;
    font-family: monospace;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>
<main>
  <p class="red-text">Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <div>
    <p>Things cats love:</p>
    <ul>
      <li>catnip</li>
      <li>laser pointers</li>
      <li>lasagna</li>
    </ul>
    <p>Top 3 things cats hate:</p>
    <ol>
      <li>flea treatment</li>
      <li>thunder</li>
      <li>other cats</li>
    </ol>
  </div>

  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <label><input type="checkbox" name="personality" checked> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```

# --solutions--

```html
<!--<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">-->
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, monospace;
  }

  p {
    font-size: 16px;
    font-family: monospace;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>
<main>
  <p class="red-text">Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <div>
    <p>Things cats love:</p>
    <ul>
      <li>catnip</li>
      <li>laser pointers</li>
      <li>lasagna</li>
    </ul>
    <p>Top 3 things cats hate:</p>
    <ol>
      <li>flea treatment</li>
      <li>thunder</li>
      <li>other cats</li>
    </ol>
  </div>

  <form action="https://freecatphotoapp.com/submit-cat-photo">
    <label><input type="radio" name="indoor-outdoor" checked> Indoor</label>
    <label><input type="radio" name="indoor-outdoor"> Outdoor</label><br>
    <label><input type="checkbox" name="personality" checked> Loving</label>
    <label><input type="checkbox" name="personality"> Lazy</label>
    <label><input type="checkbox" name="personality"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
