---
id: bad87fee1348bd9aedf08827
title: 創建一個無序列表
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cDKVPuv'
forumTopicId: 16814
dashedName: create-a-bulleted-unordered-list
---

# --description--

HTML has a special element for creating <dfn>unordered lists</dfn>, or bullet point style lists.

無序列表以 `<ul>` 開始，中間包含一個或多個 `<li>` 元素， 最後以 `</ul>` 結束。

例如：

```html
<ul>
  <li>milk</li>
  <li>cheese</li>
</ul>
```

會創建一個要點列表，包括 `milk` 和 `cheese`。

# --instructions--

請刪除頁面底部的兩個 `p` 元素，然後在底部創建一個無序列表，其中包含你認爲貓咪最喜歡的三件東西。

# --hints--

應存在一個 `ul` 無序列表。

```js
assert.isNotEmpty(document.querySelectorAll('ul'));
```

應在 `ul` 無序列表中添加三個 `li` 條目。

```js
assert.lengthOf(document.querySelectorAll('ul li'),3);
```

確保 `ul` 無序列表有結束標籤。

```js
assert.match(code,/<\/ul>/gi);
assert.match(code,/<ul/gi);
assert.strictEqual(code.match(/<\/ul>/gi).length,code.match(/<ul/gi).length);
```

確保每個 `li` 條目都有結束標籤。

```js
assert.match(code,/<\/li>/gi);
assert.match(code,/<li[\s>]/gi);
assert.strictEqual(code.match(/<\/li>/gi).length,code.match(/<li[\s>]/gi).length);
```

每個 `li` 元素不應只包含空字符串或只包含空格。

```js
assert.isEmpty([...document.querySelectorAll('ul li')].filter((item) => item.textContent.trim() === ""));
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <ul>
    <li>milk</li>
    <li>mice</li>
    <li>catnip</li>
  </ul>
</main>
```
