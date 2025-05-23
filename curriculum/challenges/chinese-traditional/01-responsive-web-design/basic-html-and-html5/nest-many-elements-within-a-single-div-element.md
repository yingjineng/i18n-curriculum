---
id: bad87fee1348bd9aede08835
title: 元素嵌套
challengeType: 0
videoUrl: 'https://scrimba.com/p/pVMPUv/cNW4kC3'
forumTopicId: 18246
dashedName: nest-many-elements-within-a-single-div-element
---

# --description--

The `div` element, also known as a division element, is a general purpose container for other elements.

它也是 HTML 中出現頻率最高的元素。

和其他普通元素一樣，你可以用 `<div>` 來標記一個 `div` 元素的開始，用 `</div>` 來標記一個 `div` 元素的結束。

# --instructions--

將你的列表“貓喜歡的三件事”和“貓最討厭的三件事”放入同一個 `div` 元素中。

提示：你可以在第一個 `<p>` 之前插入 `div` 開始標記，在 `</ol>` 之後插入 `div` 結束標籤。 這樣，所有的列表都會位於 `div` 之內。

# --hints--

所有的 `p` 元素都應嵌套在 `div` 元素中。

```js
const div = document.querySelector('div');
const children = div.querySelectorAll('p');
assert.isAbove(children.length,1);
```

所有的 `ul` 元素都應嵌套在 `div` 元素中。

```js
const div = document.querySelector('div');
const children = div.querySelectorAll('ul');
assert.notEmpty(children);
```

所有的 `ol` 元素都應嵌套在 `div` 元素中。

```js
const div = document.querySelector('div');
const children = div.querySelectorAll('ol');
assert.notEmpty(children);
```

確保該 `div` 元素有閉合標籤.

```js
assert.match(code,/<\/div>/g);
assert.strictEqual(code.match(/<\/div>/g).length,code.match(/<div>/g).length);
```

# --seed--

## --seed-contents--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

  <p>Things cats love:</p>
  <ul>
    <li>catnip</li>
    <li>laser pointers</li>
    <li>lasagna</li>
  </ul>
  <p>Top 3 things cats hate:</p>
  <ol>
    <li>flea treatment</li>
    <li>thunder</li>
    <li>other cats</li>
  </ol>

  <form action="https://www.freecatphotoapp.com/submit-cat-photo">
    <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor" value="indoor" checked> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor" value="outdoor"> Outdoor</label><br>
    <label for="loving"><input id="loving" type="checkbox" name="personality" value="loving" checked> Loving</label>
    <label for="lazy"><input id="lazy" type="checkbox" name="personality" value="lazy"> Lazy</label>
    <label for="energetic"><input id="energetic" type="checkbox" name="personality" value="energetic"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```

# --solutions--

```html
<h2>CatPhotoApp</h2>
<main>
  <p>Click here to view more <a href="#">cat photos</a>.</p>

  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
  <div>
    <p>Things cats love:</p>
    <ul>
      <li>catnip</li>
      <li>laser pointers</li>
      <li>lasagna</li>
    </ul>
    <p>Top 3 things cats hate:</p>
    <ol>
      <li>flea treatment</li>
      <li>thunder</li>
      <li>other cats</li>
    </ol>
  </div>
  <form action="https://www.freecatphotoapp.com/submit-cat-photo">
    <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor" value="indoor" checked> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor" value="outdoor"> Outdoor</label><br>
    <label for="loving"><input id="loving" type="checkbox" name="personality" value="loving" checked> Loving</label>
    <label for="lazy"><input id="lazy" type="checkbox" name="personality" value="lazy"> Lazy</label>
    <label for="energetic"><input id="energetic" type="checkbox" name="personality" value="energetic"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
</main>
```
