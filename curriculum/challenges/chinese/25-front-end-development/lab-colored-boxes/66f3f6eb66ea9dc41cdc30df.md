---
id: 66f3f6eb66ea9dc41cdc30df
title: 设计一组彩色盒子
challengeType: 25
dashedName: set-of-colored-boxes
demoType: onClick
---

# --description--

在本实验中，你将通过设计盒子来练习使用 CSS 颜色。

**目标：** 完成以下用户故事并通过所有测试以完成本实验。

**用户故事：**

1. 你需要将 `body` 的背景色设置为 `#f4f4f4`。
2. 你需要有一个带有 `color-grid` 类的 `div`，用于容纳所有颜色元素。
3. 在 `.color-grid` 元素内应有五个 `div` 元素。
4. 这五个 `div` 元素都应同时拥有 `color-box` 和 `color#` 类，其中 `#` 表示该 `div` 的顺序编号。例如：第一个 `div` 为 `color1`，第二个为 `color2`，以此类推。
5. `.color-box` 类应设置固定的 `width` 和 `height`，以确保你的 `div` 元素在页面上可见。
6. `.color1` 元素应使用十六进制颜色值设置 `background-color`。
7. `.color2` 元素应使用 RGB 颜色值设置 `background-color`。
8. `.color3` 元素应使用预定义（单词）颜色值设置 `background-color`。
9. `.color4` 元素应使用 HSL 颜色值设置 `background-color`。
10. `.color5` 元素应设置 `background-color`。

**注意：** 请确保在 HTML 中正确链接样式表并应用你的 CSS。

# --hints--

`body` 的背景色应为 `#f4f4f4`。

```js
const body = document.body;
const bodyBgColor = getComputedStyle(body).backgroundColor;
assert.strictEqual(bodyBgColor, 'rgb(244, 244, 244)');
```

你应有一个带有 `color-grid` 类的 `div` 元素。

```js
const colorGrid = document.querySelector('div.color-grid');
assert.exists(colorGrid);
```

在 `.color-grid` 元素内应有五个 `div` 元素。

```js
const colorGridChildren = document.querySelectorAll('div.color-grid > div');
assert.strictEqual(colorGridChildren.length, 5);
```

这五个 `div` 元素都应同时拥有 `color-box` 和 `color#` 类——将 `#` 替换为该 `div` 的顺序编号。

```js
const colorGridChildren = document.querySelectorAll('div.color-grid > div');
assert.strictEqual(colorGridChildren.length, 5);

colorGridChildren.forEach((child, index) => {
    const colorClass = `color${index + 1}`;
    assert.isTrue(child.classList.contains('color-box'));
    assert.isTrue(child.classList.contains(colorClass));
});
```

`.color-box` 元素应设置固定的 `width` 和 `height`。

```js
const colorBox = document.querySelector('.color-box');
assert.exists(colorBox);

const colorBoxStyles = getComputedStyle(colorBox);
const width = colorBoxStyles.width;
const height = colorBoxStyles.height;

assert.notStrictEqual(width, '0px');
assert.notStrictEqual(height, '0px');
```

`.color1` 元素应使用十六进制颜色值设置背景色。

