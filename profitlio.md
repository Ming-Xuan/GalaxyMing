

```python
from pulp import *
import pandas as pd
import numpy as np
path="C:/Users/劉明軒/Downloads/ORA_Assignment3_P96084095_劉明軒/"
df=pd.read_excel(path+"Return.xlsx")
df.iloc[:6,:]
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
      <th>稅後淨利</th>
      <th>台積電2330</th>
      <th>鴻海2371</th>
      <th>國泰金2882</th>
      <th>富邦金2881</th>
      <th>中信金2891</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2019Q1</td>
      <td>32.3</td>
      <td>2.47</td>
      <td>11.5</td>
      <td>13.3</td>
      <td>16.2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2019Q2</td>
      <td>31.6</td>
      <td>2.59</td>
      <td>9.93</td>
      <td>12.2</td>
      <td>15.2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2019Q3</td>
      <td>31.4</td>
      <td>2.42</td>
      <td>10.8</td>
      <td>11.2</td>
      <td>11.6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2019Q4</td>
      <td>32.2</td>
      <td>2.44</td>
      <td>8.82</td>
      <td>10.7</td>
      <td>11</td>
    </tr>
    <tr>
      <th>4</th>
      <td>AVG</td>
      <td>31.875</td>
      <td>2.48</td>
      <td>10.2625</td>
      <td>11.85</td>
      <td>13.5</td>
    </tr>
    <tr>
      <th>5</th>
      <td>std_DEV</td>
      <td>0.442531</td>
      <td>0.0761577</td>
      <td>1.15638</td>
      <td>1.15036</td>
      <td>2.58457</td>
    </tr>
  </tbody>
</table>
</div>




```python
cov_matrix=df.iloc[9:,1:]
cov_matrix
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
      <th>台積電2330</th>
      <th>鴻海2371</th>
      <th>國泰金2882</th>
      <th>富邦金2881</th>
      <th>中信金2891</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9</th>
      <td>0.442531</td>
      <td>-0.00633333</td>
      <td>-0.0355833</td>
      <td>0.151667</td>
      <td>0.256667</td>
    </tr>
    <tr>
      <th>10</th>
      <td>-0.00633333</td>
      <td>0.0761577</td>
      <td>-0.005875</td>
      <td>0.02725</td>
      <td>0.0935</td>
    </tr>
    <tr>
      <th>11</th>
      <td>-0.0355833</td>
      <td>-0.0059</td>
      <td>1.15638</td>
      <td>0.995833</td>
      <td>1.787</td>
    </tr>
    <tr>
      <th>12</th>
      <td>0.151667</td>
      <td>0.02725</td>
      <td>0.995833</td>
      <td>1.15036</td>
      <td>2.87333</td>
    </tr>
    <tr>
      <th>13</th>
      <td>0.256667</td>
      <td>0.0935</td>
      <td>1.787</td>
      <td>2.87333</td>
      <td>2.58457</td>
    </tr>
  </tbody>
</table>
</div>




```python
prob = LpProblem("Portolio Problem", LpMinimize)
stock={'x1','x2','x3','x4','x5'}
stock= LpVariable.dicts("percent",stock, 0)
prob += lpSum(cov_matrix.iloc[0,0]*stock['x1']+cov_matrix.iloc[1,0]*stock['x2']+cov_matrix.iloc[2,0]*stock['x3']+cov_matrix.iloc[3,0]*stock['x4']
             +cov_matrix.iloc[4,0]*stock['x5']+cov_matrix.iloc[0,1]*stock['x1']+cov_matrix.iloc[1,1]*stock['x2']+cov_matrix.iloc[2,1]*stock['x3']+cov_matrix.iloc[3,1]*stock['x4']
             +cov_matrix.iloc[4,1]*stock['x5']+cov_matrix.iloc[0,2]*stock['x1']+cov_matrix.iloc[1,2]*stock['x2']+cov_matrix.iloc[2,2]*stock['x3']+cov_matrix.iloc[3,2]*stock['x4']
             +cov_matrix.iloc[4,2]*stock['x5']+cov_matrix.iloc[0,3]*stock['x1']+cov_matrix.iloc[1,3]*stock['x2']+cov_matrix.iloc[2,3]*stock['x3']+cov_matrix.iloc[3,3]*stock['x4']
             +cov_matrix.iloc[4,3]*stock['x5']+cov_matrix.iloc[0,4]*stock['x1']+cov_matrix.iloc[1,4]*stock['x2']+cov_matrix.iloc[2,4]*stock['x3']+cov_matrix.iloc[3,4]*stock['x4']
             +cov_matrix.iloc[4,4]*stock['x5'])
prob+=lpSum(31.875*stock['x1']+2.48*stock['x2']+10.2625*stock['x3']+11.85*stock['x4']+13.5*stock['x5'])>=7
prob+=lpSum(stock[i] for i in stock)==1
prob
```




    Portolio Problem:
    MINIMIZE
    0.8089472682450505*percent_x1 + 0.18469939772530608*percent_x2 + 3.897734451642269*percent_x3 + 5.198445595115826*percent_x4 + 7.595069596664011*percent_x5 + 0.0
    SUBJECT TO
    _C1: 31.875 percent_x1 + 2.48 percent_x2 + 10.2625 percent_x3
     + 11.85 percent_x4 + 13.5 percent_x5 >= 7
    
    _C2: percent_x1 + percent_x2 + percent_x3 + percent_x4 + percent_x5 = 1
    
    VARIABLES
    percent_x1 Continuous
    percent_x2 Continuous
    percent_x3 Continuous
    percent_x4 Continuous
    percent_x5 Continuous




```python
#查看目前解的狀態
prob.solve()
print("Status:", LpStatus[prob.status])


#印出解及目標值
for v in prob.variables():
    print(v.name, "=", v.varValue)
#     print('obj=',value(prob.objective))
#解的另一種方式
# for i in Ingredients:
#   print(ingredient_vars[i],"=",ingredient_vars[i].value())
```

    Status: Optimal
    percent_x1 = 0.15376765
    percent_x2 = 0.84623235
    percent_x3 = 0.0
    percent_x4 = 0.0
    percent_x5 = 0.0
    


```python

```


```python

```


```python

```


```python

```
