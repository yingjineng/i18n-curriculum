---
id: bad87fee1348bd9aedf08816
title: 用 a 實現網頁間的跳轉
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/c8EkncB'
forumTopicId: 18226
dashedName: link-to-external-pages-with-anchor-elements
---

# --description--

You can use `a` (*anchor*) elements to link to content outside of your web page.

`a` 需要一個 `href` 屬性指向跳轉的目的地。 同時，它還應有內容。 這是一個示例：

```html
<a href="https://www.freecodecamp.org">this links to freecodecamp.org</a>
```

瀏覽器將顯示文本 `this links to freecodecamp.org`，這是一個可點擊的鏈接。 你可以通過這個鏈接訪問 `https://www.freecodecamp.org`。

# --instructions--

創建一個內容文本爲 “cat photos” 的 `a` 元素，鏈接指向 `https://www.freecatphotoapp.com`。

# --hints--

`a` 元素應有錨文本 `cat photos`。

```js
assert.match(document.querySelector('a').textContent,/cat photos/gi);
```

`a` 元素應鏈接到 `https://www.freecatphotoapp.com`。

```js
assert.match(document.querySelector('a').getAttribute('href'),/^https?:\/\/(www\.)?freecatphotoapp\.com\/?$/i);
```

確保 `a` 元素有結束標籤。

```js
assert.match(code,/<\/a>/g);
assert.strictEqual(code.match(/<\/a>/g).length,code.match(/<a/g).length);
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>



  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back.">

  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>

  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back.">

  <a href="https://www.freecatphotoapp.com">cat photos</a>
  <p>Kitty ipsum dolor sit amet, shed everywhere shed everywhere stretching attack your ankles chase the red dot, hairball run catnip eat the grass sniff.</p>
  <p>Purr jump eat the grass rip the couch scratched sunbathe, shed everywhere rip the couch sleep in the sink fluffy fur catnip scratched.</p>
</main>
```
