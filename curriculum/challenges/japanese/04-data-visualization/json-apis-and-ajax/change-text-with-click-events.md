---
id: 587d7fad367417b2b2512be2
title: クリックイベントでテキストを変更する
challengeType: 6
forumTopicId: 301500
dashedName: change-text-with-click-events
---

# --description--

クリックイベントが発生したとき、JavaScript を使用して HTML 要素を更新できます。

例えばユーザーが `Get Message` ボタンをクリックすると、`message` クラスを持つその要素のテキストが `Here is the message` に変わるとします。

これを行うには、クリックイベント内に次のコードを追加します。

```js
document.getElementsByClassName('message')[0].textContent =
  'Here is the message';
```

# --instructions--

`message` 要素内のテキストを `Here is the message` に変更するために、`onclick` イベントハンドラ内にコードを追加してください。

# --hints--

`document.getElementsByClassName` メソッドを使用して `message` クラスを持つ要素を選択し、その `textContent` を、与えられた文字列に設定する必要があります。

```js
assert.match(
  code,
  /document\s*\.getElementsByClassName\(\s*?('|")message\1\s*?\)\[0\]\s*\.textContent\s*?=\s*?('|")Here is the message\2/g
);
```

# --seed--

## --seed-contents--

```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    document.getElementById('getMessage').onclick = function () {
      // Add your code below this line
      // Add your code above this line
    };
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
    document.getElementById('getMessage').onclick = function () {
      // Add your code below this line
      document.getElementsByClassName('message')[0].textContent =
        'Here is the message';
      // Add your code above this line
    };
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
<p class="message">The message will go here</p>
<p>
  <button id="getMessage">Get Message</button>
</p>
```
