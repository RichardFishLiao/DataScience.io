

```python
import numpy  as np
import pandas as pd
```

创建Series方法1


```python
s1 = pd.Series([1,2,3,4])
```


```python
s1
```




    0    1
    1    2
    2    3
    3    4
    dtype: int64




```python
s1.values
```




    array([1, 2, 3, 4], dtype=int64)




```python
s1.index
```




    RangeIndex(start=0, stop=4, step=1)



创建Series方法2


```python
s2 = pd.Series(np.arange(10))
```


```python
s2
```




    0    0
    1    1
    2    2
    3    3
    4    4
    5    5
    6    6
    7    7
    8    8
    9    9
    dtype: int32



创建Series方法3


```python
s3 = pd.Series({'1':1,'2':2})
```


```python
s3
```




    1    1
    2    2
    dtype: int64




```python
s3.values
```




    array([1, 2], dtype=int64)




```python
s3.index
```




    Index(['1', '2'], dtype='object')




```python
import pandas as pd
import numpy as np
```


```python
s4= pd.Series([1,2,3,4],index=['A','B','C','D'])#如果键值的个数小于值得话那么就会报错 
```


```python
s4
```




    A    1
    B    2
    C    3
    D    4
    dtype: int64




```python
s4.values
```




    array([1, 2, 3, 4], dtype=int64)




```python
s4['A']
```




    1




```python
s4.to_dict()#Series转化成字典
```




    {'A': 1, 'B': 2, 'C': 3, 'D': 4}




```python
index_1 = ['A','B','C']
```


```python
s6 = pd.Series(s4,index = index_1)
```


```python
s6
```




    A    1
    B    2
    C    3
    dtype: int64




```python
pd.isnull(s6)
```




    A    False
    B    False
    C    False
    D    False
    dtype: bool




```python
pd.notnull(s6)
```




    A    True
    B    True
    C    True
    D    True
    dtype: bool




```python
s6.name = 'demo'
```


```python
s6
```




    A    1
    B    2
    C    3
    D    4
    Name: demo, dtype: int64




```python
s6.index.name = 'index'
```


```python
s6.index
```




    Index(['A', 'B', 'C', 'D'], dtype='object', name='index')


