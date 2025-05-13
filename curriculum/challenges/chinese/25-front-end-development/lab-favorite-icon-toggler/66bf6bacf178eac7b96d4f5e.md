---
id: 66bf6bacf178eac7b96d4f5e
title: 构建一个收藏图标切换器
challengeType: 25
dashedName: build-a-favorite-icon-toggler
demoType: onClick
---

# --description--

在本实验中，你将使用 JavaScript 的点击事件来切换收藏图标的外观。当点击心形图标时，心形的外观会在空心和实心之间切换。

完成以下用户故事并通过所有测试即可完成本实验。

**用户需求：**

1. 你应该有一个包含三个项目的无序列表。
2. 该无序列表应具有 `item-list` 类。
3. 三个列表项应包含项目名称，后跟一个带有 `favorite-icon` 类的 `button` 元素。
4. `button` 元素初始内容应为 `&#9825;`，表示空心心形。
5. 当包含心形的 `button` 元素被点击时，如果未包含 `filled` 类，则添加该类；如果已包含，则移除该类。
6. 你应有一个选择器 `.filled`，为其设置一些 CSS 属性。
7. 当包含心形的 `button` 元素被点击时，心形符号应根据当前状态在 `&#9825;`（空心）和 `&#10084;`（实心）之间切换。

**注意：** 请确保在 HTML 中引入你的 JavaScript 文件。（例如 `<script src="script.js"></script>`）

# --hints--

你应该有一个无序列表。

```js
assert.exists(document.querySelector('ul'));
```

你的无序列表应有 3 个项目。

```js
assert.lengthOf(document.querySelectorAll('ul li'), 3);
```

你的无序列表应具有 `item-list` 类。

```js
assert.exists(document.querySelector('ul.item-list'));
```

你的每个列表项应包含项目名称。

```js
assert.exists(document.querySelector('ul li').textContent);
```

你的每个列表项应包含一个带有 `favorite-icon` 类的 `button` 元素。

```js
assert.exists(document.querySelector('ul li button.favorite-icon'));
```

初始时，`button` 元素内容应为 `&#9825;`，表示空心心形。

```js
const inputs = document.querySelectorAll('ul li button.favorite-icon');
assert.isNotEmpty(inputs);

for (let input of inputs) {
  assert.strictEqual(input.innerHTML.charCodeAt(0), 9825);
}
```

你应有一个 `.filled` 选择器并设置一些 CSS 属性。

```js
const filled = new __helpers.CSSHelp(document).getStyle('.filled');
assert.exists(filled); 
assert.isNotEmpty([...filled]); 
```

当点击包含 `filled` 类的 `button` 元素时，应移除 `filled` 类，并将 `button` 元素的 innerHTML 改为 `&#9825;`。

```js
const buttonElements = document.querySelectorAll('.favorite-icon');
assert.isNotEmpty(buttonElements);

buttonElements.forEach(button => button.classList.add('filled'));

buttonElements.forEach(button => {
  button.dispatchEvent(new Event('click', { bubbles: true }));
  assert.isFalse(button.classList.contains('filled'));
  assert.equal(button.innerHTML.charCodeAt(0), 9825);
});
```

当点击未包含 `filled` 类的 `button` 元素时，应添加 `filled` 类，并将 `button` 元素的 innerHTML 改为 `&#10084;`。

```js
const buttonElements = document.querySelectorAll('.favorite-icon');
assert.isNotEmpty(buttonElements);

buttonElements.forEach(button => button.classList.remove('filled'));

buttonElements.forEach(button => {
  button.dispatchEvent(new Event('click', { bubbles: true }));
  assert.isTrue(button.classList.contains('filled'));
  assert.equal(button.innerHTML.charCodeAt(0), 10084);
});
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Favorite Icon Toggler</title>
    <link rel="stylesheet" href="styles.css" />
  </head>

  <body>

  </body>
</html>
```

```css

```

```js

```

# --solutions--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Favorite Icon Toggle</title>
    <link rel="stylesheet" href="styles.css" />
  </head>

  <body>
    <h1>美术用品</h1>
    <ul class="item-list">
      <li>
        120 克纸
        <button class="favorite-icon" id="favoriteIcon1">&#9825;</button>
      </li>
      <li>
        水彩套装
        <button class="favorite-icon" id="favoriteIcon2">&#9825;</button>
      </li>
      <li>
        6B 铅笔
        <button class="favorite-icon" id="favoriteIcon3">&#9825;</button>
      </li>
    </ul>

    <script src="script.js"></script>
  </body>
</html>
```

```css
body {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  font-family: Arial, sans-serif;
}

h1 {
  margin-bottom: 20px;
}

.item-list {
  list-style-type: none;
  padding: 0;
}

.item-list li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  border-bottom: 1px solid #ddd;
  width: 200px;
}

.favorite-icon {
  font-size: 1.25rem;
  background-color: transparent;
  border: none;
  cursor: pointer;
}

.filled {
  color: #d22b2b;
}
```

```js
document.addEventListener("DOMContentLoaded", () => {
  const favoriteIcons = document.querySelectorAll(".favorite-icon");

  favoriteIcons.forEach(icon => {
    icon.addEventListener("click", () => {
      if (icon.classList.contains("filled")) {
        icon.classList.remove("filled");
        icon.innerHTML = "&#9825;"; // 空心心形
      } else {
        icon.classList.add("filled");
        icon.innerHTML = "&#10084;"; // 实心心形
      }
    });
  });
});
```

