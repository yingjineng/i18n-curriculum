---
id: 637f701c72c65bc8e73dfe31
title: Links and Images Lesson F
challengeType: 15
dashedName: links-and-images-lesson-f
---

# --description--

I siti web sarebbero abbastanza noiosi se si potesse visualizzare solo del testo. Fortunatamente l'HTML fornisce una grande varietà di elementi per la visualizzazione di contenuti di ogni sorta. Tra questi il più utilizzato è l'elemento immagine.

To display an image in HTML you use the `<img>` element. Unlike the other elements you have encountered, the `<img>` is a void element. Empty, void HTML elements do not need a closing tag.

Invece di racchiudere il contenuto tra un tag di apertura e uno di chiusura, incorpora un'immagine nella pagina usando un attributo `src` che indica al browser dove si trova il file dell'immagine. L'attributo `src` funziona in modo simile all'attributo `href` per i tag di ancoraggio. Può incorporare un'immagine usando sia percorsi assoluti che relativi.

Ad esempio, utilizzando un percorso assoluto è possibile visualizzare un'immagine situata sul sito di The Odin Project:

<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_1" scrolling="no" src="https://codepen.io/TheOdinProjectExamples/embed/gORbExZ?height=300&amp;theme-id=dark&amp;default-tab=html%2Cresult&amp;slug-hash=gORbExZ&amp;user=TheOdinProjectExamples&amp;name=cp_embed_1" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_gORbExZ"></iframe>

Per utilizzare le immagini che hai sui tuoi siti web, puoi usare un percorso relativo.

- Crea una nuova cartella chiamata `images` all'interno del progetto `odin-links-and-images`.

- Next, download <a href="https://unsplash.com/photos/Mv9hjnEUHR4/download?force=true&w=640" target="_blank">this image</a> and move it into the images directory you just created.

- Rinomina l'immagine in `dog.jpg`.

Infine aggiungi l'immagine al file `index.html`:

```html
<body>
  <h1>Homepage</h1>
    <a href="https://www.theodinproject.com/about">click me</a>

    <a href="pages/about.html">About</a>

    <img src="images/dog.jpg">
</body>
```

Salva il file `index.html` e aprilo in un browser per vedere Charles in tutta la sua gloria.


## Cartelle genitori

E se volessi utilizzare l'immagine del cane nella pagina `about`? Dovresti salire di un livello dalla cartella pages fino alla sua cartella genitore in modo da poter accedere alla cartella images.

Per passare alla cartella genitore devi usare due punti nel percorso relativo, così: `../.` Vediamo come funziona: all'interno del `body` del file `about.html`, aggiungi la seguente immagine sotto l'intestazione che hai aggiunto precedentemente:

```html
<img src="../images/dog.jpg">
```

Analizziamo questo passaggio:

- Prima di tutto, stai passando alla cartella genitore della cartella pages, che è `odin-links-and-images`.

- Poi, dalla cartella genitore puoi passare alla cartella `images`.

- Infine, puoi accedere al file `dog.jpg`.

Usando la metafora che abbiamo utilizzato prima, usare `../` nel percorso è un po' come uscire dalla stanza in cui ti trovi per andare nel corridoio e poter accedere a un'altra stanza.

## Attributo alt

Oltre all'attributo `src`, ogni elemento di immagine dovrebbe avere anche un attributo `alt` (testo alternativo).

L'attributo `alt` viene usato per descrivere un'immagine. Viene usato al posto dell'immagine nel caso questa non possa essere caricata. Viene utilizzato anche dai lettori di schermo per descrivere l'immagine agli utenti ipovedenti.

Ecco come risulta l'esempio che hai usato precedentemente del logo di The Odin Project con un attributo alt incluso:
<iframe allowfullscreen="true" allowpaymentrequest="true" allowtransparency="true" class="cp_embed_iframe " frameborder="0" height="300" width="100%" name="cp_embed_2" scrolling="no" src="https://codepen.io/TheOdinProjectExamples/embed/ExXjoEp?height=300&amp;theme-id=dark&amp;default-tab=html%2Cresult&amp;slug-hash=ExXjoEp&amp;user=TheOdinProjectExamples&amp;name=cp_embed_2" style="width: 100%; overflow:hidden; display:block;" title="CodePen Embed" loading="lazy" id="cp_embed_ExXjoEp"></iframe>

# --questions--

## --text--

Di quali due attributi hanno sempre bisogno le immagini?

## --answers--

`href` e `alt`

---

`name` e `href`

---

`alt` e `src`

## --video-solution--

3
