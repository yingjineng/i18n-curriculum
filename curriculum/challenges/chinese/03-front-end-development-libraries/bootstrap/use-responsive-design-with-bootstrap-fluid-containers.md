---
id: bad87fee1348bd9acde08712
title: 使用 Bootstrap Fluid 容器实现响应式设计
challengeType: 0
forumTopicId: 18362
dashedName: use-responsive-design-with-bootstrap-fluid-containers
---

# --description--

In the HTML5 and CSS section of freeCodeCamp we built a Cat Photo App. Now let's go back to it. This time, we'll style it using the popular Bootstrap responsive CSS framework.

Bootstrap 会根据屏幕大小来动态调整 HTML 元素的大小————因此称为 <dfn>Responsive Design</dfn>（响应式设计）。

通过响应式设计，我们将无需额外设计一个手机版的网页， 因为它在任何尺寸的屏幕上看起来都很棒。

任何 Web 应用，都可以通过添加如下代码到 HTML 顶部来引入 Bootstrap 。

```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous"/>
```

不过在这里，已经预先为此页面添加了上述代码。 注意使用 `>` 或者 `/>` 两种方式闭合 `link` 标签都是可行的。

首先，我们应该将所有 HTML（ `link` 标签和 `style` 元素除外）嵌套在带有 `container-fluid` class 的 `div` 元素里面。

# --hints--

`div` 元素应该有 `container-fluid` class。

```js
assert.isTrue(document.querySelector('div')?.classList?.contains('container-fluid'));
```

`div` 元素应该有结束标签。

```js
assert.match(code,/<\/div>/g);
assert.match(code,/<div/g);
assert.equal(code.match(/<\/div>/g).length ,code.match(/<div/g).length);
```

`style` 结束标签后面的所有 HTML 元素都应该被嵌套在 `.container-fluid` 里面。

```js
const fluidContainer = document.querySelector('.container-fluid');
const possibleStyleElements = fluidContainer?.querySelectorAll(`:scope ${'style'}`);
const possibleLinkElements = fluidContainer?.querySelectorAll(`:scope ${'link'}`);

assert.lengthOf(fluidContainer?.children,8);
assert.isEmpty(possibleStyleElements);
assert.isEmpty(possibleLinkElements);
```

# --seed--

## --seed-contents--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }

  .smaller-image {
    width: 100px;
  }
</style>

<h2 class="red-text">CatPhotoApp</h2>

<p>Click here for <a href="#">cat photos</a>.</p>

<a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

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
<form action="https://freecatphotoapp.com/submit-cat-photo">
  <label><input type="radio" name="indoor-outdoor"> Indoor</label>
  <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
  <label><input type="checkbox" name="personality"> Loving</label>
  <label><input type="checkbox" name="personality"> Lazy</label>
  <label><input type="checkbox" name="personality"> Crazy</label>
  <input type="text" placeholder="cat photo URL" required>
  <button type="submit">Submit</button>
</form>
```

# --solutions--

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
<style>
  .red-text {
    color: red;
  }

  h2 {
    font-family: Lobster, Monospace;
  }

  p {
    font-size: 16px;
    font-family: Monospace;
  }

  .thick-green-border {
    border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 50%;
  }

  .smaller-image {
    width: 100px;
  }
</style>
<div class="container-fluid">
  <h2 class="red-text">CatPhotoApp</h2>

<p>Click here for <a href="#">cat photos</a>.</p>

<a href="#"><img class="smaller-image thick-green-border" src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>

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
<form action="https://freecatphotoapp.com/submit-cat-photo">
  <label><input type="radio" name="indoor-outdoor"> Indoor</label>
  <label><input type="radio" name="indoor-outdoor"> Outdoor</label>
  <label><input type="checkbox" name="personality"> Loving</label>
  <label><input type="checkbox" name="personality"> Lazy</label>
  <label><input type="checkbox" name="personality"> Crazy</label>
  <input type="text" placeholder="cat photo URL" required>
  <button type="submit">Submit</button>
</form>
</div>
```
