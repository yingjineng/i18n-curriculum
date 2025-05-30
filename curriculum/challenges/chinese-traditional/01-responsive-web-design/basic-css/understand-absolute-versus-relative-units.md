---
id: bad82fee1322bd9aedf08721
title: 理解絕對單位與相對單位
challengeType: 0
videoUrl: 'https://scrimba.com/c/cN66JSL'
forumTopicId: 301089
dashedName: understand-absolute-versus-relative-units
---

# --description--

The last several challenges all set an element's margin or padding with pixels (`px`). Pixels are a type of length unit, which is what tells the browser how to size or space an item. In addition to `px`, CSS has a number of different length unit options that you can use.

單位長度的類型可以分成 2 種：相對和絕對。 絕對單位與長度的物理單位相關。 例如，`in` 和 `mm` 分別代表着英寸和毫米。 絕對長度單位會接近屏幕上的實際測量值，不過不同屏幕的分辨率會存在差異，這就可能會造成誤差。

相對單位長度，比如 `em` 和 `rem`，它們的實際值會依賴其他長度的值而決定。 比如 `em` 的大小基於元素字體的字體大小。 如果使用它來設置 `font-size` 值，它的值會跟隨父元素的 `font-size` 值來改變。

**Note:** 有些單位長度選項是相對視窗大小來改變值的， 這種設定符合響應式網頁設計的原則。

# --instructions--

給 `red-box` class 添加 `padding` 屬性，並設置其屬性值爲 `1.5em`。

# --hints--

class 爲 `red-box` 的元素應含有 `padding` 屬性。

```js
const redBox =document.querySelector('.red-box'); 
const style = window.getComputedStyle(redBox); 

assert.notEqual(style['padding-top'], '0px');
assert.notEqual(style['padding-right'], '0px');
assert.notEqual(style['padding-bottom'], '0px');
assert.notEqual(style['padding-left'], '0px');
```

class 爲 `red-box` 的元素的 `padding` 屬性值應爲 1.5em。

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
