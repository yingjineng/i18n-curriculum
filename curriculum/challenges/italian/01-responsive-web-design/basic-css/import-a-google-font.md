---
id: bad87fee1348bd9aedf08807
title: Importare un font Google
challengeType: 0
videoUrl: 'https://scrimba.com/c/cM9MRsJ'
forumTopicId: 18200
dashedName: import-a-google-font
---

# --description--

In addition to specifying common fonts that are found on most operating systems, we can also specify non-standard, custom web fonts for use on our website. There are many sources for web fonts on the Internet. For this example we will focus on the Google Fonts library.

Google Fonts è una libreria gratuita di font che puoi utilizzare in CSS facendo riferimento all'URL del font.

Quindi, andiamo avanti e importiamo e applichiamo un carattere di Google (nota che se Google è bloccato nel vostro paese, dovrai saltare questa fase).

Per importare un font Google, puoi copiare l'URL del font dalla libreria di font Google e poi incollarlo nel tuo HTML. Per questa sfida, importeremo il font `Lobster`. Per fare questo, copia la seguente linea di codice e incollala nella parte superiore dell'editor di codice (prima dell'elemento di apertura `style`):

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
```

Ora puoi usare il carattere `Lobster` nel tuo CSS usando `Lobster` come FAMILY_NAME come nell'esempio seguente:

```css
font-family: FAMILY_NAME, GENERIC_NAME;
```

Il GENERIC_NAME è opzionale, ed è un carattere di ripiego nel caso in cui l'altro carattere specificato non sia disponibile. Questo aspetto viene affrontato nella prossima sfida.

I family name sono sensibili alle maiuscole e devono essere inseriti tra virgolette se c'è uno spazio nel nome. Ad esempio, hai bisogno delle virgolette per usare il carattere `"Open Sans"`, ma per non per usare il carattere `Lobster`.

# --instructions--

Importa il carattere `Lobster` nella tua pagina web. Usa quindi un selettore di elementi per impostare `Lobster` come `font-family` per il tuo elemento `h2`.

# --hints--

Devi importare il font `Lobster`.

```js
assert.exists(document.querySelector('link[href*="googleapis" i]'));
```

Il tuo elemento `h2` dovrebbe usare il font `Lobster`.

```js
const h2 = document.querySelector('h2'); 
const fontFamily = window.getComputedStyle(h2)['font-family']; 
assert.match(fontFamily, /lobster/i);
```

Dovresti utilizzare solo un selettore di elementi `h2` per cambiare il carattere.

```js
assert.match(__helpers.removeHtmlComments(code), /\s*[^\.]h2\s*\{\s*font-family\s*:\s*('|"|)Lobster\1\s*(,\s*('|"|)[a-z -]+\3\s*)?(;\s*\}|\})/gi);
```

Il tuo elemento `p` dovrebbe usare il font `monospace`.

```js
const paragraphElement = document.querySelector('p');
const fontFamily = window.getComputedStyle(paragraphElement)['font-family']; 
assert.match(fontFamily, /monospace/i);
```

# --seed--

## --seed-contents--

```html
<style>
  .red-text {
    color: red;
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
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  p {
    font-size: 16px;
    font-family: monospace;
  }

  h2 {
    font-family: Lobster;
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
