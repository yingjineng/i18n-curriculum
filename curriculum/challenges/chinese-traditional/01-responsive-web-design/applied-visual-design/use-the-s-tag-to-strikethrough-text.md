---
id: 587d781b367417b2b2512aba
title: 使用 s 標籤給文本添加刪除線
challengeType: 0
forumTopicId: 301079
dashedName: use-the-s-tag-to-strikethrough-text
---

# --description--

To strikethrough text, which is when a horizontal line cuts across the characters, you can use the `s` tag. It shows that a section of text is no longer valid. With the `s` tag, the browser applies the CSS of `text-decoration: line-through;` to the element.

# --instructions--

在 `h4` 標籤裏的 `Google` 文本外添加 `s` 標籤，然後在 s 標籤後面添加單詞 `Alphabet`，單詞不要有刪除線格式。

# --hints--

應添加一個 `s` 標籤。

```js
assert.lengthOf(document.querySelectorAll('s'),1);
```

`s` 標籤應該在 `h4` 標籤內的 `Google` 文字外面， 它不應包含單詞 `Alphabet`。

```js
assert.match(document.querySelector('h4 > s')?.textContent, /Google/gi);
assert.notMatch(document.querySelector('h4 > s')?.textContent, /Alphabet/gi);
```

`h4` 標籤內應有單詞 `Alphabet`，單詞不應有刪除線樣式。

```js
assert.match(document.querySelector('h4')?.innerHTML, /Alphabet/gi);
```

# --seed--

## --seed-contents--

```html
<style>
  h4 {
    text-align: center;
    height: 25px;
  }
  p {
    text-align: justify;
  }
  .links {
    text-align: left;
    color: black;
  }
  .fullCard {
    width: 245px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin: 10px 5px;
    padding: 4px;
  }
  .cardContent {
    padding: 10px;
  }
  .cardText {
    margin-bottom: 30px;
  }
</style>
<div class="fullCard">
  <div class="cardContent">
    <div class="cardText">
      <h4>Google</h4>
      <p><em>Google was founded by Larry Page and Sergey Brin while they were <u>Ph.D. students</u> at <strong>Stanford University</strong>.</em></p>
    </div>
    <div class="cardLinks">
      <a href="https://en.wikipedia.org/wiki/Larry_Page" target="_blank" class="links">Larry Page</a><br><br>
      <a href="https://en.wikipedia.org/wiki/Sergey_Brin" target="_blank" class="links">Sergey Brin</a>
    </div>
  </div>
</div>
```

# --solutions--

```html
<style>
  h4 {
    text-align: center;
    height: 25px;
  }
  p {
    text-align: justify;
  }
  .links {
    text-align: left;
    color: black;
  }
  .fullCard {
    width: 245px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin: 10px 5px;
    padding: 4px;
  }
  .cardContent {
    padding: 10px;
  }
  .cardText {
    margin-bottom: 30px;
  }
</style>
<div class="fullCard">
  <div class="cardContent">
    <div class="cardText">
      <h4><s>Google</s> Alphabet</h4>
      <p><em>Google was founded by Larry Page and Sergey Brin while they were <u>Ph.D. students</u> at <strong>Stanford University</strong>.</em></p>
    </div>
    <div class="cardLinks">
      <a href="https://en.wikipedia.org/wiki/Larry_Page" target="_blank" class="links">Larry Page</a><br><br>
      <a href="https://en.wikipedia.org/wiki/Sergey_Brin" target="_blank" class="links">Sergey Brin</a>
    </div>
  </div>
</div>
```
