---
id: bad82fee1322bd9aedf08721
title: Was absolute und relative Einheiten unterscheidet
challengeType: 0
videoUrl: 'https://scrimba.com/c/cN66JSL'
forumTopicId: 301089
dashedName: understand-absolute-versus-relative-units
---

# --description--

The last several challenges all set an element's margin or padding with pixels (`px`). Pixels are a type of length unit, which is what tells the browser how to size or space an item. In addition to `px`, CSS has a number of different length unit options that you can use.

Grundsätzlich unterscheidet man zwischen absoluten und relativen Längeneinheiten. Absolute Einheiten beziehen sich auf physikalische Längeneinheiten. Zum Beispiel beziehen sich `in` und `mm` auf Inch und Millimeter. Absolute Längeneinheiten nähern sich den realen Maßen auf dem Bildschirm an, aber es gibt Unterschiede, je nach Bildschirmauflösung.

Relative Einheiten wie `em` oder `rem` sind relativ zu einem anderen Längenwert. Beispielsweise basiert `em` auf der Schriftgröße eines Elements. Wenn man es verwendet, um die `font-size`-Eigenschaft selbst zu definieren, ist es relativ zur `font-size` des Elternelements.

**Hinweis:** Es gibt mehrere relative Einheiten die von der Größe des Viewports (deutsch etwa: Ansichtsfenster) abgeleitet werden. Sie werden im Bereich Responsive Web Design Prinzipien behandelt.

# --instructions--

Füge eine `padding`-Eigenschaft zum Element mit der Klasse `red-box` hinzu und setze sie auf `1.5em`.

# --hints--

Deine Klasse `red-box` sollte eine `padding`-Eigenschaft haben.

```js
const redBox =document.querySelector('.red-box'); 
const style = window.getComputedStyle(redBox); 

assert.notEqual(style['padding-top'], '0px');
assert.notEqual(style['padding-right'], '0px');
assert.notEqual(style['padding-bottom'], '0px');
assert.notEqual(style['padding-left'], '0px');
```

Deine Klasse `red-box` sollte Elementen einen `padding` von 1.5em zuweisen.

```js
assert.match(__helpers.removeCssComments(code), /\.red-box\s*?{[\s\S]*padding\s*:\s*?1\.5em/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  .injected-text {
    margin-bottom: -25px;
    text-align: center;
  }

  .box {
    border-style: solid;
    border-color: black;
    border-width: 5px;
    text-align: center;
  }

  .yellow-box {
    background-color: yellow;
    padding: 20px 40px 20px 40px;
  }

  .red-box {
    background-color: red;
    margin: 20px 40px 20px 40px;

  }

  .green-box {
    background-color: green;
    margin: 20px 40px 20px 40px;
  }
</style>
<h5 class="injected-text">margin</h5>

<div class="box yellow-box">
  <h5 class="box red-box">padding</h5>
  <h5 class="box green-box">padding</h5>
</div>
```

# --solutions--

```html
<style>
  .injected-text {
    margin-bottom: -25px;
    text-align: center;
  }

  .box {
    border-style: solid;
    border-color: black;
    border-width: 5px;
    text-align: center;
  }

  .yellow-box {
    background-color: yellow;
    padding: 20px 40px 20px 40px;
  }

  .red-box {
    background-color: red;
    margin: 20px 40px 20px 40px;
    padding: 1.5em;
  }

  .green-box {
    background-color: green;
    margin: 20px 40px 20px 40px;
  }
</style>
<h5 class="injected-text">margin</h5>

<div class="box yellow-box">
  <h5 class="box red-box">padding</h5>
  <h5 class="box green-box">padding</h5>
</div>
```
