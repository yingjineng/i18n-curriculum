---
id: 63ee35300d8d4841c3a7091d
title: CSS Foundations Lesson D
challengeType: 19
dashedName: css-foundations-lesson-d
---

# --description--

Eine weitere Variante der Verwendung von Selektoren ist die Verkettung in Form einer Liste ohne jegliche Trennung. Angenommen du hattest die folgende HTML:

```html
<div>
  <div class="subsection header">Latest Posts</div>
  <p class="subsection preview">This is where a preview for a post might go.</p>
</div>
```

Du hast zwei Elemente mit der `subsection`-Klasse, die eine Art von einzigartigen Stilen haben, aber was passiert, wenn du eine separate Regel nur auf das Element anwenden willst, das auch `header` als zweite Klasse hat? Nun, du könntest die beiden `class`-Selektoren in deinem CSS folgendermaßen miteinander verketten:

```css
.subsection.header {
  color: red;
}
```

`.subsection.header` wählt jedes Element aus, das sowohl die `subsection`- als auch die `header`-Klasse hat. Beachte, dass zwischen den `.subsection`- und `.header` `class`-Selektoren kein Leerzeichen steht. Diese Syntax ist grundsätzlich für die Verkettung beliebiger Kombinationen von Selektoren geeignet, mit Ausnahme der Verkettung von mehr als einem Typ-Selektor.

Auf diese Weise können auch eine Klasse und eine ID verkettet werden, wie nachstehend gezeigt:

```html
<div>
  <div class="subsection header">Latest Posts</div>
  <p class="subsection" id="preview">This is where a preview for a post might go.</p>
</div>
```

Du kannst die beiden oben genannten Elemente mit den folgenden kombinieren:

```css
.subsection.header {
  color: red;
}

.subsection#preview {
  color: blue;
}
```

Im Allgemeinen kannst du nicht mehr als einen Typ-Selektor verketten, da ein Element nicht zwei verschiedene Typen gleichzeitig sein kann. For example, chaining two type selectors like `div` and `p` would give us the selector `divp`, which wouldn’t work since the selector would try to find a literal `<divp>` element, which doesn’t exist.

# --questions--

## --text--

Wie würdest du beide Attribute für eine einzige Regel verwenden, wenn ein Element angibt, das eine `id` von `title` und eine `class` von `primary` hat?

## --answers--

```css
.title.primary {
  ...
}
```

---

```css
.title > primary {
  ...
}
```

---

```css
#title.primary { 
  ...
}
```


## --video-solution--

3
