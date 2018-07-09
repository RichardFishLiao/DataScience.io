
# DataFrame入门


```python
import numpy as np
```


```python
import pandas as pd
from pandas import DataFrame
#from pandas import Series,DataFrame
```


```python
import webbrowser
link = 'https://www.tiobe.com/tiobe-index/'
webbrowser.open(link)
```




    True




```python
df = pd.read_clipboard()#从粘贴板里获取
```


```python
df
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
      <th>Jul 2018</th>
      <th>Jul 2017</th>
      <th>Change</th>
      <th>Programming Language</th>
      <th>Ratings</th>
      <th>Change.1</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>1</td>
      <td>NaN</td>
      <td>Java</td>
      <td>16.139%</td>
      <td>+2.37%</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
      <td>C</td>
      <td>14.662%</td>
      <td>+7.34%</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>3</td>
      <td>NaN</td>
      <td>C++</td>
      <td>7.615%</td>
      <td>+2.04%</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>4</td>
      <td>NaN</td>
      <td>Python</td>
      <td>6.361%</td>
      <td>+2.82%</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>7</td>
      <td>change</td>
      <td>Visual Basic .NET</td>
      <td>4.247%</td>
      <td>+1.20%</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>5</td>
      <td>change</td>
      <td>C#</td>
      <td>3.795%</td>
      <td>+0.28%</td>
    </tr>
    <tr>
      <th>6</th>
      <td>7</td>
      <td>6</td>
      <td>change</td>
      <td>PHP</td>
      <td>2.832%</td>
      <td>-0.26%</td>
    </tr>
    <tr>
      <th>7</th>
      <td>8</td>
      <td>8</td>
      <td>NaN</td>
      <td>JavaScript</td>
      <td>2.831%</td>
      <td>+0.22%</td>
    </tr>
    <tr>
      <th>8</th>
      <td>9</td>
      <td>-</td>
      <td>change</td>
      <td>SQL</td>
      <td>2.334%</td>
      <td>+2.33%</td>
    </tr>
    <tr>
      <th>9</th>
      <td>10</td>
      <td>18</td>
      <td>change</td>
      <td>Objective-C</td>
      <td>1.453%</td>
      <td>-0.44%</td>
    </tr>
  </tbody>
</table>
</div>




```python
type(df)#这种是一种方式的dataFrame创建
```




    pandas.core.frame.DataFrame




```python
df.columns#获取列的信息
```




    Index(['Jul 2018', 'Jul 2017', 'Change', 'Programming Language', 'Ratings',
           'Change.1'],
          dtype='object')




```python
df_new = DataFrame(df,columns = ['Programming Language','Sep 2016'])#用于过滤某一个
```


```python
df_new
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
      <th>Programming Language</th>
      <th>Sep 2016</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Java</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>C</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C++</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Python</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Visual Basic .NET</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C#</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>PHP</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>7</th>
      <td>JavaScript</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>SQL</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Objective-C</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



#DataFrame是由若干个Series组成的，可以把DataFame当成表，然后每行每列都是由Series组成的


```python
df_ne = DataFrame(df,columns = ['Programming Language','Sep 2016','Sep 2018'])
```


```python
df_new['Sep 2018'] = range(10)#添加列1 ， range(10) = np.arange(10)
```


```python
type(df_new)
```




    pandas.core.frame.DataFrame




```python
df_new
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
      <th>Programming Language</th>
      <th>Sep 2016</th>
      <th>Sep 2018</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Java</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>C</td>
      <td>NaN</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C++</td>
      <td>NaN</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Python</td>
      <td>NaN</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Visual Basic .NET</td>
      <td>NaN</td>
      <td>4</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C#</td>
      <td>NaN</td>
      <td>5</td>
    </tr>
    <tr>
      <th>6</th>
      <td>PHP</td>
      <td>NaN</td>
      <td>6</td>
    </tr>
    <tr>
      <th>7</th>
      <td>JavaScript</td>
      <td>NaN</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>SQL</td>
      <td>NaN</td>
      <td>8</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Objective-C</td>
      <td>NaN</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_new['Sep 2019'] = np.arange(10)#方法2
```


```python
df_new
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
      <th>Programming Language</th>
      <th>Sep 2016</th>
      <th>Sep 2018</th>
      <th>Sep 2019</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Java</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>C</td>
      <td>NaN</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C++</td>
      <td>NaN</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Python</td>
      <td>NaN</td>
      <td>3</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Visual Basic .NET</td>
      <td>NaN</td>
      <td>4</td>
      <td>4</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C#</td>
      <td>NaN</td>
      <td>5</td>
      <td>5</td>
    </tr>
    <tr>
      <th>6</th>
      <td>PHP</td>
      <td>NaN</td>
      <td>6</td>
      <td>6</td>
    </tr>
    <tr>
      <th>7</th>
      <td>JavaScript</td>
      <td>NaN</td>
      <td>7</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>SQL</td>
      <td>NaN</td>
      <td>8</td>
      <td>8</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Objective-C</td>
      <td>NaN</td>
      <td>9</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_new['Sep 2020'] = pd.Series(np.arange(10))#方法3
```


```python
type(df_new)
```




    pandas.core.frame.DataFrame




```python
df_new['Sep 2018'] = pd.Series([100,200],index = [1,2])
```


```python
df_new#通过index修改某一行
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
      <th>Programming Language</th>
      <th>Sep 2016</th>
      <th>Sep 2018</th>
      <th>Sep 2019</th>
      <th>Sep 2020</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Java</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>C</td>
      <td>NaN</td>
      <td>100.0</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C++</td>
      <td>NaN</td>
      <td>200.0</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Python</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Visual Basic .NET</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>4</td>
      <td>4</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C#</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5</td>
      <td>5</td>
    </tr>
    <tr>
      <th>6</th>
      <td>PHP</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6</td>
      <td>6</td>
    </tr>
    <tr>
      <th>7</th>
      <td>JavaScript</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>SQL</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>8</td>
      <td>8</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Objective-C</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
type(range(10))
```




    range




```python
type(np.arange(10))
```




    numpy.ndarray




```python
type(pd.Series(np.arange(10)))
```




    pandas.core.series.Series


