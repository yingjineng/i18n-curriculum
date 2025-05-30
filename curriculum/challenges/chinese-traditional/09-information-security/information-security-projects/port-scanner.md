---
id: 5e46f979ac417301a38fb932
title: 端口掃描器
challengeType: 10
forumTopicId: 462372
helpCategory: Python
dashedName: port-scanner
---

# --description--

You will be <a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-port-scanner" target="_blank" rel="noopener noreferrer nofollow">working on this project with our Gitpod starter code</a>. Learn <a href="https://forum.freecodecamp.org/t/how-to-use-gitpod-in-the-curriculum/668669#how-can-i-share-my-workspace-to-get-help-8" target="_blank" rel="noopener noreferrer nofollow">how to share your Gitpod workspace to get help</a>.

我們仍在開發Python課程的交互式教學部分 目前，你可以在 freeCodeCamp.org 的 YouTube 頻道中通過視頻學習到這個項目相關的所有知識

- <a href="https://www.freecodecamp.org/news/python-for-everybody/" target="_blank" rel="noopener noreferrer nofollow">Python for Everybody Video Course</a> (14 hours)

- <a href="https://www.freecodecamp.org/news/learn-python-basics-in-depth-video-course/" target="_blank" rel="noopener noreferrer nofollow">深入學習 Python 基礎知識</a>（4 小時）

- <a href="https://www.freecodecamp.org/news/intermediate-python-course/" target="_blank" rel="noopener noreferrer nofollow">Python 中級課程</a>（6 小時）

# --instructions--

使用 Python 創建一個端口掃描器。

在 `port_scanner.py` 文件中，創建一個名爲 `get_open_ports` 的函數，它接受一個 `target` 參數和一個 `port_range` 參數。 `target` 可以是 URL 或 IP 地址。 `port_range` 是兩個數字的列表，表示要檢查的端口範圍的第一個和最後一個數字。

以下是如何調用該函數的示例：

```py
get_open_ports("209.216.230.240", [440, 445])
get_open_ports("www.stackoverflow.com", [79, 82])
```

該函數應返回給定範圍內的開放端口列表。

`get_open_ports` 函數還應採用可選的第三個參數 `True` 來表示“詳細”模式。 如果將其設置爲 true，則該函數應返回描述性字符串而不是端口列表。

以下是詳細模式下應返回的字符串格式（`{}` 中的文本表示應顯示的信息）：

```bash
Open ports for {URL} ({IP address})
PORT     SERVICE
{port}   {service name}
{port}   {service name}
```

你可以使用 `common_ports.py` 中的字典爲每個端口獲取正確的服務名稱。

例如，如果函數是這樣調用的：

```py
port_scanner.get_open_ports("scanme.nmap.org", [20, 80], True)
```

它應該返回以下內容：

```bash
Open ports for scanme.nmap.org (45.33.32.156)
PORT     SERVICE
22       ssh
80       http
```

確保包含正確的間距和換行符。

如果傳入 `get_open_ports` 函數的 URL 無效，該函數應返回字符串：“Error: Invalid hostname”。

如果傳入 `get_open_ports` 函數的 IP 地址無效，該函數應返回字符串：“Error:  Invalid IP address”。

## Development

在 `port_scanner.py` 中編寫你的代碼。 對於開發，你可以使用 `main.py` 來測試你的代碼。

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
