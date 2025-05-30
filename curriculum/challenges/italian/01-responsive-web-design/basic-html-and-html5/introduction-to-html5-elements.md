---
id: bad87fee1348bd9aecf08801
title: Introduzione agli elementi HTML5
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cBkZGpt7'
forumTopicId: 301097
dashedName: introduction-to-html5-elements
---

# --description--

HTML5 introduces more descriptive HTML tags. These include `main`, `header`, `footer`, `nav`, `video`, `article`, `section` and others.

Questi tag danno una struttura descrittiva al tuo HTML, rendono il tuo HTML più facile da leggere, e aiutano con l'ottimizzazione per i motori di ricerca (SEO, Search Engine Optimization) e l'accessibilità. Il tag HTML5 `main` aiuta i motori di ricerca e altri sviluppatori a trovare il contenuto principale della tua pagina.

Ecco come esempio di utilizzo un elemento `main` con due elementi figlio annidati al suo interno:

```html
<main> 
  <h1>Hello World</h1>
  <p>Hello Paragraph</p>
</main>
```

**Nota:** Molti dei nuovi tag HTML5 e i loro vantaggi sono coperti nella sezione Accessibilità Applicata.

# --instructions--

Crea un secondo elemento `p` con il seguente testo ipsum kitty: `Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.`

Crea quindi un elemento `main` e annida solo i due elementi `p` all'interno dell'elemento `main`.

# --hints--

Dovresti avere 2 elementi `p` con il testo Kitty Ipsum.

```js
assert.lengthOf(document.querySelectorAll('p'),2);
```

Ognuno dei tuoi elementi `p` dovrebbe avere un tag di chiusura.

```js
assert.match(code,/<\/p>/g);
assert.strictEqual(code.match(/<\/p>/g).length,code.match(/<p/g).length);
```

Il tuo elemento `p` dovrebbe contenere le prime parole del testo aggiuntivo `kitty ipsum` fornito.

```js
assert.match(document.querySelectorAll('p')[1].textContent,/Purr\s+jump\s+eat/gi);
```

Il tuo codice dovrebbe avere un tag `main`.

```js
assert.lengthOf(document.querySelectorAll('main'),1);
```

L'elemento `main` dovrebbe avere due elementi paragrafo come figli.

```js
const main = document.querySelector('main');
const children = main.querySelectorAll("p"); 
assert.lengthOf(children,2);
```

Il tag `main` di apertura dovrebbe venire prima del primo tag di paragrafo.

```js
assert.match(code,(/<main>\s*?<p>/g));
```

Il tag `main` di chiusura dovrebbe venire dopo il secondo tag di chiusura di paragrafo.

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
