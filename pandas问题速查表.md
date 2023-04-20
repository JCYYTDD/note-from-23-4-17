```python
  import pandas as pd
```


```python
import numpy as np
```


```python
s=pd.Series([1,2,3,4,5])
s
```




    0    1
    1    2
    2    3
    3    4
    4    5
    dtype: int64




```python
arr = np.array([1,2,3,4,5])
```


```python
s=pd.Series(arr)
```


```python
print(s[0])
```

    1
    


```python
#location[)
print(s[1:3])
```

    1    2
    2    3
    dtype: int32
    


```python
s[0]=6
s
```




    0    6
    1    2
    2    3
    3    4
    4    5
    dtype: int32




```python
s.describe()
```




    count    5.000000
    mean     4.000000
    std      1.581139
    min      2.000000
    25%      3.000000
    50%      4.000000
    75%      5.000000
    max      6.000000
    dtype: float64




```python
s[s>4]
```




    0    6
    4    5
    dtype: int32




```python
s.sort_values()
```




    1    2
    2    3
    3    4
    4    5
    0    6
    dtype: int32




```python
obj=pd.Series([1,2,3,4,5],index=['ni','wo','ta','1','2'])
```


```python
obj
```




    ni    1
    wo    2
    ta    3
    1     4
    2     5
    dtype: int64




```python
obj['1']
```




    4




```python
obj['ni']
```




    1




```python
obj[['wo','ta','ni']]
```




    wo    2
    ta    3
    ni    1
    dtype: int64




```python
%timeit obj[['wo','ta','ni']]
```

    267 µs ± 41.5 µs per loop (mean ± std. dev. of 7 runs, 1,000 loops each)
    


```python
obj[obj>2]
```




    ta    3
    1     4
    2     5
    dtype: int64




```python
sdata = {'Ohio': 35000, 'Texas': 71000, 'Oregon': 16000, 'Utah': 5000}
obj3 = pd.Series(sdata)
```


```python
obj3
```




    Ohio      35000
    Texas     71000
    Oregon    16000
    Utah       5000
    dtype: int64




```python
obj4 = pd.Series(sdata, index=['California', 'Ohio', 'Oregon', 'Texas'])
```


```python
obj4
```




    California        NaN
    Ohio          35000.0
    Oregon        16000.0
    Texas         71000.0
    dtype: float64




```python
obj4.isnull()
```




    California     True
    Ohio          False
    Oregon        False
    Texas         False
    dtype: bool




```python
import pandas as pd

s1 = pd.Series([7.3, -2.5, 3.4, 1.5], index=['a', 'c', 'd', 'e'])
s2 = pd.Series([-2.1, 3.6, -1.5, 4, 3.1], index=['a', 'c', 'e', 'f', 'g'])

# 对两个Series对象进行加法运算
s3 = s1 + s2

print(s3)
```

    a    5.2
    c    1.1
    d    NaN
    e    0.0
    f    NaN
    g    NaN
    dtype: float64
    


```python
obj4.name='population'
obj4
```




    California        NaN
    Ohio          35000.0
    Oregon        16000.0
    Texas         71000.0
    Name: population, dtype: float64




```python
obj4.index.name='location'
obj4
```




    location
    California        NaN
    Ohio          35000.0
    Oregon        16000.0
    Texas         71000.0
    Name: population, dtype: float64




```python
print(obj4.index.name)
```

    location
    


```python
obj4.index=['1','2','3','4']
obj4
```




    1        NaN
    2    35000.0
    3    16000.0
    4    71000.0
    Name: population, dtype: float64




