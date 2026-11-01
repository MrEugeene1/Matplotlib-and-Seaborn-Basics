# Data Visualisation with Matplotlib & Seaborn

A beginner-friendly, hands-on course in data visualisation with Python. It goes from "what is data?" to reading heatmaps and pair plots. Every concept is explained in plain language, with examples from everyday life (sleep, steps, daily spending in €), and every chart comes with a guide on how to **read it** and how to **explain it** to someone else.

No prior knowledge of statistics or plotting is assumed.

---

## Contents

| Notebook | Description |
|---|---|
| [`6. Matplotlib and Seaborn - Super Simple Guide.ipynb`](6.%20Matplotlib%20and%20Seaborn%20-%20Super%20Simple%20Guide.ipynb) | **Main course.** 14 lessons on a synthetic "daily life" dataset, each with a code walkthrough, a guide to reading the chart, exercises and a one-line takeaway. It ends with a framework for explaining charts, a glossary and a 14-day practice plan. |
| [`5. Matplotlib and Seaborn.ipynb`](5.%20Matplotlib%20and%20Seaborn.ipynb) | **Reference notebook.** Classic examples (line, stacked bar, density plots, iris pair plot) with plain-language explanations added under each cell, plus modern replacements for deprecated Seaborn APIs. |
| `my_water_chart.png` | Example output written by Lesson 6 (saving a figure). |

**Recommended order:** start with notebook 6, then use notebook 5 as a second set of examples.

---

## What you will learn

### Foundations
- What data, charts, DataFrames, Matplotlib and Seaborn are, and how they relate
- Generating **synthetic data** with NumPy (`normal`, `gamma`, `integers`) and choosing the right distribution for the data
- **Random seeds** and reproducibility
- Matplotlib's object model: `Figure` vs `Axes`

### Charts covered

| # | Chart | Library | Question it answers |
|---|---|---|---|
| 1 | Line chart | Matplotlib | How does it change over time? |
| 2 | Bar / horizontal bar (`barh`) | Matplotlib | Which group is bigger? |
| 3 | Histogram | Matplotlib | How often does each value occur? |
| 4 | Scatter plot | Matplotlib | Do two variables move together? |
| 5 | Subplots grid | Matplotlib | Several views on one figure |
| 6 | Saving figures | Matplotlib | Exporting to PNG |
| 7 | `lineplot` | Seaborn | Trends from a DataFrame |
| 8 | `barplot` + error bars | Seaborn | Group averages and their uncertainty (95% CI, bootstrapping) |
| 9 | `histplot` + KDE | Seaborn | Distribution shape, bins vs kernel density, bandwidth |
| 10 | `boxplot` | Seaborn | Median, IQR, whiskers and outliers per group |
| 11 | `scatterplot` with `hue` | Seaborn | Relationships split by category |
| 12 | `regplot` | Seaborn | Linear trend, slope and confidence band |
| 13 | `heatmap` of correlations | Seaborn | Which variables are correlated, and which correlations may be chance |
| 14 | `pairplot` | Seaborn | Every pairwise relationship at once (exploratory data analysis) |

### Thinking like a data scientist
- Reading a chart in a fixed order (e.g. median → spread → outliers)
- **Correlation is not causation**
- Spurious correlations in small samples
- Non-linear relationships that a correlation coefficient misses
- Not extrapolating beyond the data
- A 4-step method for presenting any chart: **question → how to read it → what I see → what it means**

---

## About the data

The main notebook uses a **synthetic dataset** of 28 days (sleep hours, steps, glasses of water, mood and money spent in €), generated with a fixed seed (`np.random.default_rng(7)`). Every reader therefore sees exactly the same numbers and charts.

One relationship is planted on purpose: **mood rises about 1.5 points per extra hour of sleep**. All other variables are independent. This makes the lessons a controlled experiment. Learners can check that the scatter plot, regression line (estimated slope ≈ 1.36), heatmap (r ≈ 0.83) and pair plot all recover the real signal, and see that the other "correlations" in the heatmap are produced by chance.

Notebook 5 uses unseeded random data and the public **iris** dataset (loaded with `seaborn.load_dataset`, which needs an internet connection the first time).

---

## Getting started

### Requirements
- Python 3.10+
- The packages in [`requirements.txt`](requirements.txt): NumPy, pandas, Matplotlib, Seaborn ≥ 0.13.2, Jupyter

Tested with Python 3.14, NumPy 2.5, pandas 3.0, Matplotlib 3.11 and Seaborn 0.13.2.

### Installation

```bash
# optional: create and activate a virtual environment
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS / Linux
source .venv/bin/activate

pip install -r requirements.txt
```

### Running the notebooks

```bash
jupyter notebook
```

Or open the folder in **VS Code** with the Python and Jupyter extensions installed.

Use **Run All** so the cells run top to bottom. Later cells depend on the data and style settings defined earlier. If charts suddenly look unstyled (no grid lines), a setup cell was skipped.

---

## Deprecated Seaborn APIs

Notebook 5 keeps the original code for reference and adds modern equivalents right below it:

| Deprecated | Modern replacement |
|---|---|
| `sns.kdeplot(x, shade=True)` | `sns.kdeplot(x, fill=True)` |
| `sns.distplot(x, hist=False)` | `sns.kdeplot(x)` |
| `sns.distplot(x)` | `sns.histplot(x, kde=True)` |
| `sns.set()` | `sns.set_theme()` |

---

## 14-day practice plan

The main notebook ends with a two-week plan. Each day takes 20–40 minutes, and learners collect and chart **their own** daily-life data:

| Days | Focus |
|---|---|
| 1 – 5 | Matplotlib basics: line, bar, histogram, scatter, subplots and saving |
| 6 – 7 | Explaining charts to someone else, then review |
| 8 – 12 | Seaborn: line, bar, histogram + KDE, box plot, `hue`, heatmap |
| 13 | A real dataset (`tips`) |
| 14 | Mini project: one question, two weeks of personal data, three charts, three sentences |

---

## Project structure

```
MatplotlibandSeaborn_Trials/
├── 5. Matplotlib and Seaborn.ipynb                      # reference examples + explanations
├── 6. Matplotlib and Seaborn - Super Simple Guide.ipynb # main course
├── my_water_chart.png                                   # example saved figure (Lesson 6)
├── requirements.txt
└── README.md
```

---

## Further reading

- Matplotlib documentation: <https://matplotlib.org/stable/>
- Seaborn tutorial: <https://seaborn.pydata.org/tutorial.html>
- pandas getting started: <https://pandas.pydata.org/docs/getting_started/>
