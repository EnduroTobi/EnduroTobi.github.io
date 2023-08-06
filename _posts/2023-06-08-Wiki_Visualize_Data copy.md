---
title: Visualize Data
date: 2023-08-06 16:00:00 +0100
categories: [Wiki, Basics]
tags: [python, data visualization, data, data format, charts, graphs, basics]
---

## Introduction to data formats

There are three popular data formats to store data

### Python Lists

```python
['Harry','Ron','Hermione']
```

### CSV data

**C**omma **S**eparated **V**alues - an Excel like spreadsheet

### Pandas Dataframe

```python
df = pd.DataFrame({
    'Character': ['Harry','Draco','Hermione'],
    'House': ['Gryffindor','Slytherin','Gryffindor']
    'Schoolyear': [1,1,1]
})
```

More about dataframes can be read in this [post]({% link _posts/2023-06-18-Wiki_Pandas.md %}).

## Matplotlib

[Matplotlib Cheat Sheets](https://matplotlib.org/cheatsheets/)

[Matplotlib Pyplot Documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html#matplotlib.pyplot.plot)

### Basic Line Plot

```python
plt.plot(x,y)
```

{::comment}

> Insert image of basic line plot

{:/comment}

Pros:

- good for visualizing data against time

#### Shaded Error Line PLots

Create two extra data sets as the boardes of the fill, e.g. the percentage error. Use a list comprehension.

```python
lower_limit = [x * 0.9 for x in y]
upper_limit = [x * 1.1 for x in y]
plt.plot(x,y)
plt.fill_between(x,lower_limit,upper_limit,alpha=0.2)
```

### Bar Plot

How to display two datasets next to each other

> n = 1 # dataset number <br />
> t = 2 # Number of datasets <br />
> d = 5 # Number of sets of bars<br />
> w = 0.8 # Width of each bar (0.8 default)<br />
> x1_values = [t \* element + w \* n for element in range(d)]

### Stacked bar plots

Good use for e.g. an overview of a budget. You can compare the several individual categories as well as the overall budget

plt.bar(x1)
plt.bar(x2,bottom=x1)

For multiple datasets stacked, use the numpy function add().

```python
x3_bottom = np.add(x1,x2)
plt.bar(x3,bottom=x3_bottom)
```

### Histrogram

```python
plt.hist(x,bins=5,density=True,histtype='step',linewidth=2)
```

### Pie Chart

plt.pie([2,45,32,8,51],labels=['A','B','C','D','E'],autopct='%1d%%)

plt.axis('equal')

### Visuals

ax = plt.subplot()

plt.title('Title')

ax.set_xlabel('x-values')

ax.set_xticks(range(len(x)))

ax.set_xticklabels(['A','B','C'])

plt.legend(['A','B'])

### Misc

plt.figure(figsize=(10,8))
plt.savefig('savedfigure.png')

### ways to display measurement error

1. error bars
2. fill between line plot
3. box plot
4. violin plot

## Seaborn

Official Seaborn [docu](https://seaborn.pydata.org) with an [introduction to the supported functions](https://seaborn.pydata.org/tutorial/function_overview.html).

https://seaborn.pydata.org/tutorial/color_palettes.html?highlight=color

Seaborn is based on Matplotlib and offers some good extensions.

1. More appealing plotting style
2. Easier to use with Pandas
3. Easily plots aggregates of a DataFrame

### Bar Plot

sns.barplot(data=df,x='column_1',y='column_2')

activate standard deviation

> ci='sd'

Use different aggregates

> estimator=np.median <br />
> estimator=len

Examples of estimators: np.median, np.mean, len, sum, max, min.

Or use an own function with lambda

estimator=lambda x: sum(xi\*xi for xi in x)

Add nested categorical variable to the plot

> hue='column_3'

### KDE Plot

KDE plots are superior to histograms, because it eliminates the bin size and thus misinterpretations by choosing a non ideal bin size.

sns.kdeplot(dataset1, shade=True)

sns.kdeplot(dataset2, shade=True)

KDE plot receive just on simple dataset. A dataset with multiple columns does not work.

### Box Plot

sns.boxplot(data=df,x='column_1','column_2')

### Violin Plot

sns.violinplot(data=df,x='column_1','column_2')

### Shapes of dataset distribution

1. discrete
2. skewed (shifted towards one value)
3. normally
4. bimodal (two peaks)

### Styling

Built in style themes

> sns.set_style("darkgrid")

darkgrid, whitegrid, dark, white, and ticks

Remove spines (top and right)

> sns.despine()

or for individual spines

> sns.despine(left=True, bottom=True)

Scaling the plot

> sns.set_context("paper")

paper, notebook, talk, and poster

set the scale, font size and line width

> sns.set_context("poster", font_scale = .5, rc={"grid.linewidth": 0.6})

rc stand for run coomand and it allows to change all attributes that can easily be printed by

> sns.plotting_context()

Coloring

Use color palettes

Save a palette to a variable:

> sns.set_palette("bright")

To visualize the colorpalette use:

> sns.palplot(sns.color_palette("bright"))

There are following standard palettes

deep, muted, pastel, bright, dark, and colorblind.

It is also possible to use Color Brewer (http://colorbrewer2.org)

> custom_palette = sns.color_palette("Paired", 9)
> Use Seaborn styling for Matplotlib plots

Use Qualitative Palettes for Categorical Datasets
(e.g. Harry, Ron, Hermoine)

Sequential Palettes go from a light color to a darker color. This is useful for variables in an ordered list (e.g Points scored in Quiddich)

https://seaborn.pydata.org/tutorial/color_palettes.html?highlight=color

Use Diverging Palettes are good for indicating both exremes, e.g. Temperature

> sns.set()
