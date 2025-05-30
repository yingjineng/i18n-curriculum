---
id: 616d47bc9eedc4bc7f621bec
title: ステップ 5
challengeType: 0
dashedName: step-5
---

# --description--

次に、その `div` 要素内に別の `div` 要素を追加して、`marker` のクラスを設定してください。

# --hints--

新しい `div` 要素に開始タグが必要です。

```js
assert.exists([...code.matchAll(/<div.*?>/gi)][1]);
```

新しい `div` 要素に終了タグが必要です。

```js
assert.exists([...code.matchAll(/<\/div\s*>/gi)][1]);
```

クラスが `container` の `div` の中に、新しい `div` 要素をネストする必要があります。

```js
assert.strictEqual(document.querySelector('.container')?.children[0]?.localName, 'div');
```

新しい `div` 要素のクラスを `marker` に設定する必要があります。

```js
const containerChildren = [...document.querySelector('.container')?.children];
assert.isNotEmpty(containerChildren)
containerChildren.forEach(child => assert.isTrue(child.classList?.contains('marker')));
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Colored Markers</title>
    <link rel="stylesheet" href="styles.css">
  </head>
--fcc-editable-region--
  <body>
    <h1>CSS Color Markers</h1>
    <div class="container">
    </div>
  </body>
--fcc-editable-region--
</html>
```

```css
h1 {
  text-align: center;
}
```
