<div>
<b>✅ Reviewer's comment, v. 2</b> 
    
Great! You've done a great job and now your project has been accepted.
    
Thank you for your work and I wish you success in the following projects!

<div>
  
**Hello Dhruval**

My name is Dima, and I will be reviewing your project. 

You will find my comments in coloured cells marked as 'Reviewer's comment'. The cell colour will vary based on the contents - I am explaining it further below. 

**Note:** Please do not remove or change my comments - they will help me in my future reviews and will make the process smoother for both of us. 

<div class="alert alert-success">
<b>✅ Reviewer's comment</b> 
    
Such comment will mark efficient solutions and good ideas that can be used in other projects.
</div>

<div class="alert alert-warning">
<b>⚠️ Reviewer's comment</b> 
    
The parts marked with yellow comments indicate that there is room for optimisation. Though the correction is not necessary it is good if you implement it.
</div>

<div class="alert alert-danger">
<b>⛔️ Reviewer's comment</b> 
    
If you see such a comment, it means that there is a problem that needs to be fixed. Please note that I won't be able to accept your project until the issue is resolved.
</div>

You are also very welcome to leave your comments / describe the corrections you've done / ask me questions, marking them with a different colour. You can use the example below: 

<div class="alert alert-info">
<b>Student's comment</b>

## Basic Python - Project <a id='intro'></a>

<div>
    
<div class="alert alert-success">
<b>Review summary</b> 
    
Dhruval, thanks for submitting the project. You've done a very good job and I enjoyed reviewing it.
    
- You completed all the tasks.
- Your code was optimal and easy to read. 
- You wrote your own functions.
    
There is only one critical comment that need to be corrected. You will find it in the red-colored cell in relevant section. If you have any questions please write them when you return your project. 
    
I'll be looking forward to getting your updated notebook.

## Introduction <a id='intro'></a>
In this project, you will work with data from the entertainment industry. You will study a dataset with records on movies and shows. The research will focus on the "Golden Age" of television, which began in 1999 with the release of *The Sopranos* and is still ongoing.

The aim of this project is to investigate how the number of votes a title receives impacts its ratings. The assumption is that highly-rated shows (we will focus on TV shows, ignoring movies) released during the "Golden Age" of television also have the most votes.

### Stages 
Data on movies and shows is stored in the `/datasets/movies_and_shows.csv` file. There is no information about the quality of the data, so you will need to explore it before doing the analysis.

First, you'll evaluate the quality of the data and see whether its issues are significant. Then, during data preprocessing, you will try to account for the most critical problems.
 
Your project will consist of three stages:
 1. Data overview
 2. Data preprocessing
 3. Data analysis

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
Title and introduction are essential parts of the project. Make sure you do not forget to include it in your further projects. 
    
It is optimal if introduction consists of:
    
- brief description of the situation;
- goal of the project;
- description of the data we are going to use.
</div>


## Stage 1. Data overview <a id='data_review'></a>

Open and explore the data.

You'll need `pandas`, so import it.


```python
# importing pandas
import pandas as pd

```

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> Needed library has been added </div>

Read the `movies_and_shows.csv` file from the `datasets` folder and save it in the `df` variable:


```python
# reading the files and storing them to df
df = pd.read_csv('/datasets/movies_and_shows.csv')
```

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> The correct path to the file is specified: the slash at the beginning of the path is very important, as it indicates that you need to search for the file in the root folder. </div>

Print the first 10 table rows:


