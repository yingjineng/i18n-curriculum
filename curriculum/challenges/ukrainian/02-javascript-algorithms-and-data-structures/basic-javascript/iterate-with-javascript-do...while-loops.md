---
id: 5a2efd662fb457916e1fe604
title: Ітерація з циклами do...while у JavaScript
challengeType: 1
forumTopicId: 301172
dashedName: iterate-with-javascript-do---while-loops
---

# --description--

The next type of loop you will learn is called a `do...while` loop. It is called a `do...while` loop because it will first `do` one pass of the code inside the loop no matter what, and then continue to run the loop `while` the specified condition evaluates to `true`.

```js
const ourArray = [];
let i = 0;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
```

Наведений вище приклад поводиться подібно до інших типів циклів, і кінцевий масив матиме такий вигляд: `[0, 1, 2, 3, 4]`. Однак цикл `do...while` відрізняється від інших циклів своєю поведінкою, коли умова не відповідає першій перевірці. Розглянемо на дії. Ось звичайний цикл `while`, який запускає код за умови, що `i < 5`:

```js
const ourArray = []; 
let i = 5;

while (i < 5) {
  ourArray.push(i);
  i++;
}
```

У цьому прикладі ми ініціалізуємо значення `ourArray` до порожнього масиву і значення `i` до 5. Коли ми виконуємо цикл `while`, умова обчислюється як `false`, оскільки `i` не менше за 5, тому ми не виконуємо код всередині циклу. Результатом є те, що `ourArray` не матиме доданих значень і досі виглядатиме як `[]`, коли весь код у прикладі вище вже завершить виконання. А зараз погляньте на цикл `do...while`:

```js
const ourArray = []; 
let i = 5;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
```

У цьому випадку ми ініціалізуємо значення `i` до 5, так само, як ми зробили з циклом `while`. Коли ми доходимо до наступного рядка, то бачимо, що немає умови, тому ми переходимо до коду у фігурних дужках та виконуємо його. Ми додамо один елемент до масиву та збільшимо `i` перед тим, як перейти до перевірки умови. Коли ми обчислимо умову `i < 5` в останньому рядку, ми побачимо, що зараз `i` дорівнює 6 та не проходить перевірку умови, тому ми виходимо з циклу і завершуємо роботу. В кінці вищеподаного прикладу, значення `ourArray` становить `[5]`. По суті, цикл `do...while` гарантує те, що код всередині циклу виконається принаймні один раз. Спробуємо заставити цикл `do...while` працювати, передаючи значення до масиву.

# --instructions--

Змініть цикл `while` у коді на цикл `do...while` так, щоб цикл передавав лише число `10` до `myArray`, та `i` дорівнювала `11`, коли код закінчить виконання.

# --hints--

Для цього завдання ви повинні використати цикл `do...while`.

```js
assert(__helpers.removeJSComments(code).match(/do/g));
```

`myArray` має дорівнювати `[10]`.

```js
assert.deepEqual(myArray, [10]);
```

`i` має дорівнювати `11`

```js
assert.equal(i, 11);
```

# --seed--

## --after-user-code--

```js
if(typeof myArray !== "undefined"){(function(){return myArray;})();}
```

## --seed-contents--

```js
// Setup
const myArray = [];
let i = 10;

// Only change code below this line
while (i < 5) {
  myArray.push(i);
  i++;
}
```

# --solutions--

```js
const myArray = [];
let i = 10;
do {
  myArray.push(i);
  i++;
} while (i < 5)
```
