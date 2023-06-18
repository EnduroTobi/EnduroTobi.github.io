---
title: Visualize Data
date: 2023-06-08 19:50:00 +0100
categories: [Wiki, Basics]
tags: [python, data visualization, data, data format, charts, graphs, basics]
---

## Introduction to data formats

There are three popular data formats to store data

**Python List**

: ```python
['Harry','Ron','Hermione']

```

**CSV data**
: **C**omma **S**eparated **V**alues - an Excel like spreadsheet

**Pandas Dataframe**
: more about dataframes
```

## Data Visulazing Libraries

### Matplotlib

> Insert Matplotlib Cheat Sheet (links?)

[Matplotlib Pyplot Documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html#matplotlib.pyplot.plot)

### Seaborn

> Insert Seaborn Cheat Sheet (links?)

## Tips for data visualization

### Basic Line Plot

```python
plt.plot(x,y)
```

> Insert image of basic line plot

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

#### stacked bar plots

Good use for e.g. an overview of a budget. You can compare the several individual categories as well as the overall budget

plt.bar(x1)
plt.bar(x2,bottom=x1)

For multiple datasets stacked, use the numpy function add().

```python
x3_bottom = np.add(x1,x2)
plt.bar(x3,bottom=x3_bottom)
```

#### Histrogram

```python
plt.hist(x,bins=5,density=True,histtype='step',linewidth=2)
```

#### Pie Chart

plt.pie([2,45,32,8,51],labels=['A','B','C','D','E'],autopct='%1d%%)

plt.axis('equal')

#### Visuals

ax = plt.subplot()

plt.title('Title')

ax.set_xlabel('x-values')

ax.set_xticks(range(len(x)))

ax.set_xticklabels(['A','B','C'])

plt.legend(['A','B'])

#### Misc

plt.figure(figsize=(10,8))
plt.savefig('savedfigure.png')

### ways to display measurement error

1. error bars
2. fill between line plot
3. box plot
4. violin plot