```python
# obtaining the first 10 rows from the df table
# hint: you can use head() and tail() in Jupyter Notebook without wrapping them into print()
print(df.head(10))
```

                  name                      Character   r0le        TITLE   Type  \
    0   Robert De Niro                  Travis Bickle  ACTOR  Taxi Driver  MOVIE   
    1     Jodie Foster                  Iris Steensma  ACTOR  Taxi Driver  MOVIE   
    2    Albert Brooks                            Tom  ACTOR  Taxi Driver  MOVIE   
    3    Harvey Keitel        Matthew 'Sport' Higgins  ACTOR  Taxi Driver  MOVIE   
    4  Cybill Shepherd                          Betsy  ACTOR  Taxi Driver  MOVIE   
    5      Peter Boyle                         Wizard  ACTOR  Taxi Driver  MOVIE   
    6   Leonard Harris      Senator Charles Palantine  ACTOR  Taxi Driver  MOVIE   
    7   Diahnne Abbott                Concession Girl  ACTOR  Taxi Driver  MOVIE   
    8      Gino Ardito             Policeman at Rally  ACTOR  Taxi Driver  MOVIE   
    9  Martin Scorsese  Passenger Watching Silhouette  ACTOR  Taxi Driver  MOVIE   
    
       release Year              genres  imdb sc0re  imdb v0tes  
    0          1976  ['drama', 'crime']         8.2    808582.0  
    1          1976  ['drama', 'crime']         8.2    808582.0  
    2          1976  ['drama', 'crime']         8.2    808582.0  
    3          1976  ['drama', 'crime']         8.2    808582.0  
    4          1976  ['drama', 'crime']         8.2    808582.0  
    5          1976  ['drama', 'crime']         8.2    808582.0  
    6          1976  ['drama', 'crime']         8.2    808582.0  
    7          1976  ['drama', 'crime']         8.2    808582.0  
    8          1976  ['drama', 'crime']         8.2    808582.0  
    9          1976  ['drama', 'crime']         8.2    808582.0  


Obtain the general information about the table with one command:


```python
# obtaining general information about the data in df
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 85579 entries, 0 to 85578
    Data columns (total 9 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0      name       85579 non-null  object 
     1   Character     85579 non-null  object 
     2   r0le          85579 non-null  object 
     3   TITLE         85578 non-null  object 
     4     Type        85579 non-null  object 
     5   release Year  85579 non-null  int64  
     6   genres        85579 non-null  object 
     7   imdb sc0re    80970 non-null  float64
     8   imdb v0tes    80853 non-null  float64
    dtypes: float64(2), int64(1), object(6)
    memory usage: 5.9+ MB


<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
Great - you've used a comprehensive set of methods to have a first look at the data.
    

The table contains nine columns. The majority store the same data type: object. The only exceptions are `'release Year'` (int64 type), `'imdb sc0re'` (float64 type) and `'imdb v0tes'` (float64 type). Scores and votes will be used in our analysis, so it's important to verify that they are present in the dataframe in the appropriate numeric format. Three columns (`'TITLE'`, `'imdb sc0re'` and `'imdb v0tes'`) have missing values.

According to the documentation:
- `'name'` — actor/director's name and last name
- `'Character'` — character played (for actors)
- `'r0le '` — the person's contribution to the title (it can be in the capacity of either actor or director)
- `'TITLE '` — title of the movie (show)
- `'  Type'` — show or movie
- `'release Year'` — year when movie (show) was released
- `'genres'` — list of genres under which the movie (show) falls
- `'imdb sc0re'` — score on IMDb
- `'imdb v0tes'` — votes on IMDb

We can see three issues with the column names:
1. Some names are uppercase, while others are lowercase.
2. There are names containing whitespace.
3. A few column names have digit '0' instead of letter 'o'. 


### Conclusions <a id='data_review_conclusions'></a> 

Each row in the table stores data about a movie or show. The columns can be divided into two categories: the first is about the roles held by different people who worked on the movie or show (role, name of the actor or director, and character if the row is about an actor); the second category is information about the movie or show itself (title, release year, genre, imdb figures).

It's clear that there is sufficient data to do the analysis and evaluate our assumption. However, to move forward, we need to preprocess the data.

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
Please note that it is highly recommended to add a conclusion / summary after each section and describe briefly your observations and / or major outcomes of the analysis.

## Stage 2. Data preprocessing <a id='data_preprocessing'></a>
Correct the formatting in the column headers and deal with the missing values. Then, check whether there are duplicates in the data.


```python
# the list of column names in the df table
df.columns

