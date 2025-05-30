---
id: 587d781c367417b2b2512ac3
title: 複数の見出し要素の font-weight を設定する
challengeType: 0
videoUrl: 'https://scrimba.com/c/crVWRHq'
forumTopicId: 301069
dashedName: set-the-font-weight-for-multiple-heading-elements
---

# --description--

ひとつ前のチャレンジでは各見出しタグの `font-size` を設定しました。次は `font-weight` を調整してみましょう。

`font-weight` プロパティは、文字の太さまたは細さを設定します。

# --instructions--

<ul><li><code>h1</code> タグの <code>font-weight</code> を 800 に設定してください。</li><li><code>h2</code> タグの <code>font-weight</code> を 600 に設定してください。</li><li><code>h3</code> タグの <code>font-weight</code> を 500 に設定してください。</li><li><code>h4</code> タグの <code>font-weight</code> を 400 に設定してください。</li><li><code>h5</code> タグの <code>font-weight</code> を 300 に設定してください。</li><li><code>h6</code> タグの <code>font-weight</code> を 200 に設定してください。</li></ul>

# --hints--

`h1` タグの `font-weight` プロパティは 800 に設定される必要があります。

```js
const h1Element =document.querySelector('h1')
const h1Style = window.getComputedStyle(h1Element);
assert.equal(h1Style?.fontWeight, '800');
```

`h2` タグの `font-weight` プロパティは 600 に設定される必要があります。

```js
const h2Element =document.querySelector('h2')
const h2Style = window.getComputedStyle(h2Element);
assert.equal(h2Style?.fontWeight, '600');
```

`h3` タグの `font-weight` プロパティは 500 に設定される必要があります。

```js
const h3Element =document.querySelector('h3')
const h3Style = window.getComputedStyle(h3Element);
assert.equal(h3Style?.fontWeight, '500');
```

`h4` タグの `font-weight` プロパティは 400 に設定される必要があります。

```js
const h4Element =document.querySelector('h4')
const h4Style = window.getComputedStyle(h4Element);
assert.equal(h4Style?.fontWeight, '400');
```

`h5` タグの `font-weight` プロパティは 300 に設定される必要があります。

```js
const h5Element =document.querySelector('h5')
const h5Style = window.getComputedStyle(h5Element);
assert.equal(h5Style?.fontWeight, '300');
```

`h6` タグの `font-weight` プロパティは 200 に設定される必要があります。

```js
const h6Element =document.querySelector('h6')
const h6Style = window.getComputedStyle(h6Element);
assert.equal(h6Style?.fontWeight, '200');
```

# --seed--

## --seed-contents--

```html
<style>
  h1 {
    font-size: 68px;

  }
  h2 {
    font-size: 52px;

  }
  h3 {
    font-size: 40px;

  }
  h4 {
    font-size: 32px;

  }
  h5 {
    font-size: 21px;

  }
  h6 {
    font-size: 14px;

  }
</style>
<h1>This is h1 text</h1>
<h2>This is h2 text</h2>
<h3>This is h3 text</h3>
<h4>This is h4 text</h4>
<h5>This is h5 text</h5>
<h6>This is h6 text</h6>
```

# --solutions--

```html
<style>
  h1 {
    font-size: 68px;
    font-weight: 800;
  }
  h2 {
    font-size: 52px;
    font-weight: 600;
  }
  h3 {
    font-size: 40px;
    font-weight: 500;
  }
  h4 {
    font-size: 32px;
    font-weight: 400;
  }
  h5 {
    font-size: 21px;
    font-weight: 300;
  }
  h6 {
    font-size: 14px;
    font-weight: 200;
  }
</style>
<h1>This is h1 text</h1>
<h2>This is h2 text</h2>
<h3>This is h3 text</h3>
<h4>This is h4 text</h4>
<h5>This is h5 text</h5>
<h6>This is h6 text</h6>
```
