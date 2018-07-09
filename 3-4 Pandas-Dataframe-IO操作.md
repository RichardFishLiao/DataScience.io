
观看cell 5 的所有方法，主要用到的是read_csv和to_csv


```python
import numpy as np
import pandas as pd
from pandas import Series,DataFrame
```


```python
import webbrowser
```


```python
link = 'http://pandas.pydata.org/pandas-docs/version/0.20/io.html'
webbrowser.open(link) #这个网站同时可以看到所有的io操作
```




    True




```python
df1 = pd.read_clipboard()
```


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
      <th>Format Type</th>
      <th>Data Description</th>
      <th>Reader</th>
      <th>Writer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>text</td>
      <td>CSV</td>
      <td>read_csv</td>
      <td>to_csv</td>
    </tr>
    <tr>
      <th>1</th>
      <td>text</td>
      <td>JSON</td>
      <td>read_json</td>
      <td>to_json</td>
    </tr>
    <tr>
      <th>2</th>
      <td>text</td>
      <td>HTML</td>
      <td>read_html</td>
      <td>to_html</td>
    </tr>
    <tr>
      <th>3</th>
      <td>text</td>
      <td>Local clipboard</td>
      <td>read_clipboard</td>
      <td>to_clipboard</td>
    </tr>
    <tr>
      <th>4</th>
      <td>binary</td>
      <td>MS Excel</td>
      <td>read_excel</td>
      <td>to_excel</td>
    </tr>
    <tr>
      <th>5</th>
      <td>binary</td>
      <td>HDF5 Format</td>
      <td>read_hdf</td>
      <td>to_hdf</td>
    </tr>
    <tr>
      <th>6</th>
      <td>binary</td>
      <td>Feather Format</td>
      <td>read_feather</td>
      <td>to_feather</td>
    </tr>
    <tr>
      <th>7</th>
      <td>binary</td>
      <td>Msgpack</td>
      <td>read_msgpack</td>
      <td>to_msgpack</td>
    </tr>
    <tr>
      <th>8</th>
      <td>binary</td>
      <td>Stata</td>
      <td>read_stata</td>
      <td>to_stata</td>
    </tr>
    <tr>
      <th>9</th>
      <td>binary</td>
      <td>SAS</td>
      <td>read_sas</td>
      <td></td>
    </tr>
    <tr>
      <th>10</th>
      <td>binary</td>
      <td>Python Pickle Format</td>
      <td>read_pickle</td>
      <td>to_pickle</td>
    </tr>
    <tr>
      <th>11</th>
      <td>SQL</td>
      <td>SQL</td>
      <td>read_sql</td>
      <td>to_sql</td>
    </tr>
    <tr>
      <th>12</th>
      <td>SQL</td>
      <td>Google Big Query</td>
      <td>read_gbq</td>
      <td>to_gbq</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1.to_clipboard()#写道粘贴板,可以用在excel操作当中
```


```python
	Format Type	Data Description	Reader	Writer
0	text	CSV	read_csv	to_csv
1	text	JSON	read_json	to_json
2	text	HTML	read_html	to_html
3	text	Local clipboard	read_clipboard	to_clipboard
4	binary	MS Excel	read_excel	to_excel
5	binary	HDF5 Format	read_hdf	to_hdf
6	binary	Feather Format	read_feather	to_feather
7	binary	Msgpack	read_msgpack	to_msgpack
8	binary	Stata	read_stata	to_stata
9	binary	SAS	read_sas	 
10	binary	Python Pickle Format	read_pickle	to_pickle
11	SQL	SQL	read_sql	to_sql
12	SQL	Google Big Query	read_gbq	to_gbq

