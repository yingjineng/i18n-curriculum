---
id: 5e46f7f8ac417301a38fb92a
title: Visualizzatore di Dati Medici
challengeType: 10
forumTopicId: 462368
dashedName: medical-data-visualizer
---

# --description--

You will be <a href="https://gitpod.io/?autostart=true#https://github.com/freeCodeCamp/boilerplate-medical-data-visualizer/" target="_blank" rel="noopener noreferrer nofollow">working on this project with our Gitpod starter code</a>.

Stiamo ancora sviluppando la parte didattica interattiva del curriculum di Python. Per ora, ecco alcuni video sul canale YouTube di freeCodeCamp.org che ti insegneranno tutto quello che devi sapere per completare questo progetto:

- <a href="https://www.freecodecamp.org/news/python-for-everybody/" target="_blank" rel="noopener noreferrer nofollow">Python for Everybody Video Course</a> (14 hours)

- <a href="https://www.freecodecamp.org/news/how-to-analyze-data-with-python-pandas/" target="_blank" rel="noopener noreferrer nofollow"> Come analizzare i dati con Python Pandas </a>(10 ore)

# --instructions--

In this project, you will visualize and make calculations from medical examination data using `matplotlib`, `seaborn`, and `pandas`. I valori dell’insieme di dati sono stati raccolti durante una serie di esami medici.

## Data description

Le righe nel set di dati rappresentano i pazienti e le colonne rappresentano informazioni come le misurazioni del corpo, i risultati di vari esami del sangue e lo stile di vita. Userai il set di dati per esplorare il rapporto tra malattie cardiache, misurazioni del corpo, marcatori del sangue e stile di vita.

Nome del file: medical_examination.csv

|                    Feature                    | Tipo Di Variabile |   Variabile   |                              Tipo Di Valore                              |
|:---------------------------------------------:|:-----------------:|:-------------:|:------------------------------------------------------------------------:|
|                      Age                      | Objective Feature |     `age`     |                                int (days)                                |
|                    Height                     |  Dato oggettivo   |   `height`    |                                 int (cm)                                 |
|                    Weight                     |  Dato oggettivo   |   `weight`    |                                float (kg)                                |
|                    Gender                     |  Dato oggettivo   |   `gender`    |                           codice di categoria                            |
|            Systolic blood pressure            |   Dato da esami   |    `ap_hi`    |                                   int                                    |
|           Diastolic blood pressure            |   Dato da esami   |    `ap_lo`    |                                   int                                    |
|                  Cholesterol                  |   Dato da esami   | `cholesterol` | 1: normale, 2: al di sopra del normale, 3: molto al di sopra del normale |
|                    Glucose                    |   Dato da esami   |    `gluc`     | 1: normale, 2: al di sopra del normale, 3: molto al di sopra del normale |
|                    Smoking                    |  Dato soggettivo  |    `smoke`    |                                 binario                                  |
|                Alcohol intake                 |  Dato soggettivo  |    `alco`     |                                 binario                                  |
|               Physical activity               |  Dato soggettivo  |   `active`    |                                 binario                                  |
| Presence or absence of cardiovascular disease | Variabile target  |   `cardio`    |                                 binario                                  |


## Instructions

Create a chart similar to `examples/Figure_1.png`, where we show the counts of good and bad outcomes for the `cholesterol`, `gluc`, `alco`, `active`, and `smoke` variables for patients with `cardio=1` and `cardio=0` in different panels.

By each number in the `medical_data_visualizer.py` file, add the code from the associated instruction number below.

1. Import the data from `medical_examination.csv` and assign it to the `df` variable.
2. Add an `overweight` column to the data. To determine if a person is overweight, first calculate their BMI by dividing their weight in kilograms by the square of their height in meters. If that value is > 25 then the person is overweight. Use the value `0` for NOT overweight and the value `1` for overweight.
3. Normalize data by making `0` always good and `1` always bad. If the value of `cholesterol` or `gluc` is 1, set the value to `0`. If the value is more than `1`, set the value to `1`.
4. Draw the Categorical Plot in the `draw_cat_plot` function.
5. Create a DataFrame for the cat plot using `pd.melt` with values from `cholesterol`, `gluc`, `smoke`, `alco`, `active`, and `overweight` in the `df_cat` variable.
6. Group and reformat the data in `df_cat` to split it by `cardio`. Show the counts of each feature. You will have to rename one of the columns for the `catplot` to work correctly.
7. Convert the data into `long` format and create a chart that shows the value counts of the categorical features using the following method provided by the seaborn library import: `sns.catplot()`.
8. Get the figure for the output and store it in the `fig` variable.
9. Do not modify the next two lines.
10. Draw the Heat Map in the `draw_heat_map` function.
11. Clean the data in the `df_heat` variable by filtering out the following patient segments that represent incorrect data:
    - diastolic pressure is higher than systolic (Keep the correct data with `(df['ap_lo'] <= df['ap_hi'])`)
    - height is less than the 2.5th percentile (Keep the correct data with `(df['height'] >= df['height'].quantile(0.025))`)
    - height is more than the 97.5th percentile
    - weight is less than the 2.5th percentile
    - weight is more than the 97.5th percentile
12. Calculate the correlation matrix and store it in the `corr` variable.
13. Generate a mask for the upper triangle and store it in the `mask` variable.
14. Set up the `matplotlib` figure.
15. Plot the correlation matrix using the method provided by the `seaborn` library import: `sns.heatmap()`.
16. Do not modify the next two lines.

## Sviluppo

Write your code in `medical_data_visualizer.py`. For development, you can use `main.py` to test your code.

## Test

The unit tests for this project are in `test_module.py`. Abbiamo importato i test da `test_module.py` in `main.py` per tua convenienza.

## Invio

Copia l'URL del tuo progetto e consegnalo nell'input qua sotto.

# --hints--

Dovrebbe superare tutti i test Python.

```js

```

# --solutions--

```py
  # Python challenges don't need solutions,
  # because they would need to be tested against a full working project.
  # Please check our contributing guidelines to learn more.
```
