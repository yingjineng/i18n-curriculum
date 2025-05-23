---
id: 5e46f983ac417301a38fb933
title: SHA-1 密码破解器
challengeType: 10
forumTopicId: 462374
helpCategory: Python
dashedName: sha-1-password-cracker
---

# --description--

You will be <a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-SHA-1-password-cracker" target="_blank" rel="noopener noreferrer nofollow">working on this project with our Gitpod starter code</a> Learn <a href="https://forum.freecodecamp.org/t/how-to-use-gitpod-in-the-curriculum/668669#how-can-i-share-my-workspace-to-get-help-8" target="_blank" rel="noopener noreferrer nofollow">how to share your Gitpod workspace to get help</a>.

我们仍在开发Python课程的交互式教学部分 目前，你可以在 freeCodeCamp.org 的 YouTube 频道中通过视频学习到这个项目相关的所有知识

- <a href="https://www.freecodecamp.org/news/python-for-everybody/" target="_blank" rel="noopener noreferrer nofollow">Python for Everybody Video Course</a> (14 hours)

- <a href="https://www.freecodecamp.org/news/learn-python-basics-in-depth-video-course/" target="_blank" rel="noopener noreferrer nofollow">Learn Python Basics in Depth</a> (4 hours)

- <a href="https://www.freecodecamp.org/news/intermediate-python-course/" target="_blank" rel="noopener noreferrer nofollow">Intermediate Python Course</a> (6 hours)

# --instructions--

密码不应以纯文本形式存储。 它们应该存储为哈希值，以防万一密码列表被泄露。 然而，并不是所有的哈希都是一样的。

在这个项目中，你将通过创建一个密码破解器来找出使用 SHA-1 散列的密码，从而了解到良好安全的重要性。

创建一个函数，该函数接受密码的 SHA-1 哈希值，如果它是使用的前 10,000 个密码之一，则返回该密码。 如果 SHA-1 哈希不是数据库中的密码，则返回“密码不在数据库中”。

该函数应该对 `top-10000-passwords.txt` 中的每个密码进行散列，并将其与传递给函数的散列进行比较。

该函数应采用名为 `use_salts` 的可选第二个参数。 如果设置为 true，则文件 `known-salts.txt` 中的每个 salt 字符串，都应该在散列之前，和将它与传递给函数的哈希值进行比较之前，添加到 `top-10000-passwords.txt` 中的每个密码的之前和之后。

以下是一些用于测试该功能的散列密码：

- `b305921a3723cd5d70a375cd21a61e60aabb84ec` should return "sammy123"
- `c7ab388a5ebefbf4d550652f1eb4d833e5316e3e` 应该返回 “abacab”
- `5baa61e4c9b93f3f0682250b6cf8331b7ee68fd8` 应该返回 “password”

以下是一些散列密码，用于在 `use_salts` 设置为 `True` 时测试该功能：

- `53d8b3dc9d39f0184144674e310185e41a87ffd5` should return "superman"
- `da5a4e8cf89539e66097acd2f8af128acae2f8ae` 应该返回 “q1w2e3r4t5”
- `ea3f62d498e3b98557f9f9cd0d905028b3b019e1` 应该返回 “bubbles1”

`hashlib` 库已经为你导入。 你应该在你的代码中使用它。 <a href="https://docs.python.org/3/library/hashlib.html" target="_blank" rel="noopener noreferrer nofollow">在此了解更多关于 “hashlib” 的信息</a>。

## Development

在 `password_cracker.py` 中编写你的代码。 对于开发，你可以使用 `main.py` 来测试你的代码。

## 测试

此项目的单元测试在 `test_module.py` 中。 为了你的方便，我们将测试从 `test_module.py` 导入到 `main.py`。

## 提交

复制项目的 URL 并将其提交给 freeCodeCamp。

# --hints--

它应该通过所有的 Python 测试。

```js

```

# --solutions--

```py
  # Python challenges don't need solutions,
  # because they would need to be tested against a full working project.
  # Please check our contributing guidelines to learn more.
```