```python
data = {'name': ['Bob', 'Tom', 'Jerry', 'Alice'],
        'age': [25, 35, 20, 27],
        'height': [175.5, 180.0, 160.5, 165.0],
        'is_student': [False, False, True, True]}

df = pd.DataFrame(data)
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
      <th>name</th>
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bob</td>
      <td>25</td>
      <td>175.5</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Tom</td>
      <td>35</td>
      <td>180.0</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Jerry</td>
      <td>20</td>
      <td>160.5</td>
      <td>True</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Alice</td>
      <td>27</td>
      <td>165.0</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.head(2)
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
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Bob</td>
      <td>25</td>
      <td>175.5</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Tom</td>
      <td>35</td>
      <td>180.0</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1=pd.DataFrame(data,columns=['age','name','is_student','height'])
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
      <th>age</th>
      <th>name</th>
      <th>is_student</th>
      <th>height</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>25</td>
      <td>Bob</td>
      <td>False</td>
      <td>175.5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>35</td>
      <td>Tom</td>
      <td>False</td>
      <td>180.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>20</td>
      <td>Jerry</td>
      <td>True</td>
      <td>160.5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>27</td>
      <td>Alice</td>
      <td>True</td>
      <td>165.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#dataframe return Series
df1['name']
```




    0      Bob
    1      Tom
    2    Jerry
    3    Alice
    Name: name, dtype: object




```python
df1.age
```




    0    25
    1    35
    2    20
    3    27
    Name: age, dtype: int64




```python
df2=pd.DataFrame(data,index=['1','2','3','4'])
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
      <th>name</th>
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Bob</td>
      <td>25</td>
      <td>175.5</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Tom</td>
      <td>35</td>
      <td>180.0</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>20</td>
      <td>160.5</td>
      <td>True</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alice</td>
      <td>27</td>
      <td>165.0</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
</div>




```python
#fh ko hk 
df2.loc['1']
```




    name            Bob
    age              25
    height        175.5
    is_student    False
    Name: 1, dtype: object




```python
df2['wo']=['1','2','3','4']
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
      <th>name</th>
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
      <th>wo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Bob</td>
      <td>25</td>
      <td>175.5</td>
      <td>False</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Tom</td>
      <td>35</td>
      <td>180.0</td>
      <td>False</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>20</td>
      <td>160.5</td>
      <td>True</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alice</td>
      <td>27</td>
      <td>165.0</td>
      <td>True</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2['is_student']=np.arange(4)
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
      <th>name</th>
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
      <th>wo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Bob</td>
      <td>25</td>
      <td>175.5</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Tom</td>
      <td>35</td>
      <td>180.0</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>20</td>
      <td>160.5</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alice</td>
      <td>27</td>
      <td>165.0</td>
      <td>3</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
val=pd.Series(np.arange(2,6),index=['2','3','1','5'])

df2['io']=val
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
      <th>name</th>
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
      <th>wo</th>
      <th>io</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Bob</td>
      <td>25</td>
      <td>175.5</td>
      <td>0</td>
      <td>1</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Tom</td>
      <td>35</td>
      <td>180.0</td>
      <td>1</td>
      <td>2</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>20</td>
      <td>160.5</td>
      <td>2</td>
      <td>3</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alice</td>
      <td>27</td>
      <td>165.0</td>
      <td>3</td>
      <td>4</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2['new']=df2.height[df2.height==180.0]
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
      <th>name</th>
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
      <th>wo</th>
      <th>io</th>
      <th>new</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Bob</td>
      <td>25</td>
      <td>175.5</td>
      <td>0</td>
      <td>1</td>
      <td>4.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Tom</td>
      <td>35</td>
      <td>180.0</td>
      <td>1</td>
      <td>2</td>
      <td>2.0</td>
      <td>180.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>20</td>
      <td>160.5</td>
      <td>2</td>
      <td>3</td>
      <td>3.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alice</td>
      <td>27</td>
      <td>165.0</td>
      <td>3</td>
      <td>4</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




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
      <th>name</th>
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
      <th>wo</th>
      <th>io</th>
      <th>new</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Bob</td>
      <td>25</td>
      <td>175.5</td>
      <td>0</td>
      <td>1</td>
      <td>4.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Tom</td>
      <td>35</td>
      <td>180.0</td>
      <td>1</td>
      <td>2</td>
      <td>2.0</td>
      <td>180.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jerry</td>
      <td>20</td>
      <td>160.5</td>
      <td>2</td>
      <td>3</td>
      <td>3.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alice</td>
      <td>27</td>
      <td>165.0</td>
      <td>3</td>
      <td>4</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2.columns
