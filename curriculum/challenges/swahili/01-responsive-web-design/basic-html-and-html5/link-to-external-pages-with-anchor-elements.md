---
id: bad87fee1348bd9aedf08816
title: Unganisha kwa Kurasa za Nje na Vipengee vya Kuunganisha
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/c8EkncB'
forumTopicId: 18226
dashedName: link-to-external-pages-with-anchor-elements
---

# --description--

You can use `a` (*anchor*) elements to link to content outside of your web page.

Vipengele vya `a` vinahitaji anwani ya tovuti lengwa inayoitwa sifa ya  `href`. Pia vinahitaji maandishi ya maelezo. Hapa kuna mfano:

```html
<a href="https://www.freecodecamp.org">this links to freecodecamp.org</a>
```

Kisha kivinjari chako kitaonyesha maandishi `this links to freecodecamp.org` kama kiungo unachoweza kubofya. Na kiungo hicho kitakupeleka kwenye anwani ya wavuti `https://www.freecodecamp.org`.

# --instructions--

Unda kipengele cha `a` kinachounganishwa na `https://www.freecatphotoapp.com` na kina "cat photos" kama maandishi yake ya maelezo.

# --hints--

Kipengele chako cha `a` kinafaa kuwa na maandishi ya `cat photos`.

```js
assert.match(document.querySelector('a').textContent,/cat photos/gi);
```

Unahitaji kipengele cha `a` kinachounganishwa na `https://www.freecatphotoapp.com`

```js
assert.match(document.querySelector('a').getAttribute('href'),/^https?:\/\/(www\.)?freecatphotoapp\.com\/?$/i);
```

Kipengele chako cha `a` kinapaswa kuwa na lebo ya kufunga.

```js
assert.match(code,/<\/a>/g);
assert.strictEqual(code.match(/<\/a>/g).length,code.match(/<a/g).length);
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>



  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back.">

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back.">

  <a href="https://www.freecatphotoapp.com">cat photos</a>
  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```
