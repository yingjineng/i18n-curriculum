---
id: 587d7fad367417b2b2512be1
title: onclick プロパティを使用してクリックイベントを JavaScript で処理する
challengeType: 6
forumTopicId: 301503
dashedName: handle-click-events-with-javascript-using-the-onclick-property
---

# --description--

ページの読み込みが完了するまで、コードが実行されないようにしましょう。 その目的のために、`DOMContentLoaded` という名前のドキュメントに JavaScript イベントをアタッチすることができます。 これを行うコードを次に示します。

```js
document.addEventListener('DOMContentLoaded', function () {});
```

`DOMContentLoaded` 関数の中に入るイベントハンドラを実装できます。 `#getMessage` の要素をユーザーがクリックしたときにトリガーされる `onclick` イベントハンドラを実装するには、次のコードを追加します。

```js
document.getElementById('getMessage').onclick = function () {};
```

# --instructions--

`getMessage` という id を持つ要素に対する `DOMContentLoaded` 関数の中に、クリックイベントハンドラを追加してください。

# --hints--

`document.getElementById` メソッドを使用して、id が `getMessage` の要素を選択する必要があります。

```js
assert.match(code, /document\s*\.getElementById\(\s*('|")getMessage\1\s*\)/g);
```

`onclick` イベントハンドラを追加する必要があります。

```js
assert.isFunction(document.getElementById('getMessage').onclick);
```

# --seed--

## --seed-contents--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    // Add your code below this line
    // Add your code above this line
  });
</script>

<style>
  body {
    text-align: center;
    font-family: 'Helvetica', sans-serif;
  }
  h1 {
    font-size: 2em;
    font-weight: bold;
  }
  .box {
    border-radius: 5px;
    background-color: #eee;
    padding: 20px 5px;
  }
  button {
    color: white;
    background-color: #4791d0;
    border-radius: 5px;
    border: 1px solid #4791d0;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    background-color: #0f5897;
    border: 1px solid #0f5897;
  }
</style>
<h1>Cat Photo Finder</h1>
<p class="message box">The message will go here</p>
<p>
  <button id="getMessage">Get Message</button>
</p>
```

# --solutions--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    // Add your code below this line
    document.getElementById('getMessage').onclick = function () {};
    // Add your code above this line
  });
</script>

<style>
  body {
    text-align: center;
    font-family: 'Helvetica', sans-serif;
  }
  h1 {
    font-size: 2em;
    font-weight: bold;
  }
  .box {
    border-radius: 5px;
    background-color: #eee;
    padding: 20px 5px;
  }
  button {
    color: white;
    background-color: #4791d0;
    border-radius: 5px;
    border: 1px solid #4791d0;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    background-color: #0f5897;
    border: 1px solid #0f5897;
  }
</style>
<h1>Cat Photo Finder</h1>
<p class="message box">The message will go here</p>
<p>
  <button id="getMessage">Get Message</button>
</p>
```
