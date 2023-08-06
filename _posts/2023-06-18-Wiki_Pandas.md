---
title: Pandas Basics
date: 2023-06-18 12:50:00 +0100
categories: [Wiki, Basics]
tags: [python, pandas, data, basics]
---

## Dataframes

```python
import pandas as pd
df = pd.DataFrame({
    'Character': ['Harry','Draco','Hermione'],
    'House': ['Gryffindor','Slytherin','Gryffindor']
    'Schoolyear': [1,1,1]
})
```

create a new DataFrame out of an old one

df_new = df_old[['column_1','column_2']].copy()

or

df_new = df_old[['column_1','column_2']]

### Set column names

```python
df = pd.DataFrame([
    ['Harry','Draco','Hermione'],
    ['Gryffindor','Slytherin','Gryffindor']
    [1,1,1],
    ],
    columns=[ 'Character','House','Schoolyear']
)
```

### Import CSV

```python
df = pd.read_csv('Harry_Potter_Stats.csv')
#or
df.to_csv('Harry_Potter_Stats.csv')
```

### Selecting columns

1. Option
   students = df['Character']
2. Option
   students = df.Character
   (This works only with a columnname without spaces and starting with a letter)

### selcting multiple columns

students = df[['Character','House']]

### Selecting Rows

df.iloc[2]

You can also select the rows like you would with lists
df.iloc[2:4]

df.iloc[:2]

df.iloc[-2:]

Select with logic

gryffindor_students = df[df.House == 'Gryffindor']

or

gryffindor_students = df[(df.House == 'Gryffindor') & (df.Schoolyear > 3)]

or

main_character = df[df.Character.isin(['Harry','Hermione'])]

### Adding columns

df['Quidditch Player'] = ['Yes','Yes','No']

or one value for all rows

df['Muggle'] = 'No'

or perform calculations

df['Final mark in Magic Portion'] = (df['Test 1'] + df['Test 2'] + df['Test 3']) / 3

### Renaming columns

df.columns = ['column_1','column_2','column_3']

df.rename(columns={'Column 1': 'column_1'}, inplace=True)

inplace=True

will add the changes to the existing dataframe. With False, a new dataframe will be created.

### Useful stuff

```python
print(df.head())
```

```python
print(df.info())
```

Reset the index of Sub-Dataframes

```python
df.reset_index(drop=True,inplace=True)
```

```python

```

Apply functions to a column

```python
df['Column 1'] = df['column 2'].apply(function)
```

Get a random sample

```python
df.sample()
# or use it for one specific column
df['column_1'].sample()
```
