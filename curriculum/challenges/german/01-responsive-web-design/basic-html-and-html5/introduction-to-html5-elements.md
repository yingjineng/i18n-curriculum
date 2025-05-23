---
id: bad87fee1348bd9aecf08801
title: Einführung in HTML5 Elemente
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cBkZGpt7'
forumTopicId: 301097
dashedName: introduction-to-html5-elements
---

# --description--

HTML5 introduces more descriptive HTML tags. These include `main`, `header`, `footer`, `nav`, `video`, `article`, `section` and others.

Diese Tags geben deinem HTML eine beschreibende Struktur, machen dein HTML leichter lesbar und helfen bei der Suchmaschinenoptimierung (SEO) und Barrierefreiheit. Der `main` -HTML5-Tag hilft Suchmaschinen und anderen Entwicklern, den Hauptinhalt deiner Seite zu finden.

Beispiel für die Verwendung, eines `main`-Elementes mit zwei darin verschachtelten Kindelementen:

```html
<main> 
  <h1>Hello World</h1>
  <p>Hello Paragraph</p>
</main>
```

**Hinweis:** Viele der neuen HTML5-Tags und ihre Vorteile werden im Abschnitt über angewandte Barrierefreiheit behandelt.

# --instructions--

Erstelle ein zweites `p`-Element mit folgendem kitty ipsum-Text: `Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.`

Erstelle dann ein `main`-Element und ordne nur die zwei `p` Elemente im `main`-Element an.

# --hints--

Du solltest 2 `p`-Elemente mit Kitty Ipsum Text haben.

```js
assert.lengthOf(document.querySelectorAll('p'),2);
```

Jedes deiner `p`-Elemente sollte ein schließendes Tag haben.

```js
assert.match(code,/<\/p>/g);
assert.strictEqual(code.match(/<\/p>/g).length,code.match(/<p/g).length);
```

Dein `p`-Element sollte die ersten Worte des mitgelieferten zusätzlichen `kitty ipsum`-Textes enthalten.

```js
assert.match(document.querySelectorAll('p')[1].textContent,/Purr\s+jump\s+eat/gi);
```

Dein Code sollte ein `main`-Element enthalten.

```js
assert.lengthOf(document.querySelectorAll('main'),1);
```

Das `main`-Element sollte zwei Absatzelemente (p) als Kinder haben.

```js
const main = document.querySelector('main');
const children = main.querySelectorAll("p"); 
assert.lengthOf(children,2);
```

Das öffnende `main`-Tag sollte vor dem ersten Absatz-Tag stehen.

```js
assert.match(code,(/<main>\s*?<p>/g));
```

Das schließende `main`-Tag sollte nach dem zweiten schließenden Absatz-Tag stehen.

```js
assert.match(code,(/<\/p>\s*?<\/main>/g));
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>

<p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```