```




    Index(['   name', 'Character', 'r0le', 'TITLE', '  Type', 'release Year',
           'genres', 'imdb sc0re', 'imdb v0tes'],
          dtype='object')



Change the column names according to the rules of good style:
* If the name has several words, use snake_case
* All characters must be lowercase
* Remove whitespace
* Replace zero with letter 'o'


```python
# renaming columns
df = df.rename(columns ={'   name': 'name', 'Character': 'character', 
                          'r0le': 'role', 'TITLE': 'title', '  Type': 'type', 'release Year': 'release_year',
                          'imdb sc0re': 'imdb_score', 'imdb v0tes': 'imdb_voted'
                         })

```

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
This is a good way to rename the columns.

Check the result. Print the names of the columns once more:


```python
# checking result: the list of column names
print(df.columns)

```

    Index(['name', 'character', 'role', 'title', 'type', 'release_year', 'genres',
           'imdb_score', 'imdb_voted'],
          dtype='object')


### Missing values <a id='missing_values'></a>
First, find the number of missing values in the table. To do so, combine two `pandas` methods:


```python
# calculating missing values
print(df.isna().sum())

```

    name               0
    character          0
    role               0
    title              1
    type               0
    release_year       0
    genres             0
    imdb_score      4609
    imdb_voted      4726
    dtype: int64


<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
The isna() method is selected to find the missing values, it's great!

Not all missing values affect the research: the single missing value in `'title'` is not critical. The missing values in columns `'imdb_score'` and `'imdb_votes'` represent around 6% of all records (4,609 and 4,726, respectively, of the total 85,579). This could potentially affect our research. To avoid this issue, we will drop rows with missing values in the `'imdb_score'` and `'imdb_votes'` columns.


```python
# dropping rows where columns with title, scores and votes have missing values
df = df.dropna(axis = 'rows')
```

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
Perfect!

Make sure the table doesn't contain any more missing values. Count the missing values again.


```python
# counting missing values
print(df.isna().sum())

```

    name            0
    character       0
    role            0
    title           0
    type            0
    release_year    0
    genres          0
    imdb_score      0
    imdb_voted      0
    dtype: int64


### Duplicates <a id='duplicates'></a>
Find the number of duplicate rows in the table using one command:


```python
# counting duplicate rows

print(df.duplicated().sum())

```

    6994


Review the duplicate rows to determine if removing them would distort our dataset.


```python
# Produce table with duplicates (with original rows included) and review last 5 rows
duplicates_rows = df[df.duplicated(keep = False)]
print(duplicates_rows.tail(5))
```

                          name                 character   role    title   type  \
    85569       Jessica Cediel           Liliana Navarro  ACTOR  Lokillo  MOVIE   
    85570  Javier Gardeaz?­bal  Agust??n "Peluca" Ort??z  ACTOR  Lokillo  MOVIE   
    85571        Carla Giraldo            Valery Reinoso  ACTOR  Lokillo  MOVIE   
    85572  Ana Mar??a S?­nchez                   Lourdes  ACTOR  Lokillo  MOVIE   
    85577         Isabel Gaona                    Cacica  ACTOR  Lokillo  MOVIE   
    
           release_year      genres  imdb_score  imdb_voted  
    85569          2021  ['comedy']         3.8        68.0  
    85570          2021  ['comedy']         3.8        68.0  
    85571          2021  ['comedy']         3.8        68.0  
    85572          2021  ['comedy']         3.8        68.0  
    85577          2021  ['comedy']         3.8        68.0  


There are two clear duplicates in the printed rows. We can safely remove them.
Call the `pandas` method for getting rid of duplicate rows:


```python
# removing duplicate rows
df = df.drop_duplicates().reset_index(drop=True)
```

Check for duplicate rows once more to make sure you have removed all of them:


```python
# checking for duplicates
print(df.duplicated())
print(df.duplicated().sum())

