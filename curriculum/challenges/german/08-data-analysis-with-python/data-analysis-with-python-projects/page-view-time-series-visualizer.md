---
id: 5e46f802ac417301a38fb92b
title: Page View Time Series Visualizer
challengeType: 10
forumTopicId: 462369
dashedName: page-view-time-series-visualizer
---

# --description--

You will be <a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-page-view-time-series-visualizer" target="_blank" rel="noopener noreferrer nofollow">working on this project with our Gitpod starter code</a>.

Wir sind noch dabei, den interaktiven Teil des Python-Lehrplans zu entwickeln. Zurzeit kannst du dir lediglich einige Videos auf unserem YouTube-Channel für freeCodeCamp.org ansehen – diese bringen dir alles bei, was du wissen musst, um dieses Projekt abzuschließen:

- <a href="https://www.freecodecamp.org/news/python-for-everybody/" target="_blank" rel="noopener noreferrer nofollow">Python for Everybody Video Course</a> (14 hours)

- <a href="https://www.freecodecamp.org/news/how-to-analyze-data-with-python-pandas/" target="_blank" rel="noopener noreferrer nofollow">How to Analyze Data with Python Pandas</a> (10 hours)

# --instructions--

Für dieses Projekt visualisierst du die Daten der Zeitserie mit Hilfe eines Liniendiagramms, Balkendiagramms und eines Boxplots. Du wirst Pandas, Matplotlib und Seaborn verwenden, um einen Datensatz zu visualisieren, der die Anzahl der täglichen FreeCodeCamp Seitenaufrufe vom 2016-05-09 bis 2019-12-03 enthält. Die Datenvisualisierungen wird dir helfen, die Muster bei Besuchen zu verstehen sowie das jährliche und monatliche Wachstum zu ermitteln.

Benutze die Daten, um folgende Aufgaben abzuschließen:

- Use Pandas to import the data from "fcc-forum-pageviews.csv". Set the index to the `date` column.
- Bereinige die Daten, indem du Tage filterst, an denen die Seitenaufrufe in den oberen 2.5% oder unteren 2.5% des Datensatzes waren.
- Erstelle eine `draw_line_plot` Funktion, die Matplotlib verwendet, um ein Liniendiagramm, ähnlich wie "examples/Figure_1.png", zu zeichnen. Der Titel sollte `Daily freeCodeCamp Forum Page Views 5/2016-12/2019` sein. Die Beschriftung der x-Achse sollte `Date` sein und die Beschriftung auf der y-Achse sollte `Page Views` lauten.
- Erstelle eine `draw_bar_plot`-Funktion, die ein Balkendiagramm, ähnlich wie "examples/Figure_2.png", verwendet. Es sollte die durchschnittlichen täglichen Seitenaufrufe pro Monat nach Jahr anzeigen. Die Legende sollte Monatsbeschriftungen anzeigen und `Months` als Titel haben. Beim Diagramm sollte die Beschriftung der x-Achse `Years` lauten und die Beschriftung der y-Achse sollte `Average Page Views` lauten.
- Erstelle eine `draw_box_plot`-Funktion, die Seaborn verwendet, um zwei angrenzende Boxplots, ähnlich wie "examples/Figure_3.png", zu zeichnen. Diese Boxplots sollten zeigen, wie die Werte innerhalb eines bestimmten Jahres oder Monats verteilt sind und wie sie im Laufe der Zeit abschneiden. Der Titel des ersten Diagramms sollte `Year-wise Box Plot (Trend)` lauten und der des zweiten Diagramms sollte `Month-wise Box Plot (Seasonality)` lauten. Stelle sicher, dass die Monatsbeschriftungen unten bei `Jan` starten und, dass die x- und y-Achse korrekt gekennzeichnet sind. Der Boilerplate-Code enthält auch Befehle zur Datenvorbereitung.

For each chart, make sure to use a copy of the data frame.

Die Boilerplate enthält auch Befehle zum Speichern und Zurückgeben des Bildes.

## Development

Schreibe deinen Code in `time_series_visualizer.py`. Für die Entwicklung kannst du `main.py` verwenden, um deinen Code zu testen.

## Prüfung

Die Einheitstests für dieses Projekt befinden sich in `test_module.py`. Wir haben die Tests von `test_module.py` nach `main.py` importiert, um Ihnen die Arbeit zu erleichtern.

## Einreichung

Kopiere die URL deines Projekts und sende es an freeCodeCamp.

# --hints--

Es sollte alle Python-Tests bestehen.

```js

```

# --solutions--

```py
  # Python challenges don't need solutions,
  # because they would need to be tested against a full working project.
  # Please check our contributing guidelines to learn more.
```
