---
id: 6406adbca6b41d3d7cef85ab
title: 步驟5
challengeType: 0
dashedName: step-5
---

# --description--

回到 `sortInputArray` 函數，你需要從 `select` 元素中獲取值。 由於它們都具有 `values-dropdown` 類，因此你可以一次查詢所有這些內容。

使用 `document.getElementsByClassName()`，傳入參數 `"values-dropdown"`，獲取具有該類的所有元素。 使用 `const` 將其賦值給 `inputValues` 變量。

# --hints--

你應該使用 `document.getElementsByClassName()` 獲取所有具有 `"values-dropdown"` 類的元素。

```js
assert.match(sortInputArray.toString(), /document\.getElementsByClassName\(\s*('|"|`)values-dropdown\1\s*\)/);
```

你應該將 `document.getElementsByClassName()` 的結果賦值給名爲 `inputValues` 的變量。

```js
assert.match(sortInputArray.toString(), /inputValues\s*=\s*document\.getElementsByClassName\(\s*('|"|`)values-dropdown\1\s*\)/);
```

你應該使用 `const` 聲明變量 `inputValues`。

```js
assert.match(code, /const\s+inputValues\s*=\s*document\.getElementsByClassName\(\s*('|"|`)values-dropdown\1\s*\)/);
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" type="text/css" href="./styles.css" />
    <title>Number Sorter</title>
  </head>
  <body>
    <main>
      <h1>Number Sorter</h1>
      <form id="form" class="form">
        <h2>Input:</h2>
        <fieldset>
          <span class="bracket">[</span>
          <div>
            <select
              name="values"
              class="values-dropdown"
              aria-label="first number"
            >
              <option value="0">0</option>
              <option value="1">1</option>
              <option value="2">2</option>
              <option value="3">3</option>
              <option value="4">4</option>
              <option value="5">5</option>
              <option value="6">6</option>
              <option value="7">7</option>
              <option value="8" selected>8</option>
              <option value="9">9</option>
            </select>
            <span class="comma">,</span>
          </div>
          <div>
            <select
              name="values"
              class="values-dropdown"
              aria-label="second number"
            >
              <option value="0">0</option>
              <option value="1">1</option>
              <option value="2" selected>2</option>
              <option value="3">3</option>
              <option value="4">4</option>
              <option value="5">5</option>
              <option value="6">6</option>
              <option value="7">7</option>
              <option value="8">8</option>
              <option value="9">9</option>
            </select>
            <span class="comma">,</span>
          </div>
          <div>
            <select
              name="values"
              class="values-dropdown"
              aria-label="third number"
            >
              <option value="0">0</option>
              <option value="1">1</option>
              <option value="2">2</option>
              <option value="3">3</option>
              <option value="4" selected>4</option>
              <option value="5">5</option>
              <option value="6">6</option>
              <option value="7">7</option>
              <option value="8">8</option>
              <option value="9">9</option>
            </select>
            <span class="comma">,</span>
          </div>
          <div>
            <select
              name="values"
              class="values-dropdown"
              aria-label="fourth number"
            >
              <option value="0">0</option>
              <option value="1" selected>1</option>
              <option value="2">2</option>
              <option value="3">3</option>
              <option value="4">4</option>
              <option value="5">5</option>
              <option value="6">6</option>
              <option value="7">7</option>
              <option value="8">8</option>
              <option value="9">9</option>
            </select>
            <span class="comma">,</span>
          </div>
          <div>
            <select
              name="values"
              class="values-dropdown"
              aria-label="fifth number"
            >
              <option value="0">0</option>
              <option value="1">1</option>
              <option value="2">2</option>
              <option value="3" selected>3</option>
              <option value="4">4</option>
              <option value="5">5</option>
              <option value="6">6</option>
              <option value="7">7</option>
              <option value="8">8</option>
              <option value="9">9</option>
            </select>
          </div>
          <span class="bracket">]</span>
        </fieldset>
        <button id="sort">Sort</button>
      </form>
      <div class="output-container">
        <h2>Output:</h2>
        <div class="output-array">
          <span class="bracket">[</span>
          <div>
            <span class="output-value" id="output-value-0">0</span>
            <span class="comma">,</span>
          </div>
          <div>
            <span class="output-value" id="output-value-1">0</span>
            <span class="comma">,</span>
          </div>
          <div>
            <span class="output-value" id="output-value-2">0</span>
            <span class="comma">,</span>
          </div>
          <div>
            <span class="output-value" id="output-value-3">0</span>
            <span class="comma">,</span>
          </div>
          <div>
            <span class="output-value" id="output-value-4">0</span>
          </div>
            <span class="bracket">]</span>
        </div>
      </div>
    </main>
    <script src="./script.js"></script>
  </body>
</html>
```

```css
:root {
  --gray-00: #ffffff;
  --gray-05: #f5f6f7;
  --gray-15: #d0d0d5;
  --gray-75: #3b3b4f;
  --gray-85: #1b1b32;
  --gray-90: #0a0a23;
  --blue-50: #198eee;
  --error: #a94442;
  --danger-color: #850000;
  --danger-background: #ffadad;
}

*,
::before,
::after {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  font-family: "Lato", Helvetica, Arial, sans-serif;
  font-size: 18px;
  background-color: var(--gray-85);
  color: var(--gray-05);
}

main {
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1 {
  margin: 30px auto;
}

h2 {
  margin-bottom: 15px;
}

form {
  width: 100%;
  text-align: center;
  padding: 15px;
}

fieldset {
  border: 0 none;
  height: 100%;
  margin: auto;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

fieldset div {
  display: flex;
  justify-content: center;
  align-items: center;
}

.bracket,
.comma {
  font-size: 2.3em;
}

form .comma {
  margin-left: 2px;
}

select {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
  height: 38px;
  width: 50px;
  text-align: center;
}

button {
  cursor: pointer;
  margin-top: 15px;
  text-decoration: none;
  background-image: linear-gradient(#fecc4c, #ffac33);
  border: 3px solid #feac32;
  padding: 10px 16px;
  font-size: 23px;
  width: 100%;
}

select:focus-visible,
button:focus-visible {
  outline: 3px solid var(--blue-50);
}

.output-container {
  width: 95%;
  min-height: 55px;
  margin-top: 25px;
  border-radius: 0;
  padding: 15px;
  overflow-wrap: break-word;
  text-align: center;
}

.output-array {
  width: 100%;
  margin: auto;
  display: flex;
  align-items: center;
  justify-content: space-around;
}

.output-value {
  font-size: 2em;
}

.alert {
  background-color: var(--danger-background);
  border: 3px solid var(--danger-color);
  color: var(--danger-color);
}

@media (min-width: 550px) {
  form,
  .output-container {
    max-width: 480px;
  }

  fieldset {
    max-width: 400px;
  }

  .output-array {
    max-width: 420px;
  }
}
```

```js
const sortButton = document.getElementById("sort");

--fcc-editable-region--
const sortInputArray = (event) => {
  event.preventDefault();


}
--fcc-editable-region--

sortButton.addEventListener("click", sortInputArray);
```