```

    0        False
    1        False
    2        False
    3        False
    4        False
             ...  
    73854    False
    73855    False
    73856    False
    73857    False
    73858    False
    Length: 73859, dtype: bool
    0


<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
Great, you found and removed the duplicates. And did very thorough checks to make sure the duplicates are gone.

Now get rid of implicit duplicates in the `'type'` column. For example, the string `'SHOW'` can be written in different ways. These kinds of errors will also affect the result.

Print a list of unique `'type'` names, sorted in alphabetical order. To do so:
* Retrieve the intended dataframe column 
* Apply a sorting method to it
* For the sorted column, call the method that will return all unique column values


```python
# viewing unique type names
print(df['type'].sort_values().unique())

```

    ['MOVIE' 'SHOW' 'movies' 'shows' 'the movie' 'tv' 'tv series' 'tv show'
     'tv shows']


<div class="alert alert-danger">
<b>⛔️ Reviewer's comment, v. 1</b> 

Please note, that according to the technical task it was asked:
    
* For the **sorted** column, call the method that will return all unique column values
    
So, we should use sorting here

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 2</b> 
    
Now it's perfect!

Look through the list to find implicit duplicates of `'show'` (`'movie'` duplicates will be ignored since the assumption is about shows). These could be names written incorrectly or alternative names of the same genre.

You will see the following implicit duplicates:
* `'shows'`
* `'SHOW'`
* `'tv show'`
* `'tv shows'`
* `'tv series'`
* `'tv'`

To get rid of them, declare the function `replace_wrong_show()` with two parameters: 
* `wrong_shows_list=` — the list of duplicates
* `correct_show=` — the string with the correct value

The function should correct the names in the `'type'` column from the `df` table (i.e., replace each value from the `wrong_shows_list` list with the value in `correct_show`).


```python
# function for replacing implicit duplicates

def replace_wrong_show(wrong_shows_list, correct_show):
    df['type'] = df['type'].replace(wrong_shows_list, correct_show)

    
```

Call `replace_wrong_show()` and pass it arguments so that it clears implicit duplicates and replaces them with `SHOW`:


```python
# removing implicit duplicates
wrong_shows_list = ['shows', 'SHOW', 'tv show', 'tv shows', 'tv series', 'tv']
correct_show = 'show'
replace_wrong_show(wrong_shows_list, correct_show)

