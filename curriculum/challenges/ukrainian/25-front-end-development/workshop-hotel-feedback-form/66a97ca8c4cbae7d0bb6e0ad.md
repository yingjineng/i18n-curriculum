---
id: 66a97ca8c4cbae7d0bb6e0ad
title: Крок 32
challengeType: 0
dashedName: step-32
---

# --description--

До елемента `select` додайте таких п’ять елементів `option` з відповідним текстом `option` і значенням атрибута `value`:

**Значення атрибута `value`:**

- poor
- satisfactory
- good
- very-good
- excellent

**Текст елемента `option`:**

- Poor
- Satisfactory
- Good
- Very Good
- Excellent


Не забудьте додати атрибут `selected` до елемента `option` зі значенням `"excellent"`.

# --hints--

Ви повинні мати елемент `option` зі значенням `"poor"`.

```js
assert.exists(document.querySelector('fieldset:nth-of-type(4) select#food option[value="poor"]'));
```

Елемент `option` зі значенням `"poor"` повинен мати текст `"Poor"`.

```js
assert.strictEqual(document.querySelector('fieldset:nth-of-type(4) select#food option[value="poor"]')?.textContent, 'Poor');
```

Ви повинні мати елемент `option` зі значенням `"satisfactory"`.

```js
assert.exists(document.querySelector('fieldset:nth-of-type(4) select#food option[value="satisfactory"]'));
```

Елемент `option` зі значенням `"satisfactory"` повинен мати текст `"Satisfactory"`.

```js
assert.strictEqual(document.querySelector('fieldset:nth-of-type(4) select#food option[value="satisfactory"]')?.textContent, 'Satisfactory');
```

Ви повинні мати елемент `option` зі значенням `"good"`.

```js
assert.exists(document.querySelector('fieldset:nth-of-type(4) select#food option[value="good"]'));
```

Елемент `option` зі значенням `"good"` повинен мати текст `"Good"`.

```js

assert.strictEqual(document.querySelector('fieldset:nth-of-type(4) select#food option[value="good"]')?.textContent, 'Good');
```

Ви повинні мати елемент `option` зі значенням `"very-good"`.

```js
assert.exists(document.querySelector('fieldset:nth-of-type(4) select#food option[value="very-good"]'));
```

Елемент `option` зі значенням `"very-good"` повинен мати текст `"Very Good"`.

```js
assert.strictEqual(document.querySelector('fieldset:nth-of-type(4) select#food option[value="very-good"]')?.textContent, 'Very Good');
```

Ви повинні мати елемент `option` зі значенням `"excellent"`.

```js
assert.exists(document.querySelector('fieldset:nth-of-type(4) select#food option[value="excellent"]'));
```

Елемент `option` зі значенням `"excellent"` повинен мати текст `"Excellent"`.

```js

assert.strictEqual(document.querySelector('fieldset:nth-of-type(4) select#food option[value="excellent"]')?.textContent, 'Excellent');
```

Ви повинні мати елемент `option` з атрибутом `selected` зі значенням `"excellent"`.

```js
assert.exists(document.querySelector('fieldset:nth-of-type(4) select#food option[value="excellent"][selected]'));
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Hotel Feedback Form</title>
  </head>
  <body>
    <header>
      <h1>Hotel Feedback Form</h1>
      <p>
        Thank you for staying with us. Please provide feedback on your recent
        stay.
      </p>
    </header>
    <main>
      <form method="POST" action="https://hotel-feedback.freecodecamp.org">
        <fieldset>
          <legend>Personal Information</legend>
          <label for="full-name">Name (required):</label>
          <input type="text" id="full-name" name="name" placeholder="Ex. John Doe" required size="20">

          <label for="email">Email address (required):</label>
          <input
            placeholder="example@email.com"
            required
            id="email"
            type="email"
            name="email"
            size="20"
          />
          <label for="age">Age (optional):</label>
          <input type="number" name="age" id="age" min="3" max="100" />
        </fieldset>

        <fieldset>
          <legend>Was this your first time at our hotel?</legend>
          <label for="yes-option">Yes</label>
          <input id="yes-option" type="radio" name="hotel-stay" />
          <label for="no-option">No</label>
          <input id="no-option" type="radio" name="hotel-stay" />
        </fieldset>

        <fieldset>
          <legend>
            Why did you choose to stay at our hotel? (Check all that apply)
          </legend>

          <label for="ads">Social Media Ads</label>
          <input type="checkbox" id="ads" name="ads" value="ads" />

          <label for="recommendation">Personal Recommendation</label>
          <input
            type="checkbox"
            id="recommendation"
            name="recommendation"
            value="recommendation"
          />

          <label for="location">Location</label>
          <input type="checkbox" id="location" name="location" value="location" />

          <label for="reputation">Reputation</label>
          <input
            checked
            type="checkbox"
            id="reputation"
            name="reputation"
            value="reputation"
          />

          <label for="price">Price</label>
          <input type="checkbox" id="price" name="price" value="price" />
        </fieldset>

        <fieldset>
          <legend>Ratings</legend>

          <label for="service">How was the service?</label>

          <select name="service" id="service">
            <option value="poor">Poor</option>
            <option value="satisfactory">Satisfactory</option>
            <option value="good">Good</option>
            <option value="very-good">Very Good</option>
            <option selected value="excellent">Excellent</option>
          </select>

          <label for="food">How was the food?</label>

          --fcc-editable-region--
          <select name="food" id="food">

          </select>
          --fcc-editable-region--
        </fieldset>
      </form>
    </main>
  </body>
</html>
```
