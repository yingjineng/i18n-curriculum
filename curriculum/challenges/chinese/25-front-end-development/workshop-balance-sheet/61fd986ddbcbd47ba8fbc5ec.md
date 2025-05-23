---
id: 61fd986ddbcbd47ba8fbc5ec
title: 步骤 23
challengeType: 0
dashedName: step-23
---

# --description--

在第三个 `tr` 元素内，添加一个 `th` 元素，其文本内容应为 `Credit The outstanding balance on our credit card.`。将此文本中，`Credit` 之后的部分（即 `The outstanding balance on our credit card.`）用一个 `class` 属性值为 `description` 的 `span` 元素包裹起来。

在该 `th` 元素之后，于同一个 `tr` 内，添加三个 `td` 元素。按顺序，分别给它们设置以下文本内容：`$50`、`$50` 和 `$75`。将第三个 `td` 元素的 `class` 属性设置为 `current`。

# --hints--

你的第三个 `tr` 元素内应该有一个 `th` 元素。

```js
const table = document.querySelectorAll('table')?.[1];
const tbody = table?.querySelector('tbody');
const tableRow = tbody?.querySelectorAll('tr')?.[2];
assert.isNotNull(tableRow?.querySelector('th'));
```

你的 `th` 元素的文本内容应为 `Credit The outstanding balance on our credit card.`。

```js
const table = document.querySelectorAll('table')?.[1];
const tbody = table?.querySelector('tbody');
const tableRow = tbody?.querySelectorAll('tr')?.[2];
assert.strictEqual(
  tableRow?.querySelector('th')?.innerText,
  'Credit The outstanding balance on our credit card.'
);
```

你应该将文本 `The outstanding balance on our credit card.` 用一个 `span` 元素包裹起来。

```js
const table = document.querySelectorAll('table')?.[1];
const tbody = table?.querySelector('tbody');
const tableRow = tbody?.querySelectorAll('tr')?.[2];
assert.strictEqual(
  tableRow?.querySelector('th > span')?.textContent,
  'The outstanding balance on our credit card.'
);
```

你的 `span` 元素的 `class` 属性应设置为 `description`。

```js
const table = document.querySelectorAll('table')?.[1];
const tbody = table?.querySelector('tbody');
const tableRow = tbody?.querySelectorAll('tr')?.[2];
assert.isTrue(
  tableRow?.querySelector('th > span')?.classList?.contains('description')
);
```

你应该有三个 `td` 元素。

```js
const table = document.querySelectorAll('table')?.[1];
const tbody = table?.querySelector('tbody');
const tableRow = tbody?.querySelectorAll('tr')?.[2];
assert.lengthOf(tableRow?.querySelectorAll('td'), 3);
```

你的第一个 `td` 元素的文本内容应为 `$50`。

```js
const table = document.querySelectorAll('table')?.[1];
const tbody = table?.querySelector('tbody');
const tableRow = tbody?.querySelectorAll('tr')?.[2];
assert.strictEqual(tableRow?.querySelectorAll('td')?.[0]?.textContent, '$50');
```

你的第二个 `td` 元素的文本内容应为 `$50`。

```js
const table = document.querySelectorAll('table')?.[1];
const tbody = table?.querySelector('tbody');
const tableRow = tbody?.querySelectorAll('tr')?.[2];
assert.strictEqual(tableRow?.querySelectorAll('td')?.[1]?.textContent, '$50');
```

你的第三个 `td` 元素的文本内容应为 `$75`。

```js
const table = document.querySelectorAll('table')?.[1];
const tbody = table?.querySelector('tbody');
const tableRow = tbody?.querySelectorAll('tr')?.[2];
assert.strictEqual(tableRow?.querySelectorAll('td')?.[2]?.textContent, '$75');
```

你的第三个 `td` 元素的 `class` 属性应设置为 `current`。

```js
const table = document.querySelectorAll('table')?.[1];
const tbody = table?.querySelector('tbody');
const tableRow = tbody?.querySelectorAll('tr')?.[2];
assert.isTrue(
  tableRow?.querySelectorAll('td')?.[2]?.classList?.contains('current')
);
```

# --seed--

## --seed-contents--

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Balance Sheet</title>
    <link rel="stylesheet" href="./styles.css" />
  </head>
  <body>
    <main>
      <section>
        <h1>
          <span class="flex">
            <span>AcmeWidgetCorp</span>
            <span>Balance Sheet</span>
          </span>
        </h1>
        <div id="years" aria-hidden="true">
          <span class="year">2019</span>
          <span class="year">2020</span>
          <span class="year">2021</span>
        </div>
        <div class="table-wrap">
          <table>
            <caption>
              Assets
            </caption>
            <thead>
              <tr>
                <td></td>
                <th><span class="sr-only year">2019</span></th>
                <th><span class="sr-only year">2020</span></th>
                <th class="current"><span class="sr-only year">2021</span></th>
              </tr>
            </thead>
            <tbody>
              <tr class="data">
                <th>Cash <span class="description">This is the cash we currently have on hand.</span></th>
                <td>$25</td>
                <td>$30</td>
                <td class="current">$28</td>
              </tr>
              <tr class="data">
                <th>Checking <span class="description">Our primary transactional account.</span></th>
                <td>$54</td>
                <td>$56</td>
                <td class="current">$53</td>
              </tr>
              <tr class="data">
                <th>Savings <span class="description">Funds set aside for emergencies.</span></th>
                <td>$500</td>
                <td>$650</td>
                <td class="current">$728</td>
              </tr>
              <tr class="total">
                <th>Total <span class="sr-only">Assets</span></th>
                <td>$579</td>
                <td>$736</td>
                <td class="current">$809</td>
              </tr>
            </tbody>
          </table>
          <table>
            <caption>
              Liabilities
            </caption>
            <thead>
              <tr>
                <td></td>
                <th><span class="sr-only">2019</span></th>
                <th><span class="sr-only">2020</span></th>
                <th><span class="sr-only">2021</span></th>
              </tr>
            </thead>
            <tbody>
--fcc-editable-region--
              <tr class="data">
                <th>Loans <span class="description">The outstanding balance on our startup loan.</span></th>
                <td>$500</td>
                <td>$250</td>
                <td class="current">$0</td>
              </tr>
              <tr class="data">
                <th>Expenses <span class="description">Annual anticipated expenses, such as payroll.</span></th>
                <td>$200</td>
                <td>$300</td>
                <td class="current">$400</td>
              </tr>
              <tr class="data">
              </tr>
              <tr class="total">
              </tr>
--fcc-editable-region--
            </tbody>
          </table>
          <table></table>
        </div>
      </section>
    </main>
  </body>
</html>
```

```css

```

