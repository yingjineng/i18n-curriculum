---
id: 5f356ed6cf6eab5f15f5cfe6
title: 步骤 20
challengeType: 0
dashedName: step-20
---

# --description--

The `div` element is used mainly for design layout purposes, unlike the other content elements you have used so far. Add a `div` element inside the `body` element and then move all the other elements inside the new `div`.

在 `div` 开始标签中，添加一个值为 `menu` 的 `id` 属性。

# --hints--

你的 `div` 开始标签的 `id` 属性值应为 `menu`。

```js
assert.strictEqual(document.querySelector('div')?.id, 'menu');
```

你应该有一个 `</div>` 结束标签。

```js
assert.match(code, /<\/div>/i);
```

你不应该改变你现有的 `body`元素。 确保你没有删除结束标签。

```js
assert.lengthOf(document.querySelectorAll('body'), 1);
```

Your `div` element should be nested in the `body`.

```js
assert.equal(document.querySelector('div')?.parentElement?.tagName, 'BODY');
```

You should move all the other elements inside the new `div`.

```js
assert.lengthOf(document.querySelector('body > div#menu > main')?.children, 3);
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Cafe Menu</title>
    <link href="styles.css" rel="stylesheet"/>
  </head>
--fcc-editable-region--
  <body>
    <main>
      <h1>CAMPER CAFE</h1>
      <p>Est. 2020</p>
      <section>
        <h2>Coffee</h2>
      </section>
    </main>
  </body>
--fcc-editable-region--
</html>
```

```css
body {
  background-color: burlywood;
}

h1, h2, p {
  text-align: center;
}
```