```

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
Yes, this is what was needed!

Make sure the duplicate names are removed. Print the list of unique values from the `'type'` column:


```python
# viewing unique genre names
print(df['type'].unique())
```

    ['MOVIE' 'the movie' 'show' 'movies']


### Conclusions <a id='data_preprocessing_conclusions'></a>
We detected three issues with the data:

- Incorrect header styles
- Missing values
- Duplicate rows and implicit duplicates

The headers have been cleaned up to make processing the table simpler.

All rows with missing values have been removed. 

The absence of duplicates will make the results more precise and easier to understand.

Now we can move on to our analysis of the prepared data.

## Stage 3. Data analysis <a id='hypotheses'></a>

Based on the previous project stages, you can now define how the assumption will be checked. Calculate the average amount of votes for each score (this data is available in the `imdb_score` and `imdb_votes` columns), and then check how these averages relate to each other. If the averages for shows with the highest scores are bigger than those for shows with lower scores, the assumption appears to be true.

Based on this, complete the following steps:

- Filter the dataframe to only include shows released in 1999 or later.
- Group scores into buckets by rounding the values of the appropriate column (a set of 1-10 integers will help us make the outcome of our calculations more evident without damaging the quality of our research).
- Identify outliers among scores based on their number of votes, and exclude scores with few votes.
- Calculate the average votes for each score and check whether the assumption matches the results.

To filter the dataframe and only include shows released in 1999 or later, you will take two steps. First, keep only titles published in 1999 or later in our dataframe. Then, filter the table to only contain shows (movies will be removed).


```python
# using conditional indexing modify df so it has only titles released after 1999 (with 1999 included)
# give the slice of dataframe new name
after_1999 = df[df['release_year'] >= 1999]
print(after_1999)
```

                         name            character      role     title       type  \
    1661          Jeff Probst       Himself - Host     ACTOR  Survivor       show   
    1952     Benicio del Toro  Franky Four Fingers     ACTOR    Snatch      MOVIE   
    1953        Dennis Farina           Cousin Avi     ACTOR    Snatch      MOVIE   
    1954         Vinnie Jones    Bullet Tooth Tony     ACTOR    Snatch      MOVIE   
    1955            Brad Pitt        Mickey O'Neil     ACTOR    Snatch      MOVIE   
    ...                   ...                  ...       ...       ...        ...   
    73854       A??da Morales              Maritza     ACTOR   Lokillo  the movie   
    73855    Adelaida Buscato           Mar??a Paz     ACTOR   Lokillo  the movie   
    73856  Luz Stella Luengas         Karen Bayona     ACTOR   Lokillo  the movie   
    73857        In??s Prieto                Fanny     ACTOR   Lokillo  the movie   
    73858      Julian Gaviria              unknown  DIRECTOR   Lokillo  the movie   
    
           release_year               genres  imdb_score  imdb_voted  
    1661           2000          ['reality']         7.4     24687.0  
    1952           2000  ['crime', 'comedy']         8.3    841435.0  
    1953           2000  ['crime', 'comedy']         8.3    841435.0  
    1954           2000  ['crime', 'comedy']         8.3    841435.0  
    1955           2000  ['crime', 'comedy']         8.3    841435.0  
    ...             ...                  ...         ...         ...  
    73854          2021           ['comedy']         3.8        68.0  
    73855          2021           ['comedy']         3.8        68.0  
    73856          2021           ['comedy']         3.8        68.0  
    73857          2021           ['comedy']         3.8        68.0  
    73858          2021           ['comedy']         3.8        68.0  
    
    [69881 rows x 9 columns]



```python
# repeat conditional indexing so df has only shows (movies are removed as result)
only_shows = after_1999[after_1999['type']== 'show']
only_shows

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>character</th>
      <th>role</th>
      <th>title</th>
      <th>type</th>
      <th>release_year</th>
      <th>genres</th>
      <th>imdb_score</th>
      <th>imdb_voted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1661</th>
      <td>Jeff Probst</td>
      <td>Himself - Host</td>
      <td>ACTOR</td>
      <td>Survivor</td>
      <td>show</td>
      <td>2000</td>
      <td>['reality']</td>
      <td>7.4</td>
      <td>24687.0</td>
    </tr>
    <tr>
      <th>2073</th>
      <td>Mayumi Tanaka</td>
      <td>Monkey D. Luffy (voice)</td>
      <td>ACTOR</td>
      <td>One Piece</td>
      <td>show</td>
      <td>1999</td>
      <td>['animation', 'action', 'comedy', 'drama', 'fa...</td>
      <td>8.8</td>
      <td>117129.0</td>
    </tr>
    <tr>
      <th>2074</th>
      <td>Kazuya Nakai</td>
      <td>Roronoa Zoro (voice)</td>
      <td>ACTOR</td>
      <td>One Piece</td>
      <td>show</td>
      <td>1999</td>
      <td>['animation', 'action', 'comedy', 'drama', 'fa...</td>
      <td>8.8</td>
      <td>117129.0</td>
    </tr>
    <tr>
      <th>2075</th>
      <td>Akemi Okamura</td>
      <td>Nami (voice)</td>
      <td>ACTOR</td>
      <td>One Piece</td>
      <td>show</td>
      <td>1999</td>
      <td>['animation', 'action', 'comedy', 'drama', 'fa...</td>
      <td>8.8</td>
      <td>117129.0</td>
    </tr>
    <tr>
      <th>2076</th>
      <td>Kappei Yamaguchi</td>
      <td>Usopp (voice)</td>
      <td>ACTOR</td>
      <td>One Piece</td>
      <td>show</td>
      <td>1999</td>
      <td>['animation', 'action', 'comedy', 'drama', 'fa...</td>
      <td>8.8</td>
      <td>117129.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>73831</th>
      <td>Maneerat Kam-Uan</td>
      <td>Ae</td>
      <td>ACTOR</td>
      <td>Let's Eat</td>
      <td>show</td>
      <td>2021</td>
      <td>['drama', 'comedy']</td>
      <td>8.2</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>73832</th>
      <td>Rudklao Amratisha</td>
      <td>unknown</td>
      <td>ACTOR</td>
      <td>Let's Eat</td>
      <td>show</td>
      <td>2021</td>
      <td>['drama', 'comedy']</td>
      <td>8.2</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>73833</th>
      <td>Jaturong Mokjok</td>
      <td>unknown</td>
      <td>ACTOR</td>
      <td>Let's Eat</td>
      <td>show</td>
      <td>2021</td>
      <td>['drama', 'comedy']</td>
      <td>8.2</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>73834</th>
      <td>Pisamai Wilaisak</td>
      <td>unknown</td>
      <td>ACTOR</td>
      <td>Let's Eat</td>
      <td>show</td>
      <td>2021</td>
      <td>['drama', 'comedy']</td>
      <td>8.2</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>73835</th>
      <td>Sarawut Wichiensarn</td>
      <td>unknown</td>
      <td>DIRECTOR</td>
      <td>Let's Eat</td>
      <td>show</td>
      <td>2021</td>
      <td>['drama', 'comedy']</td>
      <td>8.2</td>
      <td>5.0</td>
    </tr>
  </tbody>
</table>
<p>13430 rows × 9 columns</p>
</div>



The scores that are to be grouped should be rounded. For instance, titles with scores like 7.8, 8.1, and 8.3 will all be placed in the same bucket with a score of 8.


```python
# rounding column with scores

only_shows['imdb_score'] = only_shows['imdb_score'].round()
#checking the outcome with tail()
only_shows.head()
```

    /tmp/ipykernel_771/2130509769.py:3: SettingWithCopyWarning: 
    A value is trying to be set on a copy of a slice from a DataFrame.
    Try using .loc[row_indexer,col_indexer] = value instead
    
    See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
      only_shows['imdb_score'] = only_shows['imdb_score'].round()





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>character</th>
      <th>role</th>
      <th>title</th>
      <th>type</th>
      <th>release_year</th>
      <th>genres</th>
      <th>imdb_score</th>
      <th>imdb_voted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1661</th>
      <td>Jeff Probst</td>
      <td>Himself - Host</td>
      <td>ACTOR</td>
      <td>Survivor</td>
      <td>show</td>
      <td>2000</td>
      <td>['reality']</td>
      <td>7.0</td>
      <td>24687.0</td>
    </tr>
    <tr>
      <th>2073</th>
      <td>Mayumi Tanaka</td>
      <td>Monkey D. Luffy (voice)</td>
      <td>ACTOR</td>
      <td>One Piece</td>
      <td>show</td>
      <td>1999</td>
      <td>['animation', 'action', 'comedy', 'drama', 'fa...</td>
      <td>9.0</td>
      <td>117129.0</td>
    </tr>
    <tr>
      <th>2074</th>
      <td>Kazuya Nakai</td>
      <td>Roronoa Zoro (voice)</td>
      <td>ACTOR</td>
      <td>One Piece</td>
      <td>show</td>
      <td>1999</td>
      <td>['animation', 'action', 'comedy', 'drama', 'fa...</td>
      <td>9.0</td>
      <td>117129.0</td>
    </tr>
    <tr>
      <th>2075</th>
      <td>Akemi Okamura</td>
      <td>Nami (voice)</td>
      <td>ACTOR</td>
      <td>One Piece</td>
      <td>show</td>
      <td>1999</td>
      <td>['animation', 'action', 'comedy', 'drama', 'fa...</td>
      <td>9.0</td>
      <td>117129.0</td>
    </tr>
    <tr>
      <th>2076</th>
      <td>Kappei Yamaguchi</td>
      <td>Usopp (voice)</td>
      <td>ACTOR</td>
      <td>One Piece</td>
      <td>show</td>
      <td>1999</td>
      <td>['animation', 'action', 'comedy', 'drama', 'fa...</td>
      <td>9.0</td>
      <td>117129.0</td>
    </tr>
  </tbody>
</table>
</div>



<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
All the transformations were performed absolutely correctly

It is now time to identify outliers based on the number of votes.


```python
# Use groupby() for scores and count all unique values in each group, print the result
score_count = only_shows.groupby('imdb_score')['imdb_voted'].count()
score_count
```




    imdb_score
    2.0       24
    3.0       27
    4.0      180
    5.0      592
    6.0     2494
    7.0     4706
    8.0     4842
    9.0      557
    10.0       8
    Name: imdb_voted, dtype: int64



<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
The dataframe was filtered and grouped flawlessly

Based on the aggregation performed, it is evident that scores 2 (24 voted shows), 3 (27 voted shows), and 10 (only 8 voted shows) are outliers. There isn't enough data for these scores for the average number of votes to be meaningful.

To obtain the mean numbers of votes for the selected scores (we identified a range of 4-9 as acceptable), use conditional filtering and grouping.


```python
# filter dataframe using two conditions (scores to be in the range 4-9)
filtered_dataframe = only_shows[(only_shows['imdb_score'] >= 4) & (only_shows['imdb_score'] <= 9)]

# group scores and corresponding average number of votes, reset index and print the result

grouped_scores = filtered_dataframe.groupby('imdb_score')['imdb_voted'].mean().reset_index()
grouped_scores

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>imdb_score</th>
      <th>imdb_voted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4.0</td>
      <td>5277.583333</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5.0</td>
      <td>3143.942568</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6.0</td>
      <td>3481.717322</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7.0</td>
      <td>8727.068211</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8.0</td>
      <td>30299.460967</td>
    </tr>
    <tr>
      <th>5</th>
      <td>9.0</td>
      <td>126904.109515</td>
    </tr>
  </tbody>
</table>
</div>



Now for the final step! Round the column with the averages, rename both columns, and print the dataframe in descending order.


```python
# round column with averages
grouped_scores['imdb_voted'] = grouped_scores['imdb_voted'].round()

# rename columns
rename_columns = grouped_scores.rename(columns={'imdb_score':'scores', 'imdb_voted':'votes'})

# print dataframe in descending order
descending_order = rename_columns.sort_values(by= 'votes', ascending = False)
descending_order

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>scores</th>
      <th>votes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>9.0</td>
      <td>126904.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8.0</td>
      <td>30299.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7.0</td>
      <td>8727.0</td>
    </tr>
    <tr>
      <th>0</th>
      <td>4.0</td>
      <td>5278.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6.0</td>
      <td>3482.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5.0</td>
      <td>3144.0</td>
    </tr>
  </tbody>
</table>
</div>



The assumption macthes the analysis: the shows with the top 3 scores have the most amounts of votes.

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
Great! Also correct rounding and grouping in this section

## Conclusion <a id='hypotheses'></a>

The research done confirms that highly-rated shows released during the "Golden Age" of television also have the most votes. While shows with score 4 have more votes than ones with scores 5 and 6, the top three (scores 7-9) have the largest number. The data studied represents around 94% of the original set, so we can be confident in our findings.

<div class="alert alert-success">
<b>✅ Reviewer's comment, v. 1</b> 
    
Overall conclusion is an important part, where we should include the summary of the outcomes of the project.
