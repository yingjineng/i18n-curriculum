---
id: 587d78a3367417b2b2512ad1
title: 瞭解互補色
challengeType: 0
videoUrl: 'https://scrimba.com/c/c2MD3Tr'
forumTopicId: 301056
dashedName: learn-about-complementary-colors
---

# --description--

Color theory and its impact on design is a deep topic and only the basics are covered in the following challenges. On a website, color can draw attention to content, evoke emotions, or create visual harmony. Using different combinations of colors can really change the look of a website, and a lot of thought can go into picking a color palette that works with your content.

色環是我們認識顏色關係的好工具。它是一個近色相鄰、異色相離的圓環。 當兩個顏色恰好在色環的兩端時，這兩個顏色就互爲補色。 兩個互爲補色的顏色會在混合後變成灰色。 然而，補色搭配能形成強烈的視覺對比效果。

下面是一些以 hex 形式表示的補色例子：

<blockquote>紅色（#FF0000）和藍綠色 (#00FFFF)<br>綠色（#00FF00）和品紅色（#FF00FF）<br>藍色（#0000FF）和黃色（#FFFF00）</blockquote>

這與我們許多人在學校學的過時的 RYB 色彩模式不同，RYB 有不同的原色和補色。 現代色彩理論使用 RGB 模型（如在計算機屏幕上）和 CMY（K）模型（如在印刷中）。

現在，很多在線選色工具也爲我們提供了尋找補色的功能。

**注意：** 對於顏色相關的挑戰：顏色搭配是提起用戶興趣或吸引用戶注意的重要方式之一。 但我們不應讓顏色作爲傳達重要信息的唯一方式，因爲視覺障礙用戶可能無法像其他人一樣看出其中的含義。 我們將會在應用無障礙章節進行詳細介紹。

# --instructions--

把 class 爲 `blue` 和 `yellow` 的元素的 `background-color` 屬性改成相應的顏色。 注意觀察這兩個顏色的搭配效果，以及對比白色背景的視覺效果。

# --hints--

class 爲 `blue` 的 `div` 元素應有一個 `background-color`，顏色爲藍色。

```js
const blueElement = document.querySelector('.blue');
const blueStyle = window.getComputedStyle(blueElement); 
assert.equal(blueStyle?.backgroundColor, 'rgb(0, 0, 255)');
```

class 爲 `yellow` 的 `div` 元素的 `background-color` 屬性，顏色爲黃色。

```js
const yellowElement = document.querySelector('.yellow');
const yellowStyle = window.getComputedStyle(yellowElement);
assert.equal(yellowStyle?.backgroundColor, 'rgb(255, 255, 0)');
```

# --seed--

## --seed-contents--

```html
<style>
  body {
    background-color: #FFFFFF;
  }
  .blue {
    background-color: #000000;
  }
  .yellow {
    background-color: #000000;
  }
  div {
    display: inline-block;
    height: 100px;
    width: 100px;
  }
</style>
<div class="blue"></div>
<div class="yellow"></div>
```

# --solutions--

```html
<style>
  body {
    background-color: #FFFFFF;
  }
  .blue {
    background-color: blue;
  }
  .yellow {
    background-color: yellow;
  }
  div {
    display: inline-block;
    height: 100px;
    width: 100px;
  }
</style>
<div class="blue"></div>
<div class="yellow"></div>
```
