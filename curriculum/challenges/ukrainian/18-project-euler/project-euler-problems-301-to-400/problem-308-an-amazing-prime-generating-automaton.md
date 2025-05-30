---
id: 5900f4a11000cf542c50ffb3
title: 'Завдання 308: дивовижний автоматизований генератор простих чисел'
challengeType: 1
forumTopicId: 301962
dashedName: problem-308-an-amazing-prime-generating-automaton
---

# --description--

Програма, написана мовою програмування Fractran, складається зі списку дробів.

Внутрішній стан віртуальної машини Fractran — це натуральне число, значення якого рівне початковому значенню. Кожна ітерація програми Fractran множить число стану на перший дріб в списку, в результаті чого виходить ціле число.

Наприклад, одна з програм Fractran, яку написав Джон Гортон Конвей для генерації простих чисел, складається з таких 14 дробів:

$$\frac{17}{91}, \frac{78}{85}, \frac{19}{51}, \frac{23}{38}, \frac{29}{33}, \frac{77}{29}, \frac{95}{23}, \frac{77}{19}, \frac{1}{17}, \frac{11}{13}, \frac{13}{11}, \frac{15}{2}, \frac{1}{7}, \frac{55}{1}$$

Починаючи з початкового цілого числа 2, послідовні ітерації програми виробляють наступну послідовність:

$$15, 825, 725, 1925, 2275, 425, \ldots, 68, \mathbf{4}, 30, \ldots, 136, \mathbf{8}, 60, \ldots, 544, \mathbf{32}, 240, \ldots$$

У цій послідовності з’являються степені двійки: $2^2, 2^3, 2^5, \ldots$.

Можна довести, що всі степені двійки в цій послідовності мають прості показники і що всі прості числа з’являються як показники степенів двійки в правильному порядку!

Припустимо, хтось використовує вищезгадану програму Fractran, щоб розв’язати завдання №7 з проєкту Ейлера (знайти ${10001}^{\text{-е}}$ просте число). Скільки потрібно виконати ітерацій, щоб програма видала $2^{10001^{\text{-е}}\text{ просте число}}$?

# --hints--

`primeGeneratingAutomation()` має повернути `1539669807660924`.

```js
assert.strictEqual(primeGeneratingAutomation(), 1539669807660924);
```

# --seed--

## --seed-contents--

```js
function primeGeneratingAutomation() {

  return true;
}

primeGeneratingAutomation();
```

# --solutions--

```js
// solution required
```
