---
id: 637f704072c65bc8e73dfe36
videoId: tsEQgGjSmkM
title: Links and Images Lesson A
challengeType: 15
dashedName: links-and-images-lesson-a
---

# --description--

Per prendere la mano con l'utilizzo di link e immagini, in questa lezione avrai bisogno di un progetto HTML su cui lavorare.

- Crea una nuova cartella chiamata `odin-links-and-images`.

- All'interno di questa cartella crea un nuovo file chiamato `index.html`.

- Inserisci il solito boilerplate HTML.

- Infine, aggiungi il seguente `h1` al `body`: `<h1>Homepage</h1>`

## Elementi di ancoraggio
Per creare un link in HTML, si utilizza l'elemento di ancoraggio. An anchor element is defined by wrapping the text or another HTML element you want to be a link with an `<a>` tag.

Add the following to the `body` of the `index.html` page you created and open it in the browser:

```html
<a>click me</a>
```

You may have noticed that clicking this link doesn’t do anything. This is because an anchor tag on its own won’t know where you want to link to. You have to tell it a destination to go to. You do this by using an HTML attribute.

An HTML attribute gives additional information to an HTML element and always goes in the element’s opening tag. An attribute is usually made up of two parts: a name, and a value; however, not all attributes require a value. In your case, you need to add an `href` (hyperlink reference) attribute to the opening anchor tag. The value of the `href` attribute is the destination you want your link to go to.

Add the following `href` attribute to the anchor element you created previously and try clicking it again, don’t forget to refresh the browser so the new changes can be applied.

```html
<a href="https://www.theodinproject.com/about">click me</a>
```

By default, any text wrapped with an anchor tag without an `href` attribute will look like plain text. If the `href` attribute is present, the browser will give the text a blue color and underline it to signify it is a link.

It’s worth noting you can use anchor tags to link to any kind of resource on the internet, not just other HTML documents. You can link to videos, pdf files, images, and so on, but for the most part, you will be linking to other HTML documents.

# --assignment--

Watch Kevin Powell’s HTML Links video above.

# --questions--

## --text--

What HTML tag is used to create a link?

## --answers--

`<a>`

---

`<p>`

---

`<ol>`

## --video-solution--

1