```




    Index(['name', 'age', 'height', 'is_student', 'wo', 'io', 'new'], dtype='object')




```python
df2.T
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
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>name</th>
      <td>Bob</td>
      <td>Tom</td>
      <td>Jerry</td>
      <td>Alice</td>
    </tr>
    <tr>
      <th>age</th>
      <td>25</td>
      <td>35</td>
      <td>20</td>
      <td>27</td>
    </tr>
    <tr>
      <th>height</th>
      <td>175.5</td>
      <td>180.0</td>
      <td>160.5</td>
      <td>165.0</td>
    </tr>
    <tr>
      <th>is_student</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>wo</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>io</th>
      <td>4.0</td>
      <td>2.0</td>
      <td>3.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>new</th>
      <td>NaN</td>
      <td>180.0</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2.index
```




    Index(['1', '2', '3', '4'], dtype='object')




```python
df2.name
```




    1      Bob
    2      Tom
    3    Jerry
    4    Alice
    Name: name, dtype: object




```python
df2.name='wop'
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
      <th>name</th>
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
      <th>wo</th>
      <th>io</th>
      <th>new</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>wop</td>
      <td>25</td>
      <td>175.5</td>
      <td>0</td>
      <td>1</td>
      <td>4.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>wop</td>
      <td>35</td>
      <td>180.0</td>
      <td>1</td>
      <td>2</td>
      <td>2.0</td>
      <td>180.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>wop</td>
      <td>20</td>
      <td>160.5</td>
      <td>2</td>
      <td>3</td>
      <td>3.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>wop</td>
      <td>27</td>
      <td>165.0</td>
      <td>3</td>
      <td>4</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2.index.name='hh'
df2.columns.name='lx'
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
      <th>lx</th>
      <th>name</th>
      <th>age</th>
      <th>height</th>
      <th>is_student</th>
      <th>wo</th>
      <th>io</th>
      <th>new</th>
    </tr>
    <tr>
      <th>hh</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>wop</td>
      <td>25</td>
      <td>175.5</td>
      <td>0</td>
      <td>1</td>
      <td>4.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>wop</td>
      <td>35</td>
      <td>180.0</td>
      <td>1</td>
      <td>2</td>
      <td>2.0</td>
      <td>180.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>wop</td>
      <td>20</td>
      <td>160.5</td>
      <td>2</td>
      <td>3</td>
      <td>3.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>wop</td>
      <td>27</td>
      <td>165.0</td>
      <td>3</td>
      <td>4</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2.index[1]='d'
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[47], line 1
    ----> 1 df2.index[1]='d'
    

    File D:\condaen\d2l\lib\site-packages\pandas\core\indexes\base.py:5302, in Index.__setitem__(self, key, value)
       5300 @final
       5301 def __setitem__(self, key, value):
    -> 5302     raise TypeError("Index does not support mutable operations")
    

    TypeError: Index does not support mutable operations



```python
df2.index.values
```




    array(['1', '2', '3', '4'], dtype=object)




```python

sdata = {'Ohio': 35000, 'Texas': 71000, 'Oregon': 16000, 'Utah': 5000}
obj3 = pd.Series(sdata)
obj3
#obj3.reindex(range(4))

########reindex???########
```




    Ohio      35000
    Texas     71000
    Oregon    16000
    Utah       5000
    dtype: int64