```js
const hexChars = "[0-9a-fA-F]"
const hexRegex = new RegExp(`\\.color1\\s*{[^}]*\\bbackground-color\\s*:\\s*#((${hexChars}{3,4})||(${hexChars}{6})||(${hexChars}{8}))\\s*;[^}]*}`);
assert.match(__helpers.removeCssComments(code), hexRegex);
```

`.color2` 元素应使用 RGB 颜色值设置背景色。

```js
assert.match(__helpers.removeCssComments(code), /\.color2\s*{[^}]*\bbackground-color\s*:\s*rgb\s*\(\s*\d+(?:\.\d+)?\s*(,|\s+)\s*\d+(?:\.\d+)?\s*\1\s*\d+(?:\.\d+)?\s*(\/\s*\d{1,2}(?:\.\d+)?%\s*)?\)\s*;[^}]*}/);
```

`.color3` 元素应使用预定义（单词）颜色值设置背景色。

```js
const colorSet = new Set(["black", "silver", "gray", "white", "maroon", "red", "purple", "fuchsia", "green", "lime", "olive", "yellow", "navy", "blue", "teal", "aqua", "aliceblue", "antiquewhite", "aqua", "aquamarine", "azure", "beige", "bisque", "black", "blanchedalmond", "blue", "blueviolet", "brown", "burlywood", "cadetblue", "chartreuse", "chocolate", "coral", "cornflowerblue", "cornsilk", "crimson", "cyan", "aqua", "darkblue", "darkcyan", "darkgoldenrod", "darkgray", "darkgreen", "darkgrey", "darkkhaki", "darkmagenta", "darkolivegreen", "darkorange", "darkorchid", "darkred", "darksalmon", "darkseagreen", "darkslateblue", "darkslategray", "darkslategrey", "darkturquoise", "darkviolet", "deeppink", "deepskyblue", "dimgray", "dimgrey", "dodgerblue", "firebrick", "floralwhite", "forestgreen", "fuchsia", "gainsboro", "ghostwhite", "gold", "goldenrod", "gray", "green", "greenyellow", "grey", "gray", "honeydew", "hotpink", "indianred", "indigo", "ivory", "khaki", "lavender", "lavenderblush", "lawngreen", "lemonchiffon", "lightblue", "lightcoral", "lightcyan", "lightgoldenrodyellow", "lightgray", "lightgreen", "lightgrey", "lightpink", "lightsalmon", "lightseagreen", "lightskyblue", "lightslategray", "lightslategrey", "lightsteelblue", "lightyellow", "lime", "limegreen", "linen", "magenta", "fuchsia", "maroon", "mediumaquamarine", "mediumblue", "mediumorchid", "mediumpurple", "mediumseagreen", "mediumslateblue", "mediumspringgreen", "mediumturquoise", "mediumvioletred", "midnightblue", "mintcream", "mistyrose", "moccasin", "navajowhite", "navy", "oldlace", "olive", "olivedrab", "orange", "orangered", "orchid", "palegoldenrod", "palegreen", "paleturquoise", "palevioletred", "papayawhip", "peachpuff", "peru", "pink", "plum", "powderblue", "purple", "rebeccapurple", "red", "rosybrown", "royalblue", "saddlebrown", "salmon", "sandybrown", "seagreen", "seashell", "sienna", "silver", "skyblue", "slateblue", "slategray", "slategrey", "snow", "springgreen", "steelblue", "tan", "teal", "thistle", "tomato", "transparent", "turquoise", "violet", "wheat", "white", "whitesmoke", "yellow", "yellowgreen"]);
const matchedColor = __helpers.removeCssComments(code).match(/\.color3\s*{[^}]*\bbackground-color\s*:\s*(?<color>[a-zA-Z]+)\s*;[^}]*}/);
assert.isTrue(colorSet.has(matchedColor.groups.color.toLowerCase()));
```

`.color4` 元素应使用 HSL 颜色值设置背景色。

```js
const absHSLVals = '\\s*(none|\\d+(?:\\.\\d+)?(?:deg)?)\\s*\\d+(?:\\.\\d+)?%?\\s*\\d+(?:\\.\\d+)?%?\\s*(\\/\\s*\\d{1,2}(?:\\.\\d+)?%\\s*)?';
const legacyHSLVals = '\\s*\\d+(?:\\.\\d+)?(?:deg)?\\s*,\\s*\\d+(?:\\.\\d+)?%\\s*,\\s*\\d+(?:\\.\\d+)?%\\s*(?:,\\s*\\d+(?:\\.\\d+)?\\s*)?';
const hslRegex = new RegExp(`\\.color4\\s*{[^}]*\\bbackground-color\\s*:\\s*hsl\\s*\\((${absHSLVals}|${legacyHSLVals})\\)\\s*;[^}]*}`);
assert.match(__helpers.removeCssComments(code), hslRegex);
```

`.color5` 元素应设置背景色。

```js
assert.isNotEmpty(new __helpers.CSSHelp(document).getStyle('.color5')?.getPropVal('background-color', true));
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="zh">
<head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>彩色盒子</title>
</head>
<body>

</body>
</html>
```

```css

```

# --solutions--

```html
<!DOCTYPE html>
<html lang="zh">
<head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>彩色盒子</title>
        <link rel="stylesheet" href="styles.css">
</head>
<body>
        <h1>彩色盒子</h1>
        <div class="color-grid"> 
                <div class="color-box color1"></div>
                <div class="color-box color2"></div>
                <div class="color-box color3"></div>
                <div class="color-box color4"></div>
                <div class="color-box color5"></div>
        </div>
</body>
</html>
```

```css
body {
        font-family: Arial, sans-serif;
        display: flex;
        flex-direction: column;
        align-items: center;
        margin: 0;
        padding: 20px;
        background-color: #f4f4f4;
}

h1 {
        margin-bottom: 20px;
}

.color-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
        gap: 10px;
        width: 100%;
        max-width: 800px;
}

.color-box {
        display: flex;
        justify-content: center;
        align-items: center;
        font-weight: bold;
        border-radius: 8px;
        text-align: center;
        width: 100px;
        height: 100px;
}

.color1 {
        background-color: #33FF57;
}

.color2 {
        background-color: rgb(128,0,128);
}

.color3 {
        background-color: orange;
}

.color4 {
        background-color: hsl(59, 61%, 26%);
}

.color5 {
        background-color: red;
}
```

