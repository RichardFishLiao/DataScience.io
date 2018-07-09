imdb.shape 可以查看一个dataFrame是几行几列imdb.head()可以观看前五行，或者可以输入n来查看n行的数据imdb[['color','director_name']]如果要查看某两行或以上的行，需要一个数组内套多一个数组imdb.iloc[10:20]指的是取当前dataFrame的第十行到第十九行的数据，意思是如果一个dataFrame的index是从10开始的，那么[10:20]就是从20到29的数据
imdb.loc[10:20]指的是当前dataFrame的index为10到index为20的数据，完全按照index的名字来取得数据
   A         B
0  1.068932 -0.794307
2 -0.470056  1.192211
4 -0.284561  0.756029
6  1.037563 -0.267820
8 -0.538478 -0.800654

In [5]: df.iloc[[2]]
Out[5]: 
   A         B
4 -0.284561  0.756029

In [6]: df.loc[[2]]
Out[6]: 
   A         B
2 -0.470056  1.192211

```python
import numpy as np
import pandas as pd
from pandas import Series, DataFrame
```


```python
!pwd
```

    /Users/penxiao/PycharmProjects/oschina/python-data-science/03-pandas



```python
!ls /Users/penxiao/PycharmProjects/oschina/python-data-science/homework
```

    [31mmovie_metadata.csv[m[m



```python
imdb = pd.read_csv('/Users/penxiao/PycharmProjects/oschina/python-data-science/homework/movie_metadata.csv')
```


```python
imdb.shape
```




    (5043, 28)




```python
imdb.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>color</th>
      <th>director_name</th>
      <th>num_critic_for_reviews</th>
      <th>duration</th>
      <th>director_facebook_likes</th>
      <th>actor_3_facebook_likes</th>
      <th>actor_2_name</th>
      <th>actor_1_facebook_likes</th>
      <th>gross</th>
      <th>genres</th>
      <th>...</th>
      <th>num_user_for_reviews</th>
      <th>language</th>
      <th>country</th>
      <th>content_rating</th>
      <th>budget</th>
      <th>title_year</th>
      <th>actor_2_facebook_likes</th>
      <th>imdb_score</th>
      <th>aspect_ratio</th>
      <th>movie_facebook_likes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Color</td>
      <td>James Cameron</td>
      <td>723.0</td>
      <td>178.0</td>
      <td>0.0</td>
      <td>855.0</td>
      <td>Joel David Moore</td>
      <td>1000.0</td>
      <td>760505847.0</td>
      <td>Action|Adventure|Fantasy|Sci-Fi</td>
      <td>...</td>
      <td>3054.0</td>
      <td>English</td>
      <td>USA</td>
      <td>PG-13</td>
      <td>237000000.0</td>
      <td>2009.0</td>
      <td>936.0</td>
      <td>7.9</td>
      <td>1.78</td>
      <td>33000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Color</td>
      <td>Gore Verbinski</td>
      <td>302.0</td>
      <td>169.0</td>
      <td>563.0</td>
      <td>1000.0</td>
      <td>Orlando Bloom</td>
      <td>40000.0</td>
      <td>309404152.0</td>
      <td>Action|Adventure|Fantasy</td>
      <td>...</td>
      <td>1238.0</td>
      <td>English</td>
      <td>USA</td>
      <td>PG-13</td>
      <td>300000000.0</td>
      <td>2007.0</td>
      <td>5000.0</td>
      <td>7.1</td>
      <td>2.35</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Color</td>
      <td>Sam Mendes</td>
      <td>602.0</td>
      <td>148.0</td>
      <td>0.0</td>
      <td>161.0</td>
      <td>Rory Kinnear</td>
      <td>11000.0</td>
      <td>200074175.0</td>
      <td>Action|Adventure|Thriller</td>
      <td>...</td>
      <td>994.0</td>
      <td>English</td>
      <td>UK</td>
      <td>PG-13</td>
      <td>245000000.0</td>
      <td>2015.0</td>
      <td>393.0</td>
      <td>6.8</td>
      <td>2.35</td>
      <td>85000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Color</td>
      <td>Christopher Nolan</td>
      <td>813.0</td>
      <td>164.0</td>
      <td>22000.0</td>
      <td>23000.0</td>
      <td>Christian Bale</td>
      <td>27000.0</td>
      <td>448130642.0</td>
      <td>Action|Thriller</td>
      <td>...</td>
      <td>2701.0</td>
      <td>English</td>
      <td>USA</td>
      <td>PG-13</td>
      <td>250000000.0</td>
      <td>2012.0</td>
      <td>23000.0</td>
      <td>8.5</td>
      <td>2.35</td>
      <td>164000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>Doug Walker</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>131.0</td>
      <td>NaN</td>
      <td>Rob Walker</td>
      <td>131.0</td>
      <td>NaN</td>
      <td>Documentary</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>12.0</td>
      <td>7.1</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
imdb[['color','director_name']]
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>color</th>
      <th>director_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Color</td>
      <td>James Cameron</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Color</td>
      <td>Gore Verbinski</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Color</td>
      <td>Sam Mendes</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Color</td>
      <td>Christopher Nolan</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>Doug Walker</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Color</td>
      <td>Andrew Stanton</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Color</td>
      <td>Sam Raimi</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Color</td>
      <td>Nathan Greno</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Color</td>
      <td>Joss Whedon</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Color</td>
      <td>David Yates</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Color</td>
      <td>Zack Snyder</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Color</td>
      <td>Bryan Singer</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Color</td>
      <td>Marc Forster</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Color</td>
      <td>Gore Verbinski</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Color</td>
      <td>Gore Verbinski</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Color</td>
      <td>Zack Snyder</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Color</td>
      <td>Andrew Adamson</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Color</td>
      <td>Joss Whedon</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Color</td>
      <td>Rob Marshall</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Color</td>
      <td>Barry Sonnenfeld</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Color</td>
      <td>Peter Jackson</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Color</td>
      <td>Marc Webb</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Color</td>
      <td>Ridley Scott</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Color</td>
      <td>Peter Jackson</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Color</td>
      <td>Chris Weitz</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Color</td>
      <td>Peter Jackson</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Color</td>
      <td>James Cameron</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Color</td>
      <td>Anthony Russo</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Color</td>
      <td>Peter Berg</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Color</td>
      <td>Colin Trevorrow</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>5013</th>
      <td>Color</td>
      <td>Eric Eason</td>
    </tr>
    <tr>
      <th>5014</th>
      <td>Color</td>
      <td>Uwe Boll</td>
    </tr>
    <tr>
      <th>5015</th>
      <td>Black and White</td>
      <td>Richard Linklater</td>
    </tr>
    <tr>
      <th>5016</th>
      <td>Color</td>
      <td>Joseph Mazzella</td>
    </tr>
    <tr>
      <th>5017</th>
      <td>Color</td>
      <td>Travis Legge</td>
    </tr>
    <tr>
      <th>5018</th>
      <td>Color</td>
      <td>Alex Kendrick</td>
    </tr>
    <tr>
      <th>5019</th>
      <td>Color</td>
      <td>Marcus Nispel</td>
    </tr>
    <tr>
      <th>5020</th>
      <td>NaN</td>
      <td>Brandon Landers</td>
    </tr>
    <tr>
      <th>5021</th>
      <td>Color</td>
      <td>Jay Duplass</td>
    </tr>
    <tr>
      <th>5022</th>
      <td>Black and White</td>
      <td>Jim Chuchu</td>
    </tr>
    <tr>
      <th>5023</th>
      <td>Color</td>
      <td>Daryl Wein</td>
    </tr>
    <tr>
      <th>5024</th>
      <td>Color</td>
      <td>Jason Trost</td>
    </tr>
    <tr>
      <th>5025</th>
      <td>Color</td>
      <td>John Waters</td>
    </tr>
    <tr>
      <th>5026</th>
      <td>Color</td>
      <td>Olivier Assayas</td>
    </tr>
    <tr>
      <th>5027</th>
      <td>Color</td>
      <td>Jafar Panahi</td>
    </tr>
    <tr>
      <th>5028</th>
      <td>Black and White</td>
      <td>Ivan Kavanagh</td>
    </tr>
    <tr>
      <th>5029</th>
      <td>Color</td>
      <td>Kiyoshi Kurosawa</td>
    </tr>
    <tr>
      <th>5030</th>
      <td>Color</td>
      <td>Tadeo Garcia</td>
    </tr>
    <tr>
      <th>5031</th>
      <td>Color</td>
      <td>Thomas L. Phillips</td>
    </tr>
    <tr>
      <th>5032</th>
      <td>Color</td>
      <td>Ash Baron-Cohen</td>
    </tr>
    <tr>
      <th>5033</th>
      <td>Color</td>
      <td>Shane Carruth</td>
    </tr>
    <tr>
      <th>5034</th>
      <td>Color</td>
      <td>Neill Dela Llana</td>
    </tr>
    <tr>
      <th>5035</th>
      <td>Color</td>
      <td>Robert Rodriguez</td>
    </tr>
    <tr>
      <th>5036</th>
      <td>Color</td>
      <td>Anthony Vallone</td>
    </tr>
    <tr>
      <th>5037</th>
      <td>Color</td>
      <td>Edward Burns</td>
    </tr>
    <tr>
      <th>5038</th>
      <td>Color</td>
      <td>Scott Smith</td>
    </tr>
    <tr>
      <th>5039</th>
      <td>Color</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5040</th>
      <td>Color</td>
      <td>Benjamin Roberds</td>
    </tr>
    <tr>
      <th>5041</th>
      <td>Color</td>
      <td>Daniel Hsia</td>
    </tr>
    <tr>
      <th>5042</th>
      <td>Color</td>
      <td>Jon Gunn</td>
    </tr>
  </tbody>
</table>
<p>5043 rows × 2 columns</p>
</div>




```python
sub_df = imdb[['director_name', 'movie_title','imdb_score']]
```


```python
sub_df.head(5)
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>director_name</th>
      <th>movie_title</th>
      <th>imdb_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>James Cameron</td>
      <td>Avatar</td>
      <td>7.9</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Gore Verbinski</td>
      <td>Pirates of the Caribbean: At World's End</td>
      <td>7.1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sam Mendes</td>
      <td>Spectre</td>
      <td>6.8</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Christopher Nolan</td>
      <td>The Dark Knight Rises</td>
      <td>8.5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Doug Walker</td>
      <td>Star Wars: Episode VII - The Force Awakens    ...</td>
      <td>7.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
tmp_df = sub_df.iloc[10:20,0:2]
tmp_df
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>director_name</th>
      <th>movie_title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10</th>
      <td>Zack Snyder</td>
      <td>Batman v Superman: Dawn of Justice</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Bryan Singer</td>
      <td>Superman Returns</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Marc Forster</td>
      <td>Quantum of Solace</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Gore Verbinski</td>
      <td>Pirates of the Caribbean: Dead Man's Chest</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Gore Verbinski</td>
      <td>The Lone Ranger</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Zack Snyder</td>
      <td>Man of Steel</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Andrew Adamson</td>
      <td>The Chronicles of Narnia: Prince Caspian</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Joss Whedon</td>
      <td>The Avengers</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Rob Marshall</td>
      <td>Pirates of the Caribbean: On Stranger Tides</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Barry Sonnenfeld</td>
      <td>Men in Black 3</td>
    </tr>
  </tbody>
</table>
</div>




```python
tmp_df.iloc[2:4,:]
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>director_name</th>
      <th>movie_title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>12</th>
      <td>Marc Forster</td>
      <td>Quantum of Solace</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Gore Verbinski</td>
      <td>Pirates of the Caribbean: Dead Man's Chest</td>
    </tr>
  </tbody>
</table>
</div>




```python
imdb.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>color</th>
      <th>director_name</th>
      <th>num_critic_for_reviews</th>
      <th>duration</th>
      <th>director_facebook_likes</th>
      <th>actor_3_facebook_likes</th>
      <th>actor_2_name</th>
      <th>actor_1_facebook_likes</th>
      <th>gross</th>
      <th>genres</th>
      <th>...</th>
      <th>num_user_for_reviews</th>
      <th>language</th>
      <th>country</th>
      <th>content_rating</th>
      <th>budget</th>
      <th>title_year</th>
      <th>actor_2_facebook_likes</th>
      <th>imdb_score</th>
      <th>aspect_ratio</th>
      <th>movie_facebook_likes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Color</td>
      <td>James Cameron</td>
      <td>723.0</td>
      <td>178.0</td>
      <td>0.0</td>
      <td>855.0</td>
      <td>Joel David Moore</td>
      <td>1000.0</td>
      <td>760505847.0</td>
      <td>Action|Adventure|Fantasy|Sci-Fi</td>
      <td>...</td>
      <td>3054.0</td>
      <td>English</td>
      <td>USA</td>
      <td>PG-13</td>
      <td>237000000.0</td>
      <td>2009.0</td>
      <td>936.0</td>
      <td>7.9</td>
      <td>1.78</td>
      <td>33000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Color</td>
      <td>Gore Verbinski</td>
      <td>302.0</td>
      <td>169.0</td>
      <td>563.0</td>
      <td>1000.0</td>
      <td>Orlando Bloom</td>
      <td>40000.0</td>
      <td>309404152.0</td>
      <td>Action|Adventure|Fantasy</td>
      <td>...</td>
      <td>1238.0</td>
      <td>English</td>
      <td>USA</td>
      <td>PG-13</td>
      <td>300000000.0</td>
      <td>2007.0</td>
      <td>5000.0</td>
      <td>7.1</td>
      <td>2.35</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Color</td>
      <td>Sam Mendes</td>
      <td>602.0</td>
      <td>148.0</td>
      <td>0.0</td>
      <td>161.0</td>
      <td>Rory Kinnear</td>
      <td>11000.0</td>
      <td>200074175.0</td>
      <td>Action|Adventure|Thriller</td>
      <td>...</td>
      <td>994.0</td>
      <td>English</td>
      <td>UK</td>
      <td>PG-13</td>
      <td>245000000.0</td>
      <td>2015.0</td>
      <td>393.0</td>
      <td>6.8</td>
      <td>2.35</td>
      <td>85000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Color</td>
      <td>Christopher Nolan</td>
      <td>813.0</td>
      <td>164.0</td>
      <td>22000.0</td>
      <td>23000.0</td>
      <td>Christian Bale</td>
      <td>27000.0</td>
      <td>448130642.0</td>
      <td>Action|Thriller</td>
      <td>...</td>
      <td>2701.0</td>
      <td>English</td>
      <td>USA</td>
      <td>PG-13</td>
      <td>250000000.0</td>
      <td>2012.0</td>
      <td>23000.0</td>
      <td>8.5</td>
      <td>2.35</td>
      <td>164000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>Doug Walker</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>131.0</td>
      <td>NaN</td>
      <td>Rob Walker</td>
      <td>131.0</td>
      <td>NaN</td>
      <td>Documentary</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>12.0</td>
      <td>7.1</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 28 columns</p>
</div>




```python
tmp_df
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>director_name</th>
      <th>movie_title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10</th>
      <td>Zack Snyder</td>
      <td>Batman v Superman: Dawn of Justice</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Bryan Singer</td>
      <td>Superman Returns</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Marc Forster</td>
      <td>Quantum of Solace</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Gore Verbinski</td>
      <td>Pirates of the Caribbean: Dead Man's Chest</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Gore Verbinski</td>
      <td>The Lone Ranger</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Zack Snyder</td>
      <td>Man of Steel</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Andrew Adamson</td>
      <td>The Chronicles of Narnia: Prince Caspian</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Joss Whedon</td>
      <td>The Avengers</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Rob Marshall</td>
      <td>Pirates of the Caribbean: On Stranger Tides</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Barry Sonnenfeld</td>
      <td>Men in Black 3</td>
    </tr>
  </tbody>
</table>
</div>




```python
tmp_df.loc[15:17,:'director_name']
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>director_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>15</th>
      <td>Zack Snyder</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Andrew Adamson</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Joss Whedon</td>
    </tr>
  </tbody>
</table>
</div>