```


      File "<ipython-input-8-191c5742a334>", line 1
        Format Type	Data Description	Reader	Writer
                  ^
    SyntaxError: invalid syntax
    



```python
df1.to_csv('df1.csv')
```


```python
ls
```

     驱动器 C 中的卷没有标签。
     卷的序列号是 D2BD-7C9F
    
     C:\Users\Administrator\Data science I 的目录
    
    2018/06/29 周五  16:47    <DIR>          .
    2018/06/29 周五  16:47    <DIR>          ..
    2018/06/29 周五  16:42    <DIR>          .ipynb_checkpoints
    2018/06/29 周五  11:17                15 1.pkl
    2018/06/29 周五  11:19             9,272 array的input和output.ipynb
    2018/06/29 周五  16:46            12,374 DataFrame IO.ipynb
    2018/06/29 周五  16:47               539 df1.csv
    2018/06/28 周四  21:57             8,133 Numpy_array.ipynb
    2018/06/29 周五  10:33               168 one_array.npy
    2018/06/29 周五  16:25            25,694 pandas_dataframe.ipynb
    2018/06/29 周五  14:19             8,240 Pandas_Series.ipynb
    2018/06/29 周五  11:16                 0 three_array.pkl
    2018/06/29 周五  10:36               570 two_array.npz
    2018/06/29 周五  16:24                72 Untitled.ipynb
    2018/06/29 周五  16:26                72 Untitled1.ipynb
    2018/06/29 周五  10:33               195 x.pkl
    2018/06/29 周五  16:42            14,005 深入理解Series和dataframe.ipynb
    2018/06/29 周五  10:22            16,606 数组与矩阵运算.ipynb
                  15 个文件         95,955 字节
                   3 个目录 43,439,800,320 可用字节
    


```python
!more df1.csv
```

    ,Format Type,Data Description,Reader,Writer
    0,text,CSV,read_csv,to_csv
    1,text,JSON,read_json,to_json
    2,text,HTML,read_html,to_html
    3,text,Local clipboard,read_clipboard,to_clipboard
    4,binary,MS Excel,read_excel,to_excel
    5,binary,HDF5 Format,read_hdf,to_hdf
    6,binary,Feather Format,read_feather,to_feather
    7,binary,Msgpack,read_msgpack,to_msgpack
    8,binary,Stata,read_stata,to_stata
    9,binary,SAS,read_sas, 
    10,binary,Python Pickle Format,read_pickle,to_pickle
    11,SQL,SQL,read_sql,to_sql
    12,SQL,Google Big Query,read_gbq,to_gbq
    


```python
df1.to_csv('df2.csv', index = 'false')
```


```python
!more df2.csv
```

    ,Format Type,Data Description,Reader,Writer
    0,text,CSV,read_csv,to_csv
    1,text,JSON,read_json,to_json
    2,text,HTML,read_html,to_html
    3,text,Local clipboard,read_clipboard,to_clipboard
    4,binary,MS Excel,read_excel,to_excel
    5,binary,HDF5 Format,read_hdf,to_hdf
    6,binary,Feather Format,read_feather,to_feather
    7,binary,Msgpack,read_msgpack,to_msgpack
    8,binary,Stata,read_stata,to_stata
    9,binary,SAS,read_sas, 
    10,binary,Python Pickle Format,read_pickle,to_pickle
    11,SQL,SQL,read_sql,to_sql
    12,SQL,Google Big Query,read_gbq,to_gbq
    


```python
df1.to_csv('df1.csv',index=False)#消除index
```


```python
!more df1.csv
```

    Format Type,Data Description,Reader,Writer
    text,CSV,read_csv,to_csv
    text,JSON,read_json,to_json
    text,HTML,read_html,to_html
    text,Local clipboard,read_clipboard,to_clipboard
    binary,MS Excel,read_excel,to_excel
    binary,HDF5 Format,read_hdf,to_hdf
    binary,Feather Format,read_feather,to_feather
    binary,Msgpack,read_msgpack,to_msgpack
    binary,Stata,read_stata,to_stata
    binary,SAS,read_sas, 
    binary,Python Pickle Format,read_pickle,to_pickle
    SQL,SQL,read_sql,to_sql
    SQL,Google Big Query,read_gbq,to_gbq
    

DataFrame的读取


```python
df2 = pd.read_csv('df1.csv')
```


```python
df2
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
      <th>Format Type</th>
      <th>Data Description</th>
      <th>Reader</th>
      <th>Writer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>text</td>
      <td>CSV</td>
      <td>read_csv</td>
      <td>to_csv</td>
    </tr>
    <tr>
      <th>1</th>
      <td>text</td>
      <td>JSON</td>
      <td>read_json</td>
      <td>to_json</td>
    </tr>
    <tr>
      <th>2</th>
      <td>text</td>
      <td>HTML</td>
      <td>read_html</td>
      <td>to_html</td>
    </tr>
    <tr>
      <th>3</th>
      <td>text</td>
      <td>Local clipboard</td>
      <td>read_clipboard</td>
      <td>to_clipboard</td>
    </tr>
    <tr>
      <th>4</th>
      <td>binary</td>
      <td>MS Excel</td>
      <td>read_excel</td>
      <td>to_excel</td>
    </tr>
    <tr>
      <th>5</th>
      <td>binary</td>
      <td>HDF5 Format</td>
      <td>read_hdf</td>
      <td>to_hdf</td>
    </tr>
    <tr>
      <th>6</th>
      <td>binary</td>
      <td>Feather Format</td>
      <td>read_feather</td>
      <td>to_feather</td>
    </tr>
    <tr>
      <th>7</th>
      <td>binary</td>
      <td>Msgpack</td>
      <td>read_msgpack</td>
      <td>to_msgpack</td>
    </tr>
    <tr>
      <th>8</th>
      <td>binary</td>
      <td>Stata</td>
      <td>read_stata</td>
      <td>to_stata</td>
    </tr>
    <tr>
      <th>9</th>
      <td>binary</td>
      <td>SAS</td>
      <td>read_sas</td>
      <td></td>
    </tr>
    <tr>
      <th>10</th>
      <td>binary</td>
      <td>Python Pickle Format</td>
      <td>read_pickle</td>
      <td>to_pickle</td>
    </tr>
    <tr>
      <th>11</th>
      <td>SQL</td>
      <td>SQL</td>
      <td>read_sql</td>
      <td>to_sql</td>
    </tr>
    <tr>
      <th>12</th>
      <td>SQL</td>
      <td>Google Big Query</td>
      <td>read_gbq</td>
      <td>to_gbq</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1.to_json()
