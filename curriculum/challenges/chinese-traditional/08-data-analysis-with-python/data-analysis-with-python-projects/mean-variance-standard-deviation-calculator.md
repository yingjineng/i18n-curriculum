---
id: 5e46f7e5ac417301a38fb928
title: 均值-方差-標準差 計算器
challengeType: 10
forumTopicId: 462366
dashedName: mean-variance-standard-deviation-calculator
---

# --description--

You will be <a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-mean-variance-standard-deviation-calculator/" target="_blank" rel="noopener noreferrer nofollow">working on this project with our Gitpod starter code</a>.

我們仍在開發Python課程的交互式教學部分 目前，你可以在 freeCodeCamp.org 的 YouTube 頻道中通過視頻學習到這個項目相關的所有知識

- <a href="https://www.freecodecamp.org/news/python-for-everybody/" target="_blank" rel="noopener noreferrer nofollow">Python for Everybody Video Course</a> (14 hours)

- <a href="https://www.freecodecamp.org/news/how-to-analyze-data-with-python-pandas/" target="_blank" rel="noopener noreferrer nofollow">如何使用 Python Pandas 分析數據</a>（10 小時）

# --instructions--

在 `mean_var_std.py` 中創建一個名爲 `calculate()` 的函數，該函數使用 Numpy 輸出行、列、和 3 x 3 矩陣中的元素。

函數的輸入應該是一個包含 9 個數字的列表。 該函數應將列表轉換爲 3 x 3 Numpy 數組，然後返回一個字典，其中包含沿兩個軸和展平矩陣的均值、方差、標準差、最大值、最小值和總和。

返回的字典應遵循以下格式：

```py
{
  'mean': [axis1, axis2, flattened],
  'variance': [axis1, axis2, flattened],
  'standard deviation': [axis1, axis2, flattened],
  'max': [axis1, axis2, flattened],
  'min': [axis1, axis2, flattened],
  'sum': [axis1, axis2, flattened]
}
```

如果將包含少於 9 個元素的列表傳遞給函數，它應該引發 `ValueError` 異常並顯示消息：“List must contain nine numbers.” 返回的字典中的值應該是列表而不是 Numpy 數組。

例如，`calculate([0,1,2,3,4,5,6,7,8])` 應該返回：

```py
{
  'mean': [[3.0, 4.0, 5.0], [1.0, 4.0, 7.0], 4.0],
  'variance': [[6.0, 6.0, 6.0], [0.6666666666666666, 0.6666666666666666, 0.6666666666666666], 6.666666666666667],
  'standard deviation': [[2.449489742783178, 2.449489742783178, 2.449489742783178], [0.816496580927726, 0.816496580927726, 0.816496580927726], 2.581988897471611],
  'max': [[6, 7, 8], [2, 5, 8], 8],
  'min': [[0, 1, 2], [0, 3, 6], 0],
  'sum': [[9, 12, 15], [3, 12, 21], 36]
}
```

## Development

Write your code in `mean_var_std.py`. 對於開發，你可以使用 `main.py` 來測試你的代碼。 In order to run your code, type `python3 main.py` into the GitPod terminal and hit enter. This will cause the included CPython interpreter to run the `main.py` file.

## 測試

這個項目的單元測試在 `test_module.py` 中。 爲了你的方便，我們將測試從 `test_module.py` 導入到 `main.py`。

## 提交

複製項目的 URL 並將其提交給 freeCodeCamp。

# --hints--

它應該通過所有的 Python 測試。

```js

```

# --solutions--

```py
  # Python challenges don't need solutions,
  # because they would need to be tested against a full working project.
  # Please check our contributing guidelines to learn more.
```
