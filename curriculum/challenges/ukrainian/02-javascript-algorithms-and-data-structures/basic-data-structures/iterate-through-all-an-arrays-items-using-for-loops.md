---
id: 587d7b7b367417b2b2512b15
title: Ітерація через усі елементи масиву за допомогою циклів for
challengeType: 1
forumTopicId: 301161
dashedName: iterate-through-all-an-arrays-items-using-for-loops
---

# --description--

Sometimes when working with arrays, it is very handy to be able to iterate through each item to find one or more elements that we might need, or to manipulate an array based on which data items meet a certain set of criteria. JavaScript offers several built in methods that each iterate over arrays in slightly different ways to achieve different results (such as `every()`, `forEach()`, `map()`, etc.), however the technique which is most flexible and offers us the greatest amount of control is a simple `for` loop.

Розглянемо приклад:

```js
function greaterThanTen(arr) {
  let newArr = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] > 10) {
      newArr.push(arr[i]);
    }
  }
  return newArr;
}

greaterThanTen([2, 12, 8, 14, 80, 0, 1]);
```

Використовуючи цикл `for`, ця функція ітерує та отримує доступ до кожного елемента масиву, а потім виконує створений нами тест. Таким чином ми легко й програмно визначаємо елементи, які більші за `10` та повертаємо новий масив `[12, 14, 80]`, який містить ці елементи.

# --instructions--

Ми визначили функцію `filteredArray`, яка приймає вкладений масив `arr` та `elem` як аргументи і повертає новий масив. `elem` означає елемент, що може не бути присутнім в одному або більше масивах в межах `arr`. Змініть функцію, використовуючи цикл `for`, щоб повернути відфільтровану версію переданого масиву так, щоб було вилучено будь-який вкладений масив з `elem` в межах `arr`.

# --hints--

`filteredArray([[10, 8, 3], [14, 6, 23], [3, 18, 6]], 18)` має повернути `[[10, 8, 3], [14, 6, 23]]`

```js
assert.deepEqual(
  filteredArray(
    [
      [10, 8, 3],
      [14, 6, 23],
      [3, 18, 6]
    ],
    18
  ),
  [
    [10, 8, 3],
    [14, 6, 23]
  ]
);
```

`filteredArray([["trumpets", 2], ["flutes", 4], ["saxophones", 2]], 2)` має повернути `[["flutes", 4]]`

```js
assert.deepEqual(
  filteredArray(
    [
      ['trumpets', 2],
      ['flutes', 4],
      ['saxophones', 2]
    ],
    2
  ),
  [['flutes', 4]]
);
```

`filteredArray([["amy", "beth", "sam"], ["dave", "sean", "peter"]], "peter")` має повернути `[["amy", "beth", "sam"]]`

```js
assert.deepEqual(
  filteredArray(
    [
      ['amy', 'beth', 'sam'],
      ['dave', 'sean', 'peter']
    ],
    'peter'
  ),
  [['amy', 'beth', 'sam']]
);
```

`filteredArray([[3, 2, 3], [1, 6, 3], [3, 13, 26], [19, 3, 9]], 3)` має повернути `[]`

```js
assert.deepEqual(
  filteredArray(
    [
      [3, 2, 3],
      [1, 6, 3],
      [3, 13, 26],
      [19, 3, 9]
    ],
    3
  ),
  []
);
```

Функція `filteredArray` має використовувати цикл `for`

```js
assert.notStrictEqual(filteredArray.toString().search(/for/), -1);
```

# --seed--

## --seed-contents--

```js
function filteredArray(arr, elem) {
  let newArr = [];
  // Only change code below this line

  // Only change code above this line
  return newArr;
}

console.log(filteredArray([[3, 2, 3], [1, 6, 3], [3, 13, 26], [19, 3, 9]], 3));
```

# --solutions--

```js
function filteredArray(arr, elem) {
  let newArr = [];
  for (let i = 0; i<arr.length; i++) {
    if (arr[i].indexOf(elem) < 0) {
      newArr.push(arr[i]);
    }
  }
  return newArr;
}
```