```




    '{"Format Type":{"0":"text","1":"text","2":"text","3":"text","4":"binary","5":"binary","6":"binary","7":"binary","8":"binary","9":"binary","10":"binary","11":"SQL","12":"SQL"},"Data Description":{"0":"CSV","1":"JSON","2":"HTML","3":"Local clipboard","4":"MS Excel","5":"HDF5 Format","6":"Feather Format","7":"Msgpack","8":"Stata","9":"SAS","10":"Python Pickle Format","11":"SQL","12":"Google Big Query"},"Reader":{"0":"read_csv","1":"read_json","2":"read_html","3":"read_clipboard","4":"read_excel","5":"read_hdf","6":"read_feather","7":"read_msgpack","8":"read_stata","9":"read_sas","10":"read_pickle","11":"read_sql","12":"read_gbq"},"Writer":{"0":"to_csv","1":"to_json","2":"to_html","3":"to_clipboard","4":"to_excel","5":"to_hdf","6":"to_feather","7":"to_msgpack","8":"to_stata","9":" ","10":"to_pickle","11":"to_sql","12":"to_gbq"}}'




```python
pd.read_json(df1.to_json())
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
      <th>Data Description</th>
      <th>Format Type</th>
      <th>Reader</th>
      <th>Writer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>CSV</td>
      <td>text</td>
      <td>read_csv</td>
      <td>to_csv</td>
    </tr>
    <tr>
      <th>1</th>
      <td>JSON</td>
      <td>text</td>
      <td>read_json</td>
      <td>to_json</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Python Pickle Format</td>
      <td>binary</td>
      <td>read_pickle</td>
      <td>to_pickle</td>
    </tr>
    <tr>
      <th>11</th>
      <td>SQL</td>
      <td>SQL</td>
      <td>read_sql</td>
      <td>to_sql</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Google Big Query</td>
      <td>SQL</td>
      <td>read_gbq</td>
      <td>to_gbq</td>
    </tr>
    <tr>
      <th>2</th>
      <td>HTML</td>
      <td>text</td>
      <td>read_html</td>
      <td>to_html</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Local clipboard</td>
      <td>text</td>
      <td>read_clipboard</td>
      <td>to_clipboard</td>
    </tr>
    <tr>
      <th>4</th>
      <td>MS Excel</td>
      <td>binary</td>
      <td>read_excel</td>
      <td>to_excel</td>
    </tr>
    <tr>
      <th>5</th>
      <td>HDF5 Format</td>
      <td>binary</td>
      <td>read_hdf</td>
      <td>to_hdf</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Feather Format</td>
      <td>binary</td>
      <td>read_feather</td>
      <td>to_feather</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Msgpack</td>
      <td>binary</td>
      <td>read_msgpack</td>
      <td>to_msgpack</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Stata</td>
      <td>binary</td>
      <td>read_stata</td>
      <td>to_stata</td>
    </tr>
    <tr>
      <th>9</th>
      <td>SAS</td>
      <td>binary</td>
      <td>read_sas</td>
      <td></td>
    </tr>
  </tbody>
