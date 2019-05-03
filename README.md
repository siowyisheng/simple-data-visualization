# The Simple Guide to Data Visualization with Python

_Data Visualization with Python explained simply._

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/siowyisheng/simple-data-visualization/blob/master/LICENSE) ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

## Table of Contents <!-- omit in toc -->

- [What is Data Visualization?](#what-is-data-visualization)
- [What does Data Visualization look like?](#what-does-data-visualization-look-like)
- [What modules need importing?](#what-modules-need-importing)
- [What other setup is required?](#what-other-setup-is-required)
- [How do I show any plot?](#how-do-i-show-any-plot)
- [How do I show a scatter plot?](#how-do-i-show-a-scatter-plot)
- [How do I use seaborn aesthetics?](#how-do-i-use-seaborn-aesthetics)
- [How do I show a line plot?](#how-do-i-show-a-line-plot)
- [How do I customise the colors?](#how-do-i-customise-the-colors)
- [How do I show relationships between more than 2 variables?](#how-do-i-show-relationships-between-more-than-2-variables)
- [How do I show relationships between more than 3 variables?](#how-do-i-show-relationships-between-more-than-3-variables)
- [How do I plot categorical data?](#how-do-i-plot-categorical-data)
- [How do I plot linear data?](#how-do-i-plot-linear-data)
- [How do I order categorical data plots?](#how-do-i-order-categorical-data-plots)
- [How do I show all combinations?](#how-do-i-show-all-combinations)

## What is Data Visualization?

Showing data as pictures to better find and communicate information within it.

## What does Data Visualization look like?

```python
sns.scatterplot(x='total_bill', y='tip', data=data)
plt.show()
```

## What modules need importing?

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

## What other setup is required?

```python
sns.set(style="ticks", color_codes=True)
sns.set(style="darkgrid")
```

## How do I show any plot?

In many environments you will need to use `plt.show()`.

## How do I show a scatter plot?

```python
# option 1
sns.scatterplot(x='total_bill', y='tip', data=data)

# option 2
sns.relplot(x='total_bill', y='tip', data=data)

# show additional dimensions using hue, style and size semantics
sns.scatterplot(x='total_bill', y='tip', hue='smoker', style='smoker', size='size', data=data)

# overriding default size range of glyphs
sns.scatterplot(x='total_bill', y='tip', size='size', sizes=(15, 200), data=data)
```

## How do I use seaborn aesthetics?

```python
# set default styles
sns.set()

# control style
sns.axes_style()

# control style
sns.set_style('darkgrid') # default
sns.set_style('whitegrid')
sns.set_style('dark')
sns.set_style('white')
sns.set_style('ticks')

sns.plotting_context()

sns.set_context('paper')
sns.set_context('notebook')
sns.set_context('talk')
sns.set_context('poster')
```

## How do I show a line plot?

```python
df = pd.DataFrame(dict(time=np.arange(500),
                       value=np.random.randn(500).cumsum()))
g = sns.lineplot(x="time", y="value", data=df)
g.fig.autofmt_xdate()

# show additional dimensions using hue, style and size semantics
sns.lineplot(x="timepoint", y="signal", hue="event", data=data)
plt.show()
```

## How do I customise the colors?

```python
sns.set_palette("husl")

palette = sns.cubehelix_palette(light=.8, n_colors=6)
sns.relplot(x="time", y="firing_rate",
            hue="coherence", style="choice",
            palette=palette,
            kind="line", data=dots)
palette = "ch:.25"
palette = "husl"

"deep"
"muted"
"pastel"
"bright"
"dark"
"colorblind"
"husl"
"Blues"
sns.color_palette("BrBG", 7)
sns.color_palette("RdBu_r", 7)
sns.color_palette("coolwarm", 7)
sns.hls_palette(8, l=.3, s=.8)
```

## How do I show relationships between more than 2 variables?

Show multiple plots and wrap them.

```python
sns.relplot(x="timepoint", y="signal", hue="event", style="event",
            col="subject", col_wrap=5,
            height=3, aspect=.75, linewidth=2.5,
            kind="line", data=fmri.query("region == 'frontal'"))
```

## How do I show relationships between more than 3 variables?

Use the `col` and `row` arguments. Reduce `height` when showing many plots.

```python
sns.relplot(x="total_bill", y="tip", hue="smoker", col="time", data=tips)
```

## How do I plot categorical data?

```python
sns.stripplot(x="day", y="total_bill", data=tips)
sns.swarmplot(x="day", y="total_bill", data=tips)

sns.boxplot(x="day", y="total_bill", data=tips)
sns.boxplot(x="day", y="total_bill", hue="smoker", data=tips)
sns.violinplot(x="day", y="total_bill", data=tips)
sns.barplot(x="day", y="total_bill", data=tips)
sns.countplot(x="day", y="total_bill", data=tips)
```

## How do I plot linear data?

```python
sns.regplot(x="total_bill", y="tip", data=tips)
```

## How do I order categorical data plots?

```python
sns.stripplot(x="smoker", y="tip", order=["No", "Yes"], data=tips)
```

## How do I show all combinations?

```python
import seaborn as sns
sns.set(style="ticks", color_codes=True)
iris = sns.load_dataset("iris")
sns.pairplot(iris, hue="species")

# use a subset of variables
sns.pairplot(iris, hue="species", vars=["sepal_width", "sepal_length"])
```
