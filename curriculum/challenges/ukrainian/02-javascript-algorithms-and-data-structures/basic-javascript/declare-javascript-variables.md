---
id: bd7123c9c443eddfaeb5bdef
title: Оголошення змінних JavaScript
challengeType: 1
forumTopicId: 17556
dashedName: declare-javascript-variables
---

# --description--

In computer science, <dfn>data</dfn> is anything that is meaningful to the computer. JavaScript provides eight different <dfn>data types</dfn> which are `undefined`, `null`, `boolean`, `string`, `symbol`, `bigint`, `number`, and `object`.

Наприклад, комп’ютери розрізняють числа, як-от `12` та рядки (`strings`), як-от `"12"`, `"dog"` або `"123 cats"`, які є набором символів. Комп’ютери можуть виконувати математичні операції з числом, але не з рядком.

<dfn>Змінні</dfn> дозволяють комп’ютеру динамічно зберігати та керувати даними. Для цього вони використовують «мітку», щоб вказати на дані, а не використовувати самі дані. Будь-який з восьми видів даних може зберігатися у змінній.

Змінні подібні до змінних «x» та «y», які використовуються в математиці, і це означає, що вони є простою назвою для представлення даних, на які ми хочемо посилатися. Комп’ютерні змінні відрізняються від математичних змінних тим, що вони можуть зберігати різні значення в різний час.

Ми вказуємо JavaScript створити або <dfn>оголосити</dfn> змінну, написавши перед нею ключове слово `var`, ось так:

```js
var ourName;
```

створює змінну під назвою `ourName`. Інструкції в JavaScript завершуються крапкою з комою. Назви змінних можуть складатись з цифр, букв та `$` або `_`, але не можуть містити пробіли або починатися з числа.

# --instructions--

Використайте ключове слово `var`, щоб створити змінну під назвою `myName`.

**Підказка**  
Якщо застрягли, перегляньте приклад `ourName` вище.

# --hints--

Ви повинні оголосити `myName` з ключовим словом `var`, закінчуючи крапкою з комою

```js
assert(/var\s+myName\s*;/.test(__helpers.removeJSComments(code)));
```

# --seed--

## --after-user-code--

```js
if(typeof myName !== "undefined"){(function(v){return v;})(myName);}
```

## --seed-contents--

```js

```

# --solutions--

```js
var myName;
```
