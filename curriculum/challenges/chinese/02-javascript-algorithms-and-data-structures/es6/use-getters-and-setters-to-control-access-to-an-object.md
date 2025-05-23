---
id: 587d7b8c367417b2b2512b54
title: 使用 getter 和 setter 来控制对象的访问
challengeType: 1
forumTopicId: 301220
dashedName: use-getters-and-setters-to-control-access-to-an-object
---

# --description--

You can obtain values from an object and set the value of a property within an object.

这些操作通常被称为 <dfn>getters</dfn> 以及 <dfn>setters</dfn>。

Getter 函数的作用是可以让对象返回一个私有变量，而不需要直接去访问私有变量。

Setter 函数的作用是可以基于传进的参数来修改对象中私有变量。 这些修改可以是计算，或者是直接替换之前的值。

```js
class Book {
  constructor(author) {
    this._author = author;
  }
  // getter
  get writer() {
    return this._author;
  }
  // setter
  set writer(updatedAuthor) {
    this._author = updatedAuthor;
  }
}
const novel = new Book('anonymous');
console.log(novel.writer);
novel.writer = 'newAuthor';
console.log(novel.writer);
```

控制台将显示字符串 `anonymous` 和 `newAuthor`。

请注意用于调用 getter 和 setter 的语法。 它们甚至看起来不像是函数。 getter 和 setter 非常重要，因为它们隐藏了内部的实现细节。

**注意：** 通常会在私有变量前添加下划线（`_`）。 然而，这种做法本身并不是将变量变成私有的。

# --instructions--

使用 `class` 关键字创建一个 `Thermostat` class。 `constructor` 接收一个华氏温度。

在该类中，创建一个 `getter` 来获取摄氏温度，再创建一个 `setter` 来接受摄氏温度。

记得在 `C = 5/9 * (F - 32)` 和 `F = C * 9.0 / 5 + 32` 中，`F` 是华氏温度值，`C` 是摄氏温度值。

**注意：** 完成这个挑战后，应该在 class 中使用一个温度标准，要么是华氏温度，要么是摄氏温度。

这就是 getter 和 setter 的功能。 你正在为别的用户创建一个 API，不论你使用哪一个，用户都将获得正确的结果。

或者说，你从用户需求中抽象出了实现细节。

# --hints--

`Thermostat` 应该是一个具有 `constructor` 方法的 `class`。

```js
assert.isFunction(Thermostat);
assert.isFunction(Thermostat?.constructor);
```

应该使用 `class` 关键字。

```js
assert.match(code, /class/);
```

`Thermostat` 应该可以被实例化。

```js
const _t = new Thermostat(122);
assert.isObject(_t);
```

当实例化华氏温度值时，`Thermostat` 应该被设置为正确的 `temperature`。

```js
const _t = new Thermostat(122);
assert.strictEqual(_t?.temperature, 50);
```

应该定义一个 `getter`。

```js
const _desc = Object.getOwnPropertyDescriptor(Thermostat.prototype, 'temperature');
assert.isFunction(_desc?.get);
```

应该定义一个 `setter`。

```js
const _desc = Object.getOwnPropertyDescriptor(Thermostat.prototype, 'temperature');
assert.isFunction(_desc?.set);
```

调用带有摄氏温度值的 `setter` 应该设置 `temperature`。

```js
const _t = new Thermostat(32);
_t.temperature = 26;
const _u = new Thermostat(32);
_u.temperature = 50;
assert.approximately(_t.temperature, 26, 0.1);
assert.approximately(_u.temperature, 50, 0.1);
```

# --seed--

## --seed-contents--

```js
// Only change code below this line

// Only change code above this line

const thermos = new Thermostat(76); // Setting in Fahrenheit scale
let temp = thermos.temperature; // 24.44 in Celsius
thermos.temperature = 26;
temp = thermos.temperature; // 26 in Celsius
```

# --solutions--

```js
class Thermostat {
  constructor(fahrenheit) {
    this._tempInCelsius = 5/9 * (fahrenheit - 32);
  }
  get temperature(){
    return this._tempInCelsius;
  }
  set temperature(newTemp){
    this._tempInCelsius = newTemp;
  }
}

const thermos = new Thermostat(76); // Setting in Fahrenheit scale
let temp = thermos.temperature; // 24.44 in Celsius
thermos.temperature = 26;
temp = thermos.temperature; // 26 in Celsius
```