```python
frame = pd.DataFrame(np.arange(9).reshape((3, 3)), index=['a', 'c', 'd'], columns=['Ohio', 'Texas', 'California'])
frame
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
      <th>Ohio</th>
      <th>Texas</th>
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>3</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
#reindex if not has it will return nan else return the  set order
frame2 = frame.reindex(['a', 'b', 'c', 'd'])
frame2
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
      <th>Ohio</th>
      <th>Texas</th>
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>b</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>c</th>
      <td>3.0</td>
      <td>4.0</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>6.0</td>
      <td>7.0</td>
      <td>8.0</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
#reindex returun new object
states=['Texas','Ohio', 'California']
frame3=frame.reindex(columns=states)
frame3
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
      <th>Texas</th>
      <th>Ohio</th>
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>1</td>
      <td>0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>4</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>7</td>
      <td>6</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame4=frame.loc[['a', 'c'], states]
frame4
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
      <th>Texas</th>
      <th>Ohio</th>
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>1</td>
      <td>0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>4</td>
      <td>3</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
#jn xy lx uj iu bi xu ir ru axis=1
frame5=frame4.drop('Ohio',axis=1)
frame5
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
      <th>Texas</th>
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>4</td>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame5.drop('Texas',axis=1,inplace=True)
frame5
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
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>




```python
#loc只能先行后列，并且都需要用中括号索引
frame.loc[['a'],['Texas']]
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
      <th>Texas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame
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
      <th>Ohio</th>
      <th>Texas</th>
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>3</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
#iloc是用数字进行索引
frame.iloc[[0,1,2],[2]]
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
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame.iloc[:,[2]][frame.California>=5]
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
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>c</th>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
ser=pd.Series(np.arange(6))
ser
```




    0    0
    1    1
    2    2
    3    3
    4    4
    5    5
    dtype: int32




```python
ser[:1]
```




    0    0
    dtype: int32




```python
#两者输出结果不同。ser.loc[:1]会包括索引值为1的这个元素，而ser[:1]不会包括索引值为1的这个元素，这是因为loc操作是基于标签索引的，而[]操作是基于位置索引的
ser.loc[:1]
```




    0    0
    1    1
    dtype: int32




```python
#也是基于位置不包括 最后一项 右开
ser.iloc[:1]
```




    0    0
    dtype: int32




```python
frame
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
      <th>Ohio</th>
      <th>Texas</th>
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>3</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame2=frame
frame2
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
      <th>Ohio</th>
      <th>Texas</th>
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>c</th>
      <td>3</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>d</th>
      <td>6</td>
      <td>7</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame3=frame2.add(frame)
```


```python
df1=pd.DataFrame(np.arange(12.).resize((3,4)),index=['1','2','3'],columns=['one','two','three','four'])
df1
#应该是reshape 而不是resize
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
      <th>one</th>
      <th>two</th>
      <th>three</th>
      <th>four</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1 = pd.DataFrame(np.arange(9.).reshape((3, 3)),
columns=list('bcd'),
 index=['Ohio', 'Texas',
'Colorado'])
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
      <th>b</th>
      <th>c</th>
      <th>d</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Ohio</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>Texas</th>
      <td>3.0</td>
      <td>4.0</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>Colorado</th>
      <td>6.0</td>
      <td>7.0</td>
      <td>8.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1=pd.DataFrame(np.arange(12.).reshape((3,4)),index=['1','2','3'],columns=['one','two','three','four'])
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
      <th>one</th>
      <th>two</th>
      <th>three</th>
      <th>four</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>2.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.0</td>
      <td>5.0</td>
      <td>6.0</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2=pd.DataFrame(np.arange(12.).reshape(3,4),index=['1','3','4'],columns=['one','two','three','four'])
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
      <th>one</th>
      <th>two</th>
      <th>three</th>
      <th>four</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>2.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.0</td>
      <td>5.0</td>
      <td>6.0</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1+df2
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
      <th>one</th>
      <th>two</th>
      <th>three</th>
      <th>four</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0.0</td>
      <td>2.0</td>
      <td>4.0</td>
      <td>6.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>12.0</td>
      <td>14.0</td>
      <td>16.0</td>
      <td>18.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1.rdiv(1)
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
      <th>one</th>
      <th>two</th>
      <th>three</th>
      <th>four</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>inf</td>
      <td>1.000000</td>
      <td>0.500000</td>
      <td>0.333333</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.250</td>
      <td>0.200000</td>
      <td>0.166667</td>
      <td>0.142857</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.125</td>
      <td>0.111111</td>
      <td>0.100000</td>
      <td>0.090909</td>
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
      <th>one</th>
      <th>two</th>
      <th>three</th>
      <th>four</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>2.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.0</td>
      <td>5.0</td>
      <td>6.0</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
