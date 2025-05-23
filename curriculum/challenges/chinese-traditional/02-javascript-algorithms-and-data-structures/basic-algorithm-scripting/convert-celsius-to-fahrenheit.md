---
id: 56533eb9ac21ba0edf2244b3
title: 將攝氏度轉換爲華氏度
challengeType: 1
forumTopicId: 16806
dashedName: convert-celsius-to-fahrenheit
---

# --description--

The formula to convert from Celsius to Fahrenheit is the temperature in Celsius times `9/5`, plus `32`.

輸入參數 `celsius` 代表一個攝氏度的溫度。 使用已定義的變量 `fahrenheit`，並賦值爲相應的華氏度的溫度值。 使用上面提到的公式來幫助將攝氏溫度轉換爲華氏溫度。

# --hints--

`convertCtoF(0)` 應該返回一個數字

```js
assert.isNumber(convertCtoF(0));
```

`convertCtoF(-30)` 應該返回 `-22` 的值

```js
assert.strictEqual(convertCtoF(-30), -22);
```

`convertCtoF(-10)` 應該返回 `14` 的值

```js
assert.strictEqual(convertCtoF(-10), 14);
```

`convertCtoF(0)` 應該返回 `32` 的值

```js
assert.strictEqual(convertCtoF(0), 32);
```

`convertCtoF(20)` 應該返回 `68` 的值

```js
assert.strictEqual(convertCtoF(20), 68);
```

`convertCtoF(30)` 應該返回 `86` 的值

```js
assert.strictEqual(convertCtoF(30), 86);
```

# --seed--

## --seed-contents--

```js
function convertCtoF(celsius) {
  let fahrenheit;
  return fahrenheit;
}

convertCtoF(30);
```

# --solutions--

```js
function convertCtoF(celsius) {
  let fahrenheit = celsius * (9 / 5) + 32;
  return fahrenheit;
}

convertCtoF(30);
```
