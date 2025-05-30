---
id: 587d78aa367417b2b2512aed
title: Оголошення типу документа Doctype HTML
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cra98AJ'
forumTopicId: 301095
dashedName: declare-the-doctype-of-an-html-document
---

# --description--

The challenges so far have covered specific HTML elements and their uses. However, there are a few elements that give overall structure to your page, and should be included in every HTML document.

У верхній частині вашого документа, вам необхідно вказати в браузері яку версію HTML ви використовуєте. HTML - мова, що розвивається і регулярно оновлюється. Більшість основних браузерів підтримують останню специфікацію, яка є HTML5. Проте, старші вебсторінки, можливо, використовують попередні версії мови.

Ви повідомляєте браузеру цю інформацію, додаючи тег `<!DOCTYPE ...>` у першому рядку, де частина `...` є версією HTML. Для HTML5, ви використовуєте `<!DOCTYPE html>`.

`!` та регістр `DOCTYPE` є важливими, особливо для старших браузерів. `html` не залежить від регістра.

Далі, решта HTML коду повинна бути оброблена в теги `html`. Відкриття `<html>` йде безпосередньо нижче рядка `<!DOCTYPE html>`, а закривання `</html>` йде внизу сторінки.

Ось приклад структури сторінки. Ваш HTML код буде між двома тегами `html`.

```html
<!DOCTYPE html>
<html>

</html>
```

# --instructions--

Додайте тег `DOCTYPE` для HTML5 вгорі пустого HTML-документа в редакторі кода. Під ним, додайте відкриття і закриття тегів `html`, які містяться навколо елементу `h1`. Заголовок може містити будь-який текст.

# --hints--

Ваш код повинен включати тег `<!DOCTYPE html>`.

```js
assert.match(code,/<!DOCTYPE\s+?html\s*?>/gi);
```

Має бути один елемент `html`.

```js
assert.lengthOf(document.querySelectorAll('html'), 1);
```

Теги `html` повинні бути пронумерованими навколо елементу `h1`.

```js
assert.match(code,/<html>\s*?<h1>\s*?.*?\s*?<\/h1>\s*?<\/html>/gi);
```

# --seed--

## --seed-contents--

```html

```

# --solutions--

```html
<!DOCTYPE html>
<html>
  <h1> Hello world </h1>
</html>
```