se1=pd.Series(np.arange(3),index=['1','2','3'])
se1
```




    1    0
    2    1
    3    2
    dtype: int32




```python

```


```python
#Series也是把他看作列，列表要对应才能广播想减
```


```python
df1-se1
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
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>four</th>
      <th>one</th>
      <th>three</th>
      <th>two</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
series2 = pd.Series(range(3), index=['b', 'e', 'f'])
```


```python

```


```python
frame = pd.DataFrame(np.arange(12.).reshape((4, 3)), columns=list('bde'),index=['Utah', 'Ohio', 'Texas', 'Oregon'])

```


```python
frame
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
      <th>b</th>
      <th>d</th>
      <th>e</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Utah</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>Ohio</th>
      <td>3.0</td>
      <td>4.0</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>Texas</th>
      <td>6.0</td>
      <td>7.0</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>Oregon</th>
      <td>9.0</td>
      <td>10.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
series2
```




    b    0
    e    1
    f    2
    dtype: int64




```python
res=frame-series2
res
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
      <th>b</th>
      <th>d</th>
      <th>e</th>
      <th>f</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Utah</th>
      <td>0.0</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Ohio</th>
      <td>3.0</td>
      <td>NaN</td>
      <td>4.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Texas</th>
      <td>6.0</td>
      <td>NaN</td>
      <td>7.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>Oregon</th>
      <td>9.0</td>
      <td>NaN</td>
      <td>10.0</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python

```


```python

```


```python
res.fillna(-1)
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
      <th>b</th>
      <th>d</th>
      <th>e</th>
      <th>f</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Utah</th>
      <td>0.0</td>
      <td>-1.0</td>
      <td>1.0</td>
      <td>-1.0</td>
    </tr>
    <tr>
      <th>Ohio</th>
      <td>3.0</td>
      <td>-1.0</td>
      <td>4.0</td>
      <td>-1.0</td>
    </tr>
    <tr>
      <th>Texas</th>
      <td>6.0</td>
      <td>-1.0</td>
      <td>7.0</td>
      <td>-1.0</td>
    </tr>
    <tr>
      <th>Oregon</th>
      <td>9.0</td>
      <td>-1.0</td>
      <td>10.0</td>
      <td>-1.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
res=res['e']
res
```




    Utah       1.0
    Ohio       4.0
    Texas      7.0
    Oregon    10.0
    Name: e, dtype: float64




```python
frame
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
      <th>b</th>
      <th>d</th>
      <th>e</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Utah</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>Ohio</th>
      <td>3.0</td>
      <td>4.0</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>Texas</th>
      <td>6.0</td>
      <td>7.0</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>Oregon</th>
      <td>9.0</td>
      <td>10.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#默认在列上匹配在行上广播
#若想在行上匹配，在列上广播使用DataFrame.sub传参
frame=frame.T
frame
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
se1=pd.Series(np.arange(3),index=['b','a','e'])
se1
```




    b    0
    a    1
    e    2
    dtype: int32




```python
#行上匹配，列上传播 axis=0 or axis='index'
frame1=frame1.sub(se1,axis=0)
frame1
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>e</th>
      <td>-2.0</td>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#原位值修改
np.abs(frame)
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
f=lambda x :x.max()-x.min()
```


```python
res=frame.apply(f ,axis='index')
res
```




    Utah      2.0
    Ohio      2.0
    Texas     2.0
    Oregon    2.0
    dtype: float64




```python
format=lambda x :'%.2f'%x
```


```python

```


```python
frame
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
#进行格式修改要使用applymap
res=frame.applymap(format)
res
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.00</td>
      <td>3.00</td>
      <td>6.00</td>
      <td>9.00</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.00</td>
      <td>4.00</td>
      <td>7.00</td>
      <td>10.00</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.00</td>
      <td>5.00</td>
      <td>8.00</td>
      <td>11.00</td>
    </tr>
  </tbody>
</table>
</div>