</table>
</div>




```python
df1.to_html()
```




    '<table border="1" class="dataframe">\n  <thead>\n    <tr style="text-align: right;">\n      <th></th>\n      <th>Format Type</th>\n      <th>Data Description</th>\n      <th>Reader</th>\n      <th>Writer</th>\n    </tr>\n  </thead>\n  <tbody>\n    <tr>\n      <th>0</th>\n      <td>text</td>\n      <td>CSV</td>\n      <td>read_csv</td>\n      <td>to_csv</td>\n    </tr>\n    <tr>\n      <th>1</th>\n      <td>text</td>\n      <td>JSON</td>\n      <td>read_json</td>\n      <td>to_json</td>\n    </tr>\n    <tr>\n      <th>2</th>\n      <td>text</td>\n      <td>HTML</td>\n      <td>read_html</td>\n      <td>to_html</td>\n    </tr>\n    <tr>\n      <th>3</th>\n      <td>text</td>\n      <td>Local clipboard</td>\n      <td>read_clipboard</td>\n      <td>to_clipboard</td>\n    </tr>\n    <tr>\n      <th>4</th>\n      <td>binary</td>\n      <td>MS Excel</td>\n      <td>read_excel</td>\n      <td>to_excel</td>\n    </tr>\n    <tr>\n      <th>5</th>\n      <td>binary</td>\n      <td>HDF5 Format</td>\n      <td>read_hdf</td>\n      <td>to_hdf</td>\n    </tr>\n    <tr>\n      <th>6</th>\n      <td>binary</td>\n      <td>Feather Format</td>\n      <td>read_feather</td>\n      <td>to_feather</td>\n    </tr>\n    <tr>\n      <th>7</th>\n      <td>binary</td>\n      <td>Msgpack</td>\n      <td>read_msgpack</td>\n      <td>to_msgpack</td>\n    </tr>\n    <tr>\n      <th>8</th>\n      <td>binary</td>\n      <td>Stata</td>\n      <td>read_stata</td>\n      <td>to_stata</td>\n    </tr>\n    <tr>\n      <th>9</th>\n      <td>binary</td>\n      <td>SAS</td>\n      <td>read_sas</td>\n      <td></td>\n    </tr>\n    <tr>\n      <th>10</th>\n      <td>binary</td>\n      <td>Python Pickle Format</td>\n      <td>read_pickle</td>\n      <td>to_pickle</td>\n    </tr>\n    <tr>\n      <th>11</th>\n      <td>SQL</td>\n      <td>SQL</td>\n      <td>read_sql</td>\n      <td>to_sql</td>\n    </tr>\n    <tr>\n      <th>12</th>\n      <td>SQL</td>\n      <td>Google Big Query</td>\n      <td>read_gbq</td>\n      <td>to_gbq</td>\n    </tr>\n  </tbody>\n</table>'




