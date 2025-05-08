---
title: Starting With Data
teaching: 30
exercises: 30
---

::::::::::::::::::::::::::::::::::::::: objectives

- Navigate the workshop directory and download a dataset.
- Explain what a library is and what libraries are used for.
- Describe what the Python Data Analysis Library (Pandas) is.
- Load the Python Data Analysis Library (Pandas).
- Read tabular data into Python using Pandas.
- Describe what a DataFrame is in Python.
- Access and summarize data stored in a DataFrame.
- Define indexing as it relates to data structures.
- Perform basic mathematical operations and summary statistics on data in a Pandas DataFrame.
- Create simple plots.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How can I import data in Python?
- What is Pandas?
- Why should I use Pandas to work with data?

::::::::::::::::::::::::::::::::::::::::::::::::::

## Working With Pandas DataFrames in Python

We can automate the process of performing data manipulations in Python. It's efficient to spend time
building the code to perform these tasks because once it's built, we can use it
over and over on different datasets that use a similar format. This makes our
data manipulation processes reproducible. We can also share our code with
colleagues and they can replicate the same analysis starting with the same original data.

#### Starting in the same spot

To help the lesson run smoothly, let's ensure everyone is in the same directory.
This should help us avoid path and file name issues. At this time please
navigate to the workshop directory. We are using Jupyter Notebook so be sure
that you start your notebook in the workshop directory.

#### Our Data