```python
#只有series有map方法DataFrame没有
#dataframe使用applymap
res=frame.loc[['b'],:].applymap(format)
res
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.00</td>
      <td>3.00</td>
      <td>6.00</td>
      <td>9.00</td>
    </tr>
  </tbody>
</table>
</div>




```python
res=frame['Texas'].map(format)
res
```




    b    6.00
    d    7.00
    e    8.00
    Name: Texas, dtype: object




```python
frame
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
newf=frame.reindex(['e','b','d'])
```


```python
newf
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
frame.reindex(['Ohio','Oregon','Texas','Utah'],axis=1)

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
      <th>Ohio</th>
      <th>Oregon</th>
      <th>Texas</th>
      <th>Utah</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>3.0</td>
      <td>9.0</td>
      <td>6.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>4.0</td>
      <td>10.0</td>
      <td>7.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>5.0</td>
      <td>11.0</td>
      <td>8.0</td>
      <td>2.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
newf.sort_values('Utah',ascending=True)
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
data = {'name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
        'score': [90, 80, 70, 80, 95]}
df = pd.DataFrame(data)
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
      <th>name</th>
      <th>score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alice</td>
      <td>90</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Bob</td>
      <td>80</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Charlie</td>
      <td>70</td>
    </tr>
    <tr>
      <th>3</th>
      <td>David</td>
      <td>80</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Eva</td>
      <td>95</td>
    </tr>
  </tbody>
</table>
</div>




```python
#first 常用
#ascending=False 从上到下降序排列
#key:rank 排序 
df['rank']=df['score'].rank(method='first',ascending=False)
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
      <th>name</th>
      <th>score</th>
      <th>score_rank</th>
      <th>rank</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alice</td>
      <td>90</td>
      <td>2.0</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Bob</td>
      <td>80</td>
      <td>3.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Charlie</td>
      <td>70</td>
      <td>5.0</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>David</td>
      <td>80</td>
      <td>3.0</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Eva</td>
      <td>95</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
import pandas as pd

data = {'name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
        'score': [90, 80, 70, 80, 95]}
df = pd.DataFrame(data)

# 计算每个分数的排名
df['score_rank'] = df['score'].rank(method='min', ascending=False)

print(df)
```

          name  score  score_rank
    0    Alice     90         2.0
    1      Bob     80         3.0
    2  Charlie     70         5.0
    3    David     80         3.0
    4      Eva     95         1.0
    


```python
obj = pd.Series([7, -5, 7, 4, 2, 0, 4])
obj.rank(method='first')
```




    0    6.0
    1    1.0
    2    7.0
    3    4.0
    4    3.0
    5    2.0
    6    5.0
    dtype: float64




```python
frame
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame.rank(axis='columns',ascending=False)
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>4.0</td>
      <td>3.0</td>
      <td>2.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>4.0</td>
      <td>3.0</td>
      <td>2.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>4.0</td>
      <td>3.0</td>
      <td>2.0</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
obj = pd.Series(range(5), index=['a', 'a', 'b', 'b', 'c']) 
obj.index.is_unique
```




    False




```python
obj[['a','b']]
```




    a    0
    a    1
    b    2
    b    3
    dtype: int64




```python
frame
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#axis=1 按行求和
#关键字 sum sumaxis
frame.sum(axis=1)
```




    b    18.0
    d    22.0
    e    26.0
    dtype: float64




```python
# mean skipna
frame.mean(axis=0)
```




    Utah       1.0
    Ohio       4.0
    Texas      7.0
    Oregon    10.0
    dtype: float64




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
      <th>one</th>
      <th>two</th>
      <th>three</th>
      <th>four</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>2.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.0</td>
      <td>5.0</td>
      <td>6.0</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>8.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




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
      <th>one</th>
      <th>two</th>
      <th>three</th>
      <th>four</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0.0</td>
      <td>1.0</td>
      <td>2.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.0</td>
      <td>5.0</td>
      <td>6.0</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
k=df1+df2
k
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
      <th>one</th>
      <th>two</th>
      <th>three</th>
      <th>four</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0.0</td>
      <td>2.0</td>
      <td>4.0</td>
      <td>6.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>12.0</td>
      <td>14.0</td>
      <td>16.0</td>
      <td>18.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# skipna na 行也不计入个数
