
1.df1.iterrows()把dataframe转化成生成器，在想遍历数据的时候使用

2.可以把若干个Series变成数组插入DataFrame中变成DataFrame

3.df_new = df_new.T   T是转置


```python
import numpy as np
import pandas as pd
from pandas import Series,DataFrame
```


```python
data = {'Country':['Belgium','India','Brazil'],'Capital':['Brussels','New Delhi','Brasilia'],'Population':[11190846,1303171035,207847528]}
```


```python
data
```




    {'Capital': ['Brussels', 'New Delhi', 'Brasilia'],
     'Country': ['Belgium', 'India', 'Brazil'],
     'Population': [11190846, 1303171035, 207847528]}



Series


```python
s1 = pd.Series(data['Country'],index=['A','B','C'])
```


```python
s1
```




    A    Belgium
    B      India
    C     Brazil
    dtype: object




```python
s1.values
```




    array(['Belgium', 'India', 'Brazil'], dtype=object)




```python
s1.index
```




    Index(['A', 'B', 'C'], dtype='object')




```python
DataFrame
```




    pandas.core.frame.DataFrame



df1 = pd.DataFrame(data)


```python
xxx = Series()
```


```python
type(xxx
)
```




    pandas.core.series.Series




```python
df1 = DataFrame(data)#创建图表
```


```python
df1#一个dataFrame是由若干个Series组成
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
      <th>Capital</th>
      <th>Country</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Brussels</td>
      <td>Belgium</td>
      <td>11190846</td>
    </tr>
    <tr>
      <th>1</th>
      <td>New Delhi</td>
      <td>India</td>
      <td>1303171035</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Brasilia</td>
      <td>Brazil</td>
      <td>207847528</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1['Country']
```




    0    Belgium
    1      India
    2     Brazil
    Name: Country, dtype: object



把dataFrame转化成generator然后进行遍历


```python
df1.iterrows()#如果是生成器就可以遍历，就可以用for
```




    <generator object DataFrame.iterrows at 0x0A67F690>




```python
for row in df1.iterrows():
    print(row),
    print(type(row)),#返回了tuple
    print(len(row))#一共有两个元素
    #index是整型，然后其他的信息是Series
```

    (0, Capital       Brussels
    Country        Belgium
    Population    11190846
    Name: 0, dtype: object)
    <class 'tuple'>
    2
    (1, Capital        New Delhi
    Country            India
    Population    1303171035
    Name: 1, dtype: object)
    <class 'tuple'>
    2
    (2, Capital        Brasilia
    Country          Brazil
    Population    207847528
    Name: 2, dtype: object)
    <class 'tuple'>
    2
    

因此可以利用Series来创建DataFrame


```python
s1 = pd.Series(data['Capital'])
```


```python
s2= Series(data['Country'])
```


```python
s3 = Series(data['Population'])
```


```python
df_new= DataFrame([s1,s2,s3],index = ['Capital','Country','Population'])
```


```python
df_new #发现columns出现了问题
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
      <th>0</th>
      <th>1</th>
      <th>2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Capital</th>
      <td>Brussels</td>
      <td>New Delhi</td>
      <td>Brasilia</td>
    </tr>
    <tr>
      <th>Country</th>
      <td>Belgium</td>
      <td>India</td>
      <td>Brazil</td>
    </tr>
    <tr>
      <th>Population</th>
      <td>11190846</td>
      <td>1303171035</td>
      <td>207847528</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_new = df_new.T#理解成倒置
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
      <th>Capital</th>
      <th>Country</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Brussels</td>
      <td>Belgium</td>
      <td>11190846</td>
    </tr>
    <tr>
      <th>1</th>
      <td>New Delhi</td>
      <td>India</td>
      <td>1303171035</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Brasilia</td>
      <td>Brazil</td>
      <td>207847528</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1
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
      <th>Capital</th>
      <th>Country</th>
      <th>Population</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Brussels</td>
      <td>Belgium</td>
      <td>11190846</td>
    </tr>
    <tr>
      <th>1</th>
      <td>New Delhi</td>
      <td>India</td>
      <td>1303171035</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Brasilia</td>
      <td>Brazil</td>
      <td>207847528</td>
    </tr>
  </tbody>
</table>
</div>