```python
ls
```

     驱动器 C 中的卷没有标签。
     卷的序列号是 D2BD-7C9F
    
     C:\Users\Administrator\Data science I 的目录
    
    2018/06/29 周五  16:52    <DIR>          .
    2018/06/29 周五  16:52    <DIR>          ..
    2018/06/29 周五  16:42    <DIR>          .ipynb_checkpoints
    2018/06/29 周五  11:17                15 1.pkl
    2018/06/29 周五  11:19             9,272 array的input和output.ipynb
    2018/06/29 周五  16:52            19,625 DataFrame IO.ipynb
    2018/06/29 周五  16:50               509 df1.csv
    2018/06/29 周五  16:49               539 df2.csv
    2018/06/28 周四  21:57             8,133 Numpy_array.ipynb
    2018/06/29 周五  10:33               168 one_array.npy
    2018/06/29 周五  16:25            25,694 pandas_dataframe.ipynb
    2018/06/29 周五  14:19             8,240 Pandas_Series.ipynb
    2018/06/29 周五  11:16                 0 three_array.pkl
    2018/06/29 周五  10:36               570 two_array.npz
    2018/06/29 周五  16:24                72 Untitled.ipynb
    2018/06/29 周五  16:26                72 Untitled1.ipynb
    2018/06/29 周五  10:33               195 x.pkl
    2018/06/29 周五  16:42            14,005 深入理解Series和dataframe.ipynb
    2018/06/29 周五  10:22            16,606 数组与矩阵运算.ipynb
                  16 个文件        103,715 字节
                   3 个目录 43,438,731,264 可用字节
    


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
      <th>Format Type</th>
      <th>Data Description</th>
      <th>Reader</th>
      <th>Writer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>text</td>
      <td>CSV</td>
      <td>read_csv</td>
      <td>to_csv</td>
    </tr>
    <tr>
      <th>1</th>
      <td>text</td>
      <td>JSON</td>
      <td>read_json</td>
      <td>to_json</td>
    </tr>
    <tr>
      <th>2</th>
      <td>text</td>
      <td>HTML</td>
      <td>read_html</td>
      <td>to_html</td>
    </tr>
    <tr>
      <th>3</th>
      <td>text</td>
      <td>Local clipboard</td>
      <td>read_clipboard</td>
      <td>to_clipboard</td>
    </tr>
    <tr>
      <th>4</th>
      <td>binary</td>
      <td>MS Excel</td>
      <td>read_excel</td>
      <td>to_excel</td>
    </tr>
    <tr>
      <th>5</th>
      <td>binary</td>
      <td>HDF5 Format</td>
      <td>read_hdf</td>
      <td>to_hdf</td>
    </tr>
    <tr>
      <th>6</th>
      <td>binary</td>
      <td>Feather Format</td>
      <td>read_feather</td>
      <td>to_feather</td>
    </tr>
    <tr>
      <th>7</th>
      <td>binary</td>
      <td>Msgpack</td>
      <td>read_msgpack</td>
      <td>to_msgpack</td>
    </tr>
    <tr>
      <th>8</th>
      <td>binary</td>
      <td>Stata</td>
      <td>read_stata</td>
      <td>to_stata</td>
    </tr>
    <tr>
      <th>9</th>
      <td>binary</td>
      <td>SAS</td>
      <td>read_sas</td>
      <td></td>
    </tr>
    <tr>
      <th>10</th>
      <td>binary</td>
      <td>Python Pickle Format</td>
      <td>read_pickle</td>
      <td>to_pickle</td>
    </tr>
    <tr>
      <th>11</th>
      <td>SQL</td>
      <td>SQL</td>
      <td>read_sql</td>
      <td>to_sql</td>
    </tr>
    <tr>
      <th>12</th>
      <td>SQL</td>
      <td>Google Big Query</td>
      <td>read_gbq</td>
      <td>to_gbq</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1.to_excel('df1.xlsx')
