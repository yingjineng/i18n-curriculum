---
id: 5dfa30b9eacea3f48c6300ad
title: ステップ 17
challengeType: 0
dashedName: step-17
---

# --description--

以前のステップでは、アンカー要素を使用してテキストをリンクに変換しました。 他の種類のコンテンツも、アンカータグで囲むことでリンクにすることができます。

下記は画像をリンクに変換する例です:

```html
<a href="example-link">
  <img src="image-link.jpg" alt="A photo of a cat.">
</a>
```

画像を適切な要素のタグで囲んで、リンクに変換してください。 アンカーの `href` 属性値には `https://freecatphotoapp.com` を使用してください。

# --hints--

`src` の値が `https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg` に設定された `img` 要素が必要です。 誤って削除された可能性があります。

```js
assert(
  document.querySelector('img') &&
    document.querySelector('img').getAttribute('src') ===
      'https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg'
);
```

アンカー (`a`) 要素には開始タグが必要です。 開始タグは `<elementName>` のような形式の構文です。

```js
assert(document.querySelectorAll('a').length >= 2);
```

画像の後に、`a` タグの終了タグがありません。

```js
assert.lengthOf(document.querySelectorAll('a'), 3);
```

アンカー (`a`) 要素には終了タグが必要です。 終了タグは `<` の直後に `/` があります。

```js
assert(code.match(/<\/a>/g).length >= 2);
```

アンカー (`a`) の終了タグは 1 つだけ追加してください。 余分なものは削除してください。

```js
assert.lengthOf(code.match(/<\/a>/g), 3);
```

アンカー (`a`) 要素に `href` 属性がありません。 開始タグのタグ名の後にスペースがあることと、すべての属性名の前にスペースがあることを確認してください。

```js
assert(document.querySelector('a').hasAttribute('href'));
```

アンカー (`a`) 要素は `https://freecatphotoapp.com` にリンクされる必要があります。 URL が設定されていないか、誤字脱字があります。

```js
assert(
  document.querySelectorAll('a')[1].getAttribute('href') ===
    'https://freecatphotoapp.com'
);
```

Your anchor (`a`) element does not have an `href` attribute. Check that there is a space after the opening tag's name and/or there are spaces before all attribute names.

```js
assert.isTrue(document.querySelectorAll('a')[2]?.hasAttribute('href'));
```

Your anchor (`a`) element should link to `https://freecatphotoapp.com`. You have either omitted the URL or have a typo.

```js
assert.equal(
  document.querySelectorAll('a')[2]?.getAttribute('href').trim(),
    'https://freecatphotoapp.com'
);
```

`img` 要素はアンカー (`a`) 要素の中にネストされている必要があります。 `img` 要素全体が、アンカー (`a`) 要素の開始タグと終了タグの内側にあるようにしてください。

```js
assert(document.querySelector('img').parentNode.nodeName === 'A');
```

# --seed--

## --seed-contents--

```html
<html>
  <body>
    <main>
      <h1>CatPhotoApp</h1>
      <h2>Cat Photos</h2>
      <p>Everyone loves <a href="https://cdn.freecodecamp.org/curriculum/cat-photo-app/running-cats.jpg">cute cats</a> online!</p>
      <p>See more <a target="_blank" href="https://freecatphotoapp.com">cat photos</a> in our gallery.</p>
--fcc-editable-region--
      <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back.">
--fcc-editable-region--
    </main>
  </body>
</html>
```