For this lesson, we will be using the Tree data from the municipality of Amsterdam. 
The data originates from the [data portal of the municipality](https://api.data.amsterdam.nl/v1/bomen/stamgegevens/) 
and has been downloaded, translated and modified for education purposes in November 2024 (see [this reposity](https://github.com/Morrizzzzz/Geodatabases_UNIGIS)
for the modifications that have been made). 

Now download the data here: [trees_nov_2024.csv]() and store it is your data folder. 

The dataset is stored as a `.csv` file: each row holds information for a
single tree, and the columns represent:


| Column              | Description                          | 
| --------------------| ------------------------------------ |
| id                  | Unique id for the tree               | 
| year_planted        | year in which the tree is planted    | 
| botanical_name      | the botanical name                   | 
| name                | name of the tree (Dutch)             | 
| diameter_tree_trunk | class of diameter tree trunk         | 
| height_of_tree      | class of tree height                 | 
| object_type         | Type of tree (what humans did )      | 
| X                   | x coordinate                         | 
| Y                   | y coordinate                         | 

The first few rows of our first file look like this (when you open it for instance using a text editor like [Notepad++](https://notepad-plus-plus.org/) ) ):

```output
id,year_planted,botanical_name,name,diameter_tree_trunk,height_of_tree,object_type,X,Y
919933,1948.0,Tilia americana,Linde (Tilia),,e. 15 to 18 ,non free growing tree,4.904670904743209,52.33981350119924
919934,1978.0,Ulmus hollandica 'Vegeta',Iep (Ulmus),,c. 9 to 12 m.,non free growing tree,4.902687460773278,52.34009448996643
919935,1990.0,Fraxinus excelsior 'Westhof's Glorie',Es (Fraxinus),0.2 to 0.3 m.,c. 9 to 12 m.,non free growing tree,4.85520763084145,52.33198441265341
919936,2002.0,Ulmus glabra 'Lutescens',Iep (Ulmus),,b. 6 to 9 m.,non free growing tree,4.903684257065518,52.34883076374636
919937,1985.0,Quercus robur,Eik (Quercus),,b. 6 to 9 m.,non free growing tree,4.875886424004287,52.34105572150886
```

***

### About Libraries

A library in Python contains a set of tools (called functions) that perform
tasks on our data. Importing a library is like getting a piece of lab equipment
out of a storage locker and setting it up on the bench for use in a project.
Once a library is set up, it can be used or called to perform the task(s)
it was built to do.

### Pandas in Python

One of the best options for working with tabular data in Python is to use the
[Python Data Analysis Library][pandas] (a.k.a. Pandas). The
Pandas library provides data structures, produces high quality plots with
[matplotlib] and integrates nicely with other libraries
that use [NumPy][numpy] (which is another Python library) arrays.

Python doesn't load all of the libraries available to it by default. We have to
add an `import` statement to our code in order to use library functions. To import
a library, we use the syntax `import libraryName`. If we want to give the
library a nickname to shorten the command, we can add `as nickNameHere`.  An
example of importing the pandas library using the common nickname `pd` is below.

```python
import pandas as pd
```

Each time we call a function that's in a library, we use the syntax
`LibraryName.FunctionName`. Adding the library name with a `.` before the
function name tells Python where to find the function. In the example above, we
have imported Pandas as `pd`. This means we don't have to type out `pandas` each
time we call a Pandas function.

## Reading CSV Data Using Pandas

We will begin by locating and reading our tree data which have available in CSV format. CSV stands for
Comma-Separated Values and is a common way to store formatted data. Other symbols may also be used, so
you might see tab-separated, colon-separated or space separated files. pandas can work with each of these
types of separators, as it allows you to specify the appropriate separator for your data.
CSV files (and other -separated value file types) make it easy to share data, and can be imported and exported
from many applications, including Microsoft Excel. For more details on CSV
files, see the [Data Organisation in Spreadsheets][spreadsheet-lesson5] lesson.
To read the csv we use Pandas' `read_csv` function to pull the file directly into a [DataFrame][pd-dataframe].

### So What's a DataFrame?

A DataFrame is a 2-dimensional data structure that can store data of different
types (including strings, numbers, categories and more)
in columns. It is similar to a spreadsheet or an SQL table or the `data.frame` in
R. A DataFrame always has an index (0-based). An index refers to the position of
an element in the data structure.

```python
# Note that pd.read_csv is used because we imported pandas as pd
pd.read_csv("data/trees_nov_2024.csv")
```

The above command yields the **output** below:

```output
id  year_planted                         botanical_name  \
0        919933        1948.0                        Tilia americana   
1        919934        1978.0              Ulmus hollandica 'Vegeta'   
2        919935        1990.0  Fraxinus excelsior 'Westhof's Glorie'   
3        919936        2002.0               Ulmus glabra 'Lutescens'   
4        919937        1985.0                          Quercus robur   
...         ...           ...                                    ...   
315419  5481144           NaN                 Elaeagnus angustifolia   
315420  5481147           NaN                       Pinus sylvestris   
315421  5481149        2011.0                       Pinus sylvestris   
315422  5481151        2011.0                       Pinus sylvestris   
315423  5481153        2011.0                            Pinus nigra   

                 name diameter_tree_trunk height_of_tree  \
0       Linde (Tilia)                 NaN   e. 15 to 18    
1         Iep (Ulmus)                 NaN  c. 9 to 12 m.   
2       Es (Fraxinus)       0.2 to 0.3 m.  c. 9 to 12 m.   
3         Iep (Ulmus)                 NaN   b. 6 to 9 m.   
4       Eik (Quercus)                 NaN   b. 6 to 9 m.   
...               ...                 ...            ...   
315419      Elaeagnus                 NaN     a. to 6 m.   
315420          Pinus                 NaN   b. 6 to 9 m.   
315421          Pinus                 NaN     a. to 6 m.   
315422          Pinus                 NaN     a. to 6 m.   
315423          Pinus                 NaN     a. to 6 m.   

                  object_type                                      geometry  \
0       non free growing tree   POINT (4.904670904743209 52.33981350119924)   
1       non free growing tree   POINT (4.902687460773278 52.34009448996643)   
2       non free growing tree    POINT (4.85520763084145 52.33198441265341)   
3       non free growing tree   POINT (4.903684257065518 52.34883076374636)   
4       non free growing tree   POINT (4.875886424004287 52.34105572150886)   
...                       ...                                           ...   
315419                    NaN   POINT (5.001934493840532 52.34663387012799)   
315420                    NaN   POINT (5.001901933117327 52.34663576448863)   
315421                    NaN    POINT (5.00188831913458 52.34664887177107)   
315422                    NaN   POINT (5.001831722779572 52.34664652209999)   
315423                    NaN  POINT (5.001842162883901 52.346668676136744)   

               X          Y  
0       4.904671  52.339814  
1       4.902687  52.340094  
2       4.855208  52.331984  
3       4.903684  52.348831  
4       4.875886  52.341056  
...          ...        ...  
315419  5.001934  52.346634  
315420  5.001902  52.346636  
315421  5.001888  52.346649  
315422  5.001832  52.346647  
315423  5.001842  52.346669  

[315424 rows x 10 columns]
```

We can see that there were 315424 rows parsed. Each row has 9
columns. The first column is the index of the DataFrame. The index is used to
identify the position of the data, but it is not an actual column of the DataFrame.
It looks like the `read_csv` function in Pandas  read our file properly. However,
we haven't saved any data to memory so we can work with it. We need to assign the
DataFrame to a variable. Remember that a variable is a name for a value, such as `x`,
or  `data`. We can create a new  object with a variable name by assigning a value to it using `=`.

Let's call the imported survey data `trees_nov_24`:

```python
trees_nov_24_df = pd.read_csv("data/trees_nov_24.csv")
```

Note that Python does not produce any output on the screen  when you assign the imported DataFrame to a variable.
We can view the value of the `trees_nov_24_df`
object by typing its name into the Python command prompt.

```python
trees_nov_24_df
```

which prints contents like above.

Note: if the output is too wide to print on your narrow terminal window, you may see something
slightly different as the large set of data scrolls past. Don't worry: all the data is there! You can confirm this by scrolling upwards, or by
looking at the `[# of rows x # of columns]` block at the end of the output.

You can also use `trees_nov_24_df.head()` to view only the first few rows of the dataset in an output
that is easier to fit in one window. After doing this, you can see that pandas has neatly formatted
the data to fit our screen:

```python
trees_nov_24_df.head() # The head() method displays the first several lines of a file. It
                  # is discussed below.
```

```output
id	year_planted	botanical_name	name	diameter_tree_trunk	height_of_tree	object_type	X	Y
0	919933	1948.0	Tilia americana	Linde (Tilia)	NaN	e. 15 to 18	non free growing tree	4.904671	52.339814
1	919934	1978.0	Ulmus hollandica 'Vegeta'	Iep (Ulmus)	NaN	c. 9 to 12 m.	non free growing tree	4.902687	52.340094
2	919935	1990.0	Fraxinus excelsior 'Westhof's Glorie'	Es (Fraxinus)	0.2 to 0.3 m.	c. 9 to 12 m.	non free growing tree	4.855208	52.331984
3	919936	2002.0	Ulmus glabra 'Lutescens'	Iep (Ulmus)	NaN	b. 6 to 9 m.	non free growing tree	4.903684	52.348831
4	919937	1985.0	Quercus robur	Eik (Quercus)	NaN	b. 6 to 9 m.	non free growing tree	4.875886	52.341056


```

### Exploring Our Tree Data

Again, we can use the `type` function to see what kind of thing `trees_nov_24_df` is:

```python
type(trees_nov_24_df)
```

```output
<class 'pandas.core.frame.DataFrame'>
```

As expected, it's a DataFrame (or, to use the full name that Python uses to refer
to it internally, a `pandas.core.frame.DataFrame`).

What kind of things does `trees_nov_24_df` contain? DataFrames have an attribute
called `dtypes` that answers this:

```python
trees_nov_24_df.dtypes
```

```output
id                       int64
year_planted           float64
botanical_name          object
name                    object
diameter_tree_trunk     object
height_of_tree          object
object_type             object
X                      float64
Y                      float64
dtype: object
```

All the values in a single column have the same type. For example, values in the year_planted
column have type `float64`, which is a kind of foating point number. The `object` type for for instance botanical_name doesn't have a very helpful name, but in
this case it represents strings (such as 'Ulmus hollandica 'Vegeta'' or 'Quercus robur').

We'll talk a bit more about what the different formats mean in a different lesson.

#### Useful Ways to View DataFrame Objects in Python

There are many ways to summarize and access the data stored in DataFrames,
using **attributes** and **methods** provided by the DataFrame object.

Attributes are features of an object. For example, the `shape` attribute will output
the size (the number of rows and columns) of an object. To access an attribute,
use the DataFrame object name followed by the attribute name `df_object.attribute`.
For example, using the DataFrame `trees_nov_24_df` and attribute `columns`, an index
of all the column names in the DataFrame can be accessed with `trees_nov_24_df.columns`.

Methods are like functions, but they only work on particular kinds of objects. As
an example, **the `head()` method** works on DataFrames. Methods are called in a
similar fashion to attributes, using the syntax `df_object.method()`. Using
`trees_nov_24_df.head()` gets the first few rows in the DataFrame `trees_nov_24_df`
using the `head()` method. With a method, we can supply extra information
in the parentheses to control behaviour.

Let's look at the data using these.

:::::::::::::::::::::::::::::::::::::::  challenge

### Challenge - DataFrames

Using our DataFrame `trees_nov_24_df`, try out the **attributes** \& **methods** below to see
what they return.

1. `trees_nov_24_df.columns`

2. `trees_nov_24_df.shape` Take note of the output of `shape` - what format does it
  return the shape of the DataFrame in?
  
  HINT: [More on tuples, here][python-datastructures].

3. `trees_nov_24_df.head()` Also, what does `trees_nov_24_df.head(15)` do?

4. `trees_nov_24_df.tail()`
  
::::::::::::::::::::::: solution

1. `trees_nov_24_df.columns` provides the names of the columns in the DataFrame.
2. `trees_nov_24_df.shape` provides the dimensions of the DataFrame as a tuple 
   in `(r,c)` format,
   where `r` is the number of rows and `c` the number of columns.
3. `trees_nov_24_df.head()` returns the first 5 lines of the DataFrame, 
   annotated with column and row labels.
   Adding an integer as an argument to the function 
   specifies the number of lines to display from the top of the DataFrame, 
   e.g. `trees_nov_24_df.head(15)` will return the first 15 lines.
4. `trees_nov_24_df.tail()` will display the last 5 lines, 
   and behaves similarly to the `head()` method.

::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::: instructor

## Recapping object (im)mutability

Working through solutions to the challenge above
can provide a good opportunity to recap about mutability and immutability
of different objects.
Show that the DataFrame index
( the `columns` attribute) is immutable, e.g. 
`trees_nov_24_df.columns[3]  = "dutch_name"` returns a `TypeError`.

Adapting the name is done with the `rename` function:

```python
trees_nov_24_df.rename(columns={"name": "dutch_name"})`)
```

::::::::::::::::::::::::::::::::::

### Calculating Statistics From Data In A Pandas DataFrame

We've read our data into Python. Next, let's perform some quick summary
statistics to learn more about the data that we're working with. We might want
to know how many animals were collected in each site, or how many of each
species were caught. We can perform summary stats quickly using groups. But
first we need to figure out what we want to group by.

Let's begin by exploring our data:

```python
# Look at the column names
trees_nov_24_df.columns
```

which **returns**:

```output
Index(['id', 'year_planted', 'botanical_name', 'name', 'diameter_tree_trunk',
       'height_of_tree', 'object_type', 'X', 'Y'],
      dtype='object')
```

Let's get a list of all the species. The `pd.unique` function tells us all of
the unique values in the `height_of_tree` column.

```python
pd.unique(trees_nov_24_df['height_of_tree'])
```

which **returns**:

```output
array(['e. 15 to 18 ', 'c. 9 to 12 m.', 'b. 6 to 9 m.', 'd. 12 to 15 m.',
       'a. to 6 m.', 'f. 18 to 24 m.', 'q. Not applicable',
       'g. 24 m. and higher', 'p. Impossible to determine', nan,
       'r. Not applicabel (tree need to be removed)',
       'ZZ_Discard 6 to 12 m.', 'ZZ_Discard 12 to 18 m.'], dtype=object)
```

As you can see, the values of 'height_of_tree' are stored as string categories. In order to get an understand of the average tree height in this dataset we could count the number of times a height category is assigned by using the method `.value_counts` on a pandas DataFrame

```python
trees_nov_24_df['height_of_tree'].value_counts()
```

Will provide counts of every height category.

```output
height_of_tree
c. 9 to 12 m.                                  49082
d. 12 to 15 m.                                 46356
b. 6 to 9 m.                                   44399
a. to 6 m.                                     40783
e. 15 to 18                                    40325
f. 18 to 24 m.                                 28390
q. Not applicable                              12198
g. 24 m. and higher                             8920
p. Impossible to determine                      1798
ZZ_Discard 12 to 18 m.                           104
ZZ_Discard 6 to 12 m.                             82
r. Not applicabel (tree need to be removed)       53
Name: count, dtype: int64
```

However, if we want to calculate with this data we will need to replace the categories to number values. For this we can use the method `.replace` on the pandas DataFrame. Since we do have a the actual height, we are going to make three collumns. One with the minimum height, the average height and maximum height of the tree. For this we assume that the maximum height of a tree is 30 meters and the minimum height 2 meters. Height categories from which no numbers can be extracted are assigned NaN (Not a Number) and not 0, since that will effect possible calculations. 


```python
trees_nov_24_df['height_min'] = trees_nov_24_df['height_of_tree'].replace({
     'e. 15 to 18 ': 15 ,
     'c. 9 to 12 m.': 9 ,
     'b. 6 to 9 m.': 6,
     'd. 12 to 15 m.': 12,
     'a. to 6 m.': 2,
     'f. 18 to 24 m.': 18 ,
     'q. Not applicable': 'NaN',
     'g. 24 m. and higher': 24,
     'p. Impossible to determine': 'NaN'  ,
     'r. Not applicabel (tree need to be removed)': 'NaN'  ,
     'ZZ_Discard 6 to 12 m.': 'NaN' ,
     'ZZ_Discard 12 to 18 m.': 'NaN' 
})
```

Yet, in order to use these figures in calculations, the data needs to be stored as numbers (floats). If we keep them as objects python will not be able to calculate with them. 

You can check the data type of the columns by using the .dtypes .

```python
trees_nov_24_df.dtypes
```

Since height of trees are not integer values, but could also have decimal we parse the column as floats by using the method .astype() .

```python
trees_nov_24_df['height_min'].astype('float')
```

We repeat the procedure for the average and the max.

```python
trees_nov_24_df['height_avg'] = trees_nov_24_df['height_of_tree'].replace({
     'e. 15 to 18 ': 16.5 ,
     'c. 9 to 12 m.': 10.5 ,
     'b. 6 to 9 m.': 7.5,
     'd. 12 to 15 m.': 13.5,
     'a. to 6 m.': 4.5,
     'f. 18 to 24 m.': 21 ,
     'q. Not applicable': 'NaN',
     'g. 24 m. and higher': 27,
     'p. Impossible to determine': 'NaN'  ,
     'r. Not applicabel (tree need to be removed)': 'NaN'  ,
     'ZZ_Discard 6 to 12 m.': 'NaN' ,
     'ZZ_Discard 12 to 18 m.': 'NaN' 
}).astype('float') 
```

```python
trees_nov_24_df['height_max'] = trees_nov_24_df['height_of_tree'].replace({
     'e. 15 to 18 ': 18 ,
     'c. 9 to 12 m.': 12 ,
     'b. 6 to 9 m.': 9,
     'd. 12 to 15 m.': 15,
     'a. to 6 m.': 6,
     'f. 18 to 24 m.': 24 ,
     'q. Not applicable': 'NaN',
     'g. 24 m. and higher': 30,
     'p. Impossible to determine': 'NaN'  ,
     'r. Not applicabel (tree need to be removed)': 'NaN'  ,
     'ZZ_Discard 6 to 12 m.': 'NaN' ,
     'ZZ_Discard 12 to 18 m.': 'NaN' 
}).astype('float') 
```

In general, botanical names of trees exist of three parts. All names start with the family name - the genus - followed by the species name and the cultivar name which is the name for the sort of cultivated tree selected by humans for specific traits. Since the number of unique tree names is quite high, we want to create a new column names `genus`, which only contains the first word from the column `botanical_name`. To do so, we use the `split` method. 

Splitting a string is relatively easy in pyton.

```python
a_string = "This string will be split"
splitted_string = a_string.split()
``` 

results in a list with the splitted string

```python
['This', 'string', 'will', 'be', 'split']
```

Adding a number to the the method gives you output of that specific string in the list.

For instance:
```python
splitted_strong = a_string.split()[0]
```

gives "This"

whereas:  

```python
splitted_strong = a_string.split()[1]
```

gives "string"

Since we want to apply this on a pandas dataframe we need to specify the datatype. When you work with a pandas Series (like the column trees_nov_24_df['botanical_name']), the values inside are strings, but the Series itself is not a string — it’s a pandas object (kind of like a list of many values). Therefore you can't call string methods (split, lower, replace, etc.) directly on a Series. Instead, pandas gives you a .str accessor — it's a bridge that lets you apply string methods to every item inside the Series.

Thus, in order to create a column with the genus we need to make sure to add the .str accessor as follows:

```python
trees_nov_24_df['genus'] = trees_nov_24_df['botanical_name'].str.split().str[0]
```


:::::::::::::::::::::::::::::::::::::::  challenge

### Challenge - Statistics

1. Create a list of unique tree types, by looking at `genus`  in the data and call it `tree_types`. 
  How many treesunique sites are there in the data? 

2. What is the difference between `len(tree_types)` and `trees_nov_24_df['genus'].nunique()`?

::::::::::::::::::::::: solution

1. `tree_types = pd.unique(trees_nov_24_df["genus"])`
  - How many unique trees are in the data? 
    `tree_types.size` or `len(tree_types)` provide the answer: 190
  
2. `len(tree_types)` and `trees_nov_24_df['genus'].nunique()` 
   both do not provide the same output since nunique expludes the trees with no names ('nan')
   The `nunique` method combines the count and unique value extraction,
   and can help avoid the creation of intermediate variables like `tree_types`.

::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

## Groups in Pandas

We often want to calculate summary statistics grouped by subsets or attributes
within fields of our data. For example, we might want to calculate the average
heigt of all trees in our data.

We can calculate basic statistics for all records in a single column using the
syntax below:

```python
trees_nov_24_df['height_avg'].describe()
```

gives **output**

```python
count    258255.000000
mean         12.236261
std           5.742619
min           4.500000
25%           7.500000
50%          10.500000
75%          16.500000
max          27.000000
Name: height_avg, dtype: float64
```


We can also extract one specific metric if we wish:

```python
trees_nov_24_df['height_avg'].min()
trees_nov_24_df['height_avg'].max()
trees_nov_24_df['height_avg'].mean()
trees_nov_24_df['height_avg'].std()
trees_nov_24_df['height_avg'].count()
```

But if we want to summarize by one or more variables, for example the type of tree `botanical_name`, we can
use **Pandas' `.groupby` method**. Once we've created a groupby DataFrame, we
can quickly calculate summary statistics by a group of our choice.

```python
# Group data by sex
grouped_data = trees_nov_24_df.groupby('genus')
```

The **pandas function `describe`** will return descriptive stats including: mean,
median, max, min, std and count for a particular column in the data. Pandas'
`describe` function will only return summary values for columns containing
numeric data.

```python
# Summary statistics for all numeric columns by genus
grouped_data.describe()
# Provide the mean for each numeric column by genus
grouped_data.mean(numeric_only=True)
```

`grouped_data.mean(numeric_only=True)` **OUTPUT:**

```output
                       id  year_planted         X          Y  height_min  \
genus                                                                      
Abelia       2.117183e+06   1881.755102  4.888244  52.372109   10.000000   
Abies        1.458963e+06   1742.028037  4.920285  52.340517   11.469136   
Acer         1.151349e+06   1807.874260  4.905818  52.351156   10.109694   
Aesculus     1.248570e+06   1909.928940  4.903473  52.359668    9.705545   
Ailanthus    1.111462e+06   1766.773523  4.871994  52.355281    8.093363   
...                   ...           ...       ...        ...         ...   
Weigela      9.221960e+05   2014.000000  4.936185  52.344231    2.000000   
Wisteria     4.513267e+06   1900.000000  4.904574  52.360918         NaN   
Zanthoxylum  9.287790e+05   1332.333333  4.920407  52.343063    2.000000   
Zelkova      1.963307e+06   1439.848168  4.943533  52.328632    4.566667   
Ziziphus     2.457262e+06   2012.000000  4.883860  52.342512    2.000000   

             height_avg  height_max  
genus                                
Abelia        11.700000   13.200000  
Abies         13.574074   15.518519  
Acer          11.818219   13.421655  
Aesculus      11.373942   12.948921  
Ailanthus      9.683352   11.203600  
...                 ...         ...  
Weigela        4.500000    6.000000  
Wisteria            NaN         NaN  
Zanthoxylum    4.500000    6.000000  
Zelkova        6.600000    8.120000  
Ziziphus       4.500000    6.000000  

[189 rows x 7 columns]
```

The `groupby` command is powerful in that it allows us to quickly generate
summary stats.

### Basic Math Functions

If we wanted to, we could apply a mathematical operation like addition or division
on an entire column of our data. For example, let's multiply all height_max values by 2.

```python
# Multiply all height_max values by 2
trees_nov_24_df["height_max"]*2
```

A more practical use of this might be to normalize the data according to a mean, area,
or some other value calculated from our data.

## Quick \& Easy Plotting Data Using Pandas

We can plot our summary stats using Pandas, too. 

However before we do so, let us first create a pandas dataframe containing the count for every tree type (i.e. genus). Since we want to count it based on the unique id, we include ['id'].

```python
genus_count = trees_nov_24_df.groupby('genus')['id'].nunique()
```

This is however a series and not a dataframe anymore. We therefore need to convert it back again to a dataframe by doing. 

```python
genus_count_df = genus_count.reset_index()
```
When you do .reset_index() on a Series, it converts it into a DataFrame. A Series has an index (the labels, like your genus names) and values (the counts). When you .reset_index(), it moves the index into a normal column and keeps the values in another column. 

Now, let us rename the ['id'] column into ['count'] to make the dataframe look more neatier.

```python
genus_count_df = genus_count_df.rename(columns={'id': 'count'})
```

Next we want to create a plot based on this dataframe, however plotting 189 different trees might be a bit too much in one plot. We therefore select the top 20 of most present trees in our dataset. To do so, we first sort our data based on the count, after which we make a dataframe with the top 20 in it. 

To sort a dataframe we use .sort_values, we choose the column and set how to sort it. 

```python
genus_count_df = genus_count_df.sort_values(by='count', ascending=False)
```
Next, we make a subselection of the top 20 using `.head`

```python
top_20_trees = genus_count_df.head(20)
```

Now let us make the plot.

```python
# Make sure figures appear inline in Ipython Notebook
%matplotlib inline
# Create a quick bar chart and put the genus name on the x-axis
top_20_trees.plot(x='genus', kind='bar')
```

![](fig/01_bar_tree_count.png){alt='Weight by Species Site'}
Count per genus

For more information on pandas plots, see [pandas' documentation page on visualization][pandas-plot].

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::



[ernst]: https://www.esapubs.org/archive/ecol/E090/118/default.htm
[pptd]: https://figshare.com/articles/Portal_Project_Teaching_Database/1314459
[figshare-ndownloader]: https://ndownloader.figshare.com/files/2292172
[pandas]: https://pandas.pydata.org
[matplotlib]: https://matplotlib.org
[numpy]: https://www.numpy.org/
[spreadsheet-lesson5]: https://www.datacarpentry.org/spreadsheet-ecology-lesson/05-exporting-data
[pd-dataframe]: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html
[python-datastructures]: https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences
[pandas-plot]: https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html#basic-plotting-plot


:::::::::::::::::::::::::::::::::::::::: keypoints

- Libraries enable us to extend the functionality of Python.
- Pandas is a popular library for working with data.
- A Dataframe is a Pandas data structure that allows one to access data by column (name or index) or row.
- Aggregating data using the `groupby()` function enables you to generate useful summaries of data quickly.

::::::::::::::::::::::::::::::::::::::::::::::::::


