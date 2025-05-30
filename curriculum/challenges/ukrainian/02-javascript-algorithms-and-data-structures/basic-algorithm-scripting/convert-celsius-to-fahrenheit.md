---
id: 56533eb9ac21ba0edf2244b3
title: Цельсій у Фаренгейт
challengeType: 1
forumTopicId: 16806
dashedName: convert-celsius-to-fahrenheit
---

# --description--

The formula to convert from Celsius to Fahrenheit is the temperature in Celsius times `9/5`, plus `32`.

Вам надано змінну `celsius`, яка відповідає температурі за Цельсієм. Використайте вже визначену змінну `fahrenheit` та призначте їй температуру за Фаренгейтом, еквівалентну заданій температурі за Цельсієм. Використайте запропоновану вище формулу для конвертації температури за Цельсієм у температуру за Фаренгейтом.

# --hints--

`convertCtoF(0)` має повертати число

```js
assert.isNumber(convertCtoF(0));
```

`convertCtoF(-30)` має повертати значення `-22`

```js
assert.strictEqual(convertCtoF(-30), -22);
```

`convertCtoF(-10)` має повертати значення `14`

```js
assert.strictEqual(convertCtoF(-10), 14);
```

`convertCtoF(0)` має повертати значення `32`

```js
assert.strictEqual(convertCtoF(0), 32);
```

`convertCtoF(20)` має повертати значення `68`

```js
assert.strictEqual(convertCtoF(20), 68);
```

`convertCtoF(30)` має повертати значення `86`

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