```


    ---------------------------------------------------------------------------

    ModuleNotFoundError                       Traceback (most recent call last)

    <ipython-input-31-d0f9bbdd6fda> in <module>()
    ----> 1 df1.to_excel('df1.xlsx')
    

    c:\users\administrator\appdata\local\programs\python\python36-32\lib\site-packages\pandas\core\frame.py in to_excel(self, excel_writer, sheet_name, na_rep, float_format, columns, header, index, index_label, startrow, startcol, engine, merge_cells, encoding, inf_rep, verbose, freeze_panes)
       1543         formatter.write(excel_writer, sheet_name=sheet_name, startrow=startrow,
       1544                         startcol=startcol, freeze_panes=freeze_panes,
    -> 1545                         engine=engine)
       1546 
       1547     def to_stata(self, fname, convert_dates=None, write_index=True,
    

    c:\users\administrator\appdata\local\programs\python\python36-32\lib\site-packages\pandas\io\formats\excel.py in write(self, writer, sheet_name, startrow, startcol, freeze_panes, engine)
        641             need_save = False
        642         else:
    --> 643             writer = ExcelWriter(_stringify_path(writer), engine=engine)
        644             need_save = True
        645 
    

    c:\users\administrator\appdata\local\programs\python\python36-32\lib\site-packages\pandas\io\excel.py in __init__(self, path, engine, **engine_kwargs)
        835 
        836     def __init__(self, path, engine=None, **engine_kwargs):
    --> 837         if not openpyxl_compat.is_compat(major_ver=self.openpyxl_majorver):
        838             raise ValueError('Installed openpyxl is not supported at this '
        839                              'time. Use {majorver}.x.y.'
    

    c:\users\administrator\appdata\local\programs\python\python36-32\lib\site-packages\pandas\compat\openpyxl_compat.py in is_compat(major_ver)
         25         ``False`` otherwise.
         26     """
    ---> 27     import openpyxl
         28     ver = LooseVersion(openpyxl.__version__)
         29     if major_ver == 1:
    

    ModuleNotFoundError: No module named 'openpyxl'



```python
df1.to_excel('df1.xlsx')
```


    ---------------------------------------------------------------------------

    ModuleNotFoundError                       Traceback (most recent call last)

    <ipython-input-32-d0f9bbdd6fda> in <module>()
    ----> 1 df1.to_excel('df1.xlsx')
    

    c:\users\administrator\appdata\local\programs\python\python36-32\lib\site-packages\pandas\core\frame.py in to_excel(self, excel_writer, sheet_name, na_rep, float_format, columns, header, index, index_label, startrow, startcol, engine, merge_cells, encoding, inf_rep, verbose, freeze_panes)
       1543         formatter.write(excel_writer, sheet_name=sheet_name, startrow=startrow,
       1544                         startcol=startcol, freeze_panes=freeze_panes,
    -> 1545                         engine=engine)
       1546 
       1547     def to_stata(self, fname, convert_dates=None, write_index=True,
    

    c:\users\administrator\appdata\local\programs\python\python36-32\lib\site-packages\pandas\io\formats\excel.py in write(self, writer, sheet_name, startrow, startcol, freeze_panes, engine)
        641             need_save = False
        642         else:
    --> 643             writer = ExcelWriter(_stringify_path(writer), engine=engine)
        644             need_save = True
        645 
    

    c:\users\administrator\appdata\local\programs\python\python36-32\lib\site-packages\pandas\io\excel.py in __init__(self, path, engine, **engine_kwargs)
        835 
        836     def __init__(self, path, engine=None, **engine_kwargs):
    --> 837         if not openpyxl_compat.is_compat(major_ver=self.openpyxl_majorver):
        838             raise ValueError('Installed openpyxl is not supported at this '
        839                              'time. Use {majorver}.x.y.'
    

    c:\users\administrator\appdata\local\programs\python\python36-32\lib\site-packages\pandas\compat\openpyxl_compat.py in is_compat(major_ver)
         25         ``False`` otherwise.
         26     """
    ---> 27     import openpyxl
         28     ver = LooseVersion(openpyxl.__version__)
         29     if major_ver == 1:
    

    ModuleNotFoundError: No module named 'openpyxl'

