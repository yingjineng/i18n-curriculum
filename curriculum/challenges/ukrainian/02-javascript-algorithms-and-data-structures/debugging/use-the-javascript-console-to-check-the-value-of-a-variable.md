---
id: 587d7b83367417b2b2512b33
title: Використання консолі JavaScript для перевірки значення змінної
challengeType: 1
forumTopicId: 18372
dashedName: use-the-javascript-console-to-check-the-value-of-a-variable
---

# --description--

Both Chrome and Firefox have excellent JavaScript consoles, also known as DevTools, for debugging your JavaScript.

Ви можете знайти інструменти розробника у меню Chrome або вебконсоль у меню Firefox. Якщо ви використовуєте інший браузер або мобільний телефон, ми наполегливо радимо вам перейти на комп’ютерну версію Firefox або Chrome.

Метод `console.log()`, який «друкує» вихідні дані з того, що знаходиться між його дужками, на консоль, мабуть, буде найкориснішим інструментом для налагодження програм. Розміщення його у стратегічно важливих місцях вашого коду може показати вам проміжні значення змінних. Добре мати уявлення про те, яким повинен бути результат, перш ніж глянути, яким він є. Формування ключових моментів для розуміння стану ваших розрахунків у всьому коді допоможе скоротити кількість місць для пошуку проблеми.

Ось приклад виведення рядка `Hello world!` на консоль:

```js
console.log('Hello world!');
```

# --instructions--

Використайте метод `console.log()` там, де вказано в коді, щоб вивести на екран значення змінної `a`.

# --hints--

Ваш код повинен використовувати `console.log()` для перевірки значення змінної `a`.

```js
assert(__helpers.removeJSComments(code).match(/console\.log\(a\)/g));
```

# --seed--

## --seed-contents--

```js
let a = 5;
let b = 1;
a++;
// Only change code below this line


let sumAB = a + b;
console.log(sumAB);
```

# --solutions--

```js
var a = 5; console.log(a);
```