k.mean(axis=0,skipna=True)
```




    one       6.0
    two       8.0
    three    10.0
    four     12.0
    dtype: float64




```python
# idxmax
k.idxmax(axis=1,skipna=True)
```




    1    four
    2     NaN
    3    four
    4     NaN
    dtype: object




```python
frame
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame.cumsum(axis=1)
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>9.0</td>
      <td>18.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>1.0</td>
      <td>5.0</td>
      <td>12.0</td>
      <td>22.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>7.0</td>
      <td>15.0</td>
      <td>26.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame.describe()
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>3.0</td>
      <td>3.0</td>
      <td>3.0</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.0</td>
      <td>3.0</td>
      <td>6.0</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>0.5</td>
      <td>3.5</td>
      <td>6.5</td>
      <td>9.5</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1.5</td>
      <td>4.5</td>
      <td>7.5</td>
      <td>10.5</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
frame.tail(1)
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>e</th>
      <td>2.0</td>
      <td>5.0</td>
      <td>8.0</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#协方差
frame.cov()
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Utah</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>Ohio</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>Texas</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>Oregon</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#相关系数
frame.corr().round(4)
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
      <th>Utah</th>
      <th>Ohio</th>
      <th>Texas</th>
      <th>Oregon</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Utah</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>Ohio</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>Texas</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>Oregon</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
frame['Utah'].cov(frame['Texas'])
```




    1.0




```python
obj = pd.Series(['orange','apple', 'banana', 'apple',  'banana'])
uniques = obj.unique()
uniques
```




    array(['orange', 'apple', 'banana'], dtype=object)




```python
obj.value_counts()
```




    apple     2
    banana    2
    orange    1
    dtype: int64




```python
obj.value_counts(sort=False)
```




    orange    1
    apple     2
    banana    2
    dtype: int64




```python
to_match = pd.Series(['c', 'a', 'b', 'b', 'c', 'a']) 
unique_vals = pd.Series(['c', 'b', 'a']) 
pd.Index(unique_vals).get_indexer(to_match)
#顺序是unique_vals，索引是to_match中的顺序

```




    array([0, 2, 1, 1, 0, 2], dtype=int64)




```python
obj = pd.Series(['a', 'b', 'c', 'd', 'e'])
mask = obj.isin(['a', 'c'])
print(mask)
```

    0     True
    1    False
    2     True
    3    False
    4    False
    dtype: bool
    


```python
data = pd.DataFrame({'Qu1': [1, 3, 4, 3, 4],
 'Qu2': [2, 3, 1, 2, 3],
'Qu3': [1, 5, 2, 4, 4]})
```


```python
#每一列值出现的次数如果没有出现则用0来填充
result = data.apply(pd.value_counts).fillna(0)
result
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
      <th>Qu1</th>
      <th>Qu2</th>
      <th>Qu3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>1.0</td>
      <td>1.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.0</td>
      <td>2.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2.0</td>
      <td>2.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2.0</td>
      <td>0.0</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python


```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python
np.ads(frame)
```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```

    Object `reshape` not found.
    


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

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
      <th>Ohio</th>
      <th>Texas</th>
      <th>California</th>
      <th>wo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>0</td>
      <td>2</td>
      <td>4</td>
      <td>1</td>
    </tr>
    <tr>
      <th>c</th>
      <td>6</td>
      <td>8</td>
      <td>10</td>
      <td>3</td>
    </tr>
    <tr>
      <th>d</th>
      <td>12</td>
      <td>14</td>
      <td>16</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python

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
      <th>Ohio</th>
      <th>Texas</th>
      <th>California</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>0</td>
      <td>3</td>
      <td>6</td>
    </tr>
    <tr>
      <th>c</th>
      <td>9</td>
      <td>12</td>
      <td>15</td>
    </tr>
    <tr>
      <th>d</th>
      <td>18</td>
      <td>21</td>
      <td>24</td>
    </tr>
  </tbody>
</table>
</div>




