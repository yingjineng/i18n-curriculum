---
id: 5e46f8e3ac417301a38fb92f
title: Інструмент рекомендацій книг із використанням KNN
challengeType: 10
forumTopicId: 462378
dashedName: book-recommendation-engine-using-knn
---

# --description--

Ви будете <a href="https://colab.research.google.com/github/freeCodeCamp/boilerplate-book-recommendation-engine/blob/master/fcc_book_recommendation_knn.ipynb" target="_blank" rel="noopener noreferrer nofollow">працювати над цим проєктом з Google Colaboratory</a>.

Перейшовши за цим посиланням, створіть копію блокнота у своєму обліковому записі або локально. Як тільки ви завершили проєкт та пройшли тест (доданий до посилання), введіть посилання на свій проєкт. Якщо ви надаєте посилання на Google Colaboratory, переконайтеся, що ви увімкнули режим доступу для «усіх, хто має це посилання».

Ми досі розробляємо інтерактивну складову для навчальної програми з машинного навчання. Поки ви можете переглянути відеозавдання цієї сертифікації. Вам також можуть знадобитися додаткові навчальні ресурси, так само як під час роботи із повноцінним проєктом.

# --instructions--

У цьому завданні ви створите алгоритм книжкових рекомендацій, використовуючи метод **k-найближчих сусідів**.

In this project, you will use the Book-Crossings dataset, which contains 1.1 million ratings (scale of 1-10) of 270,000 books by 90,000 users. The dataset is already imported in the notebook, so no additional download is required.

Use `NearestNeighbors` from `sklearn.neighbors` to develop a model that shows books that are similar to a given book. Алгоритм найближчих сусідів вимірює відстань, щоб визначити «близькість» екземплярів.

Створіть функцію під назвою `get_recommends`, яка приймає назву книжки (з набору даних) як аргумент та повертає список із 5 подібних книжок з відстанями до аргументу книжки.

Цей код:

```py
get_recommends("The Queen of the Damned (Vampire Chronicles (Paperback))")
```

має повернути:

```py
[
  'The Queen of the Damned (Vampire Chronicles (Paperback))',
  [
    ['Catch 22', 0.793983519077301], 
    ['The Witching Hour (Lives of the Mayfair Witches)', 0.7448656558990479], 
    ['Interview with the Vampire', 0.7345068454742432],
    ['The Tale of the Body Thief (Vampire Chronicles (Paperback))', 0.5376338362693787],
    ['The Vampire Lestat (Vampire Chronicles, Book II)', 0.5178412199020386]
  ]
]
```

Зверніть увагу, що дані, які повертає `get_recommends()`, є списком. Першим елементом у списку є назва книжки, передана до функції. Другим елементом списку є список із ще п’яти списків. Кожен з п’яти списків містить рекомендовану книжку та відстань від рекомендованої книжки до книжки, переданої до функції.

Якщо ви побудуєте графік набору даних (необов’язково), ви помітите, що більшість книжок оцінюється рідко. Щоб забезпечити статистичну значущість, видаліть із набору даних користувачів з менш ніж 200 оцінками та книжки з менш ніж 100 оцінками.

Перші три клітинки імпортують бібліотеки, які вам можуть знадобитися, та дані для використання. Кінцева клітинка — для тестування. Напишіть весь свій код між цими клітинками.

# --hints--

Він повинен пройти усі тести Python.

```js

```

# --solutions--

```py
  # Python challenges don't need solutions,
  # because they would need to be tested against a full working project.
  # Please check our contributing guidelines to learn more.
```
