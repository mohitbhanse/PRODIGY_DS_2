# Data cleaning and Exploratory data analysis (EDA)


```python
import pandas as pd
import matplotlib.pyplot as plt
```


```python
titanic = pd.read_csv(r"C:\Users\91992\Downloads\archive (3)\tested.csv")
```


```python
titanic.head()
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
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>892</td>
      <td>0</td>
      <td>3</td>
      <td>Kelly, Mr. James</td>
      <td>male</td>
      <td>34.5</td>
      <td>0</td>
      <td>0</td>
      <td>330911</td>
      <td>7.8292</td>
      <td>NaN</td>
      <td>Q</td>
    </tr>
    <tr>
      <th>1</th>
      <td>893</td>
      <td>1</td>
      <td>3</td>
      <td>Wilkes, Mrs. James (Ellen Needs)</td>
      <td>female</td>
      <td>47.0</td>
      <td>1</td>
      <td>0</td>
      <td>363272</td>
      <td>7.0000</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>2</th>
      <td>894</td>
      <td>0</td>
      <td>2</td>
      <td>Myles, Mr. Thomas Francis</td>
      <td>male</td>
      <td>62.0</td>
      <td>0</td>
      <td>0</td>
      <td>240276</td>
      <td>9.6875</td>
      <td>NaN</td>
      <td>Q</td>
    </tr>
    <tr>
      <th>3</th>
      <td>895</td>
      <td>0</td>
      <td>3</td>
      <td>Wirz, Mr. Albert</td>
      <td>male</td>
      <td>27.0</td>
      <td>0</td>
      <td>0</td>
      <td>315154</td>
      <td>8.6625</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>4</th>
      <td>896</td>
      <td>1</td>
      <td>3</td>
      <td>Hirvonen, Mrs. Alexander (Helga E Lindqvist)</td>
      <td>female</td>
      <td>22.0</td>
      <td>1</td>
      <td>1</td>
      <td>3101298</td>
      <td>12.2875</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
  </tbody>
</table>
</div>




```python
titanic.tail()
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
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>413</th>
      <td>1305</td>
      <td>0</td>
      <td>3</td>
      <td>Spector, Mr. Woolf</td>
      <td>male</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>A.5. 3236</td>
      <td>8.0500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>414</th>
      <td>1306</td>
      <td>1</td>
      <td>1</td>
      <td>Oliva y Ocana, Dona. Fermina</td>
      <td>female</td>
      <td>39.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17758</td>
      <td>108.9000</td>
      <td>C105</td>
      <td>C</td>
    </tr>
    <tr>
      <th>415</th>
      <td>1307</td>
      <td>0</td>
      <td>3</td>
      <td>Saether, Mr. Simon Sivertsen</td>
      <td>male</td>
      <td>38.5</td>
      <td>0</td>
      <td>0</td>
      <td>SOTON/O.Q. 3101262</td>
      <td>7.2500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>416</th>
      <td>1308</td>
      <td>0</td>
      <td>3</td>
      <td>Ware, Mr. Frederick</td>
      <td>male</td>
      <td>NaN</td>
      <td>0</td>
      <td>0</td>
      <td>359309</td>
      <td>8.0500</td>
      <td>NaN</td>
      <td>S</td>
    </tr>
    <tr>
      <th>417</th>
      <td>1309</td>
      <td>0</td>
      <td>3</td>
      <td>Peter, Master. Michael J</td>
      <td>male</td>
      <td>NaN</td>
      <td>1</td>
      <td>1</td>
      <td>2668</td>
      <td>22.3583</td>
      <td>NaN</td>
      <td>C</td>
    </tr>
  </tbody>
</table>
</div>




```python
titanic.shape
```




    (418, 12)



# this titanic dataset feature like age and cabin contains missing data value


```python
clean_df_titanic = titanic.dropna()

```


```python
clean_df_titanic.head()
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
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>12</th>
      <td>904</td>
      <td>1</td>
      <td>1</td>
      <td>Snyder, Mrs. John Pillsbury (Nelle Stevenson)</td>
      <td>female</td>
      <td>23.0</td>
      <td>1</td>
      <td>0</td>
      <td>21228</td>
      <td>82.2667</td>
      <td>B45</td>
      <td>S</td>
    </tr>
    <tr>
      <th>14</th>
      <td>906</td>
      <td>1</td>
      <td>1</td>
      <td>Chaffee, Mrs. Herbert Fuller (Carrie Constance...</td>
      <td>female</td>
      <td>47.0</td>
      <td>1</td>
      <td>0</td>
      <td>W.E.P. 5734</td>
      <td>61.1750</td>
      <td>E31</td>
      <td>S</td>
    </tr>
    <tr>
      <th>24</th>
      <td>916</td>
      <td>1</td>
      <td>1</td>
      <td>Ryerson, Mrs. Arthur Larned (Emily Maria Borie)</td>
      <td>female</td>
      <td>48.0</td>
      <td>1</td>
      <td>3</td>
      <td>PC 17608</td>
      <td>262.3750</td>
      <td>B57 B59 B63 B66</td>
      <td>C</td>
    </tr>
    <tr>
      <th>26</th>
      <td>918</td>
      <td>1</td>
      <td>1</td>
      <td>Ostby, Miss. Helene Ragnhild</td>
      <td>female</td>
      <td>22.0</td>
      <td>0</td>
      <td>1</td>
      <td>113509</td>
      <td>61.9792</td>
      <td>B36</td>
      <td>C</td>
    </tr>
    <tr>
      <th>28</th>
      <td>920</td>
      <td>0</td>
      <td>1</td>
      <td>Brady, Mr. John Bertram</td>
      <td>male</td>
      <td>41.0</td>
      <td>0</td>
      <td>0</td>
      <td>113054</td>
      <td>30.5000</td>
      <td>A21</td>
      <td>S</td>
    </tr>
  </tbody>
</table>
</div>




```python
clean_df_titanic.shape
```




    (87, 12)




```python
clean_df_titanic.tail()
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
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>404</th>
      <td>1296</td>
      <td>0</td>
      <td>1</td>
      <td>Frauenthal, Mr. Isaac Gerald</td>
      <td>male</td>
      <td>43.0</td>
      <td>1</td>
      <td>0</td>
      <td>17765</td>
      <td>27.7208</td>
      <td>D40</td>
      <td>C</td>
    </tr>
    <tr>
      <th>405</th>
      <td>1297</td>
      <td>0</td>
      <td>2</td>
      <td>Nourney, Mr. Alfred (Baron von Drachstedt")"</td>
      <td>male</td>
      <td>20.0</td>
      <td>0</td>
      <td>0</td>
      <td>SC/PARIS 2166</td>
      <td>13.8625</td>
      <td>D38</td>
      <td>C</td>
    </tr>
    <tr>
      <th>407</th>
      <td>1299</td>
      <td>0</td>
      <td>1</td>
      <td>Widener, Mr. George Dunton</td>
      <td>male</td>
      <td>50.0</td>
      <td>1</td>
      <td>1</td>
      <td>113503</td>
      <td>211.5000</td>
      <td>C80</td>
      <td>C</td>
    </tr>
    <tr>
      <th>411</th>
      <td>1303</td>
      <td>1</td>
      <td>1</td>
      <td>Minahan, Mrs. William Edward (Lillian E Thorpe)</td>
      <td>female</td>
      <td>37.0</td>
      <td>1</td>
      <td>0</td>
      <td>19928</td>
      <td>90.0000</td>
      <td>C78</td>
      <td>Q</td>
    </tr>
    <tr>
      <th>414</th>
      <td>1306</td>
      <td>1</td>
      <td>1</td>
      <td>Oliva y Ocana, Dona. Fermina</td>
      <td>female</td>
      <td>39.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17758</td>
      <td>108.9000</td>
      <td>C105</td>
      <td>C</td>
    </tr>
  </tbody>
</table>
</div>




```python
clean_df_titanic.isna().sum()
```




    PassengerId    0
    Survived       0
    Pclass         0
    Name           0
    Sex            0
    Age            0
    SibSp          0
    Parch          0
    Ticket         0
    Fare           0
    Cabin          0
    Embarked       0
    dtype: int64



# Accessing Columns and Individual Cells


```python
print(f"number of total survival in a ship : {clean_df_titanic['Survived'].sum()}")
```

    number of total survival in a ship : 44
    


```python
clean_df_titanic[clean_df_titanic['Sex'] == 'male'].count()[4]
```




    43




```python
print(f"total number of male passenger is : 43")
```

    total number of male passenger is : 43
    


```python
clean_df_titanic[clean_df_titanic['Sex'] == 'female'].count()[4]
```




    44




```python
print(f"total number of male passenger is : 44")
```

    total number of male passenger is : 44
    


```python
ls_thirty = clean_df_titanic[clean_df_titanic['Age'] <= 30]
```


```python
gr_thirty = clean_df_titanic[clean_df_titanic['Age'] >= 30]
```


```python
print(f" total number passernger whose age is less than 30 is : {clean_df_titanic[clean_df_titanic['Age'] <= 30].count()[5]}")
```

     total number passernger whose age is less than 30 is : 30
    


```python
print(f" total number passernger whose age is greater than 30 is : {clean_df_titanic[clean_df_titanic['Age'] >= 30].count()[5]}")
```

     total number passernger whose age is greater than 30 is : 61
    


```python
ls_thirty[ls_thirty['Sex'] == 'male'].count()
```




    PassengerId    15
    Survived       15
    Pclass         15
    Name           15
    Sex            15
    Age            15
    SibSp          15
    Parch          15
    Ticket         15
    Fare           15
    Cabin          15
    Embarked       15
    dtype: int64




```python
print(f"total number of male with age is less than or equal to 30 is : 15")
```

    total number of male with age is less than or equal to 30 is : 15
    


```python
ls_thirty[ls_thirty['Sex'] == 'female'].count()
```




    PassengerId    15
    Survived       15
    Pclass         15
    Name           15
    Sex            15
    Age            15
    SibSp          15
    Parch          15
    Ticket         15
    Fare           15
    Cabin          15
    Embarked       15
    dtype: int64




```python
print(f"total number of male with age is less than or equal to 30 is : 15")
```

    total number of male with age is less than or equal to 30 is : 15
    

# which means we can say that the people on ship below the age of 30 of male and female ratio is 15:15

# 


```python
gr_thirty[gr_thirty['Sex'] == 'male'].count()
```




    PassengerId    31
    Survived       31
    Pclass         31
    Name           31
    Sex            31
    Age            31
    SibSp          31
    Parch          31
    Ticket         31
    Fare           31
    Cabin          31
    Embarked       31
    dtype: int64




```python
print(f"male passenger age greater than 30 is :31")
```

    male passenger age greater than 30 is :31
    


```python
gr_thirty[gr_thirty['Sex'] == 'female'].count()
```




    PassengerId    30
    Survived       30
    Pclass         30
    Name           30
    Sex            30
    Age            30
    SibSp          30
    Parch          30
    Ticket         30
    Fare           30
    Cabin          30
    Embarked       30
    dtype: int64




```python
print(f"female passenger age greater than 30 is :30")
```

    female passenger age greater than 30 is :30
    

# passenger greater than age 30 male female ratio is also in 50:50 for 
50% are female and 50% are female

# 


```python
clean_df_titanic[clean_df_titanic['Embarked'] == 'S']
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
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>12</th>
      <td>904</td>
      <td>1</td>
      <td>1</td>
      <td>Snyder, Mrs. John Pillsbury (Nelle Stevenson)</td>
      <td>female</td>
      <td>23.0</td>
      <td>1</td>
      <td>0</td>
      <td>21228</td>
      <td>82.2667</td>
      <td>B45</td>
      <td>S</td>
    </tr>
    <tr>
      <th>14</th>
      <td>906</td>
      <td>1</td>
      <td>1</td>
      <td>Chaffee, Mrs. Herbert Fuller (Carrie Constance...</td>
      <td>female</td>
      <td>47.0</td>
      <td>1</td>
      <td>0</td>
      <td>W.E.P. 5734</td>
      <td>61.1750</td>
      <td>E31</td>
      <td>S</td>
    </tr>
    <tr>
      <th>28</th>
      <td>920</td>
      <td>0</td>
      <td>1</td>
      <td>Brady, Mr. John Bertram</td>
      <td>male</td>
      <td>41.0</td>
      <td>0</td>
      <td>0</td>
      <td>113054</td>
      <td>30.5000</td>
      <td>A21</td>
      <td>S</td>
    </tr>
    <tr>
      <th>44</th>
      <td>936</td>
      <td>1</td>
      <td>1</td>
      <td>Kimball, Mrs. Edwin Nelson Jr (Gertrude Parsons)</td>
      <td>female</td>
      <td>45.0</td>
      <td>1</td>
      <td>0</td>
      <td>11753</td>
      <td>52.5542</td>
      <td>D19</td>
      <td>S</td>
    </tr>
    <tr>
      <th>50</th>
      <td>942</td>
      <td>0</td>
      <td>1</td>
      <td>Smith, Mr. Lucien Philip</td>
      <td>male</td>
      <td>24.0</td>
      <td>1</td>
      <td>0</td>
      <td>13695</td>
      <td>60.0000</td>
      <td>C31</td>
      <td>S</td>
    </tr>
    <tr>
      <th>53</th>
      <td>945</td>
      <td>1</td>
      <td>1</td>
      <td>Fortune, Miss. Ethel Flora</td>
      <td>female</td>
      <td>28.0</td>
      <td>3</td>
      <td>2</td>
      <td>19950</td>
      <td>263.0000</td>
      <td>C23 C25 C27</td>
      <td>S</td>
    </tr>
    <tr>
      <th>57</th>
      <td>949</td>
      <td>0</td>
      <td>3</td>
      <td>Abelseth, Mr. Olaus Jorgensen</td>
      <td>male</td>
      <td>25.0</td>
      <td>0</td>
      <td>0</td>
      <td>348122</td>
      <td>7.6500</td>
      <td>F G63</td>
      <td>S</td>
    </tr>
    <tr>
      <th>69</th>
      <td>961</td>
      <td>1</td>
      <td>1</td>
      <td>Fortune, Mrs. Mark (Mary McDougald)</td>
      <td>female</td>
      <td>60.0</td>
      <td>1</td>
      <td>4</td>
      <td>19950</td>
      <td>263.0000</td>
      <td>C23 C25 C27</td>
      <td>S</td>
    </tr>
    <tr>
      <th>77</th>
      <td>969</td>
      <td>1</td>
      <td>1</td>
      <td>Cornell, Mrs. Robert Clifford (Malvina Helen L...</td>
      <td>female</td>
      <td>55.0</td>
      <td>2</td>
      <td>0</td>
      <td>11770</td>
      <td>25.7000</td>
      <td>C101</td>
      <td>S</td>
    </tr>
    <tr>
      <th>81</th>
      <td>973</td>
      <td>0</td>
      <td>1</td>
      <td>Straus, Mr. Isidor</td>
      <td>male</td>
      <td>67.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17483</td>
      <td>221.7792</td>
      <td>C55 C57</td>
      <td>S</td>
    </tr>
    <tr>
      <th>92</th>
      <td>984</td>
      <td>1</td>
      <td>1</td>
      <td>Davidson, Mrs. Thornton (Orian Hays)</td>
      <td>female</td>
      <td>27.0</td>
      <td>1</td>
      <td>2</td>
      <td>F.C. 12750</td>
      <td>52.0000</td>
      <td>B71</td>
      <td>S</td>
    </tr>
    <tr>
      <th>96</th>
      <td>988</td>
      <td>1</td>
      <td>1</td>
      <td>Cavendish, Mrs. Tyrell William (Julia Florence...</td>
      <td>female</td>
      <td>76.0</td>
      <td>1</td>
      <td>0</td>
      <td>19877</td>
      <td>78.8500</td>
      <td>C46</td>
      <td>S</td>
    </tr>
    <tr>
      <th>109</th>
      <td>1001</td>
      <td>0</td>
      <td>2</td>
      <td>Swane, Mr. George</td>
      <td>male</td>
      <td>18.5</td>
      <td>0</td>
      <td>0</td>
      <td>248734</td>
      <td>13.0000</td>
      <td>F</td>
      <td>S</td>
    </tr>
    <tr>
      <th>114</th>
      <td>1006</td>
      <td>1</td>
      <td>1</td>
      <td>Straus, Mrs. Isidor (Rosalie Ida Blun)</td>
      <td>female</td>
      <td>63.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17483</td>
      <td>221.7792</td>
      <td>C55 C57</td>
      <td>S</td>
    </tr>
    <tr>
      <th>117</th>
      <td>1009</td>
      <td>1</td>
      <td>3</td>
      <td>Sandstrom, Miss. Beatrice Irene</td>
      <td>female</td>
      <td>1.0</td>
      <td>1</td>
      <td>1</td>
      <td>PP 9549</td>
      <td>16.7000</td>
      <td>G6</td>
      <td>S</td>
    </tr>
    <tr>
      <th>156</th>
      <td>1048</td>
      <td>1</td>
      <td>1</td>
      <td>Bird, Miss. Ellen</td>
      <td>female</td>
      <td>29.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17483</td>
      <td>221.7792</td>
      <td>C97</td>
      <td>S</td>
    </tr>
    <tr>
      <th>158</th>
      <td>1050</td>
      <td>0</td>
      <td>1</td>
      <td>Borebank, Mr. John James</td>
      <td>male</td>
      <td>42.0</td>
      <td>0</td>
      <td>0</td>
      <td>110489</td>
      <td>26.5500</td>
      <td>D22</td>
      <td>S</td>
    </tr>
    <tr>
      <th>178</th>
      <td>1070</td>
      <td>1</td>
      <td>2</td>
      <td>Becker, Mrs. Allen Oliver (Nellie E Baumgardner)</td>
      <td>female</td>
      <td>36.0</td>
      <td>0</td>
      <td>3</td>
      <td>230136</td>
      <td>39.0000</td>
      <td>F4</td>
      <td>S</td>
    </tr>
    <tr>
      <th>182</th>
      <td>1074</td>
      <td>1</td>
      <td>1</td>
      <td>Marvin, Mrs. Daniel Warner (Mary Graham Carmic...</td>
      <td>female</td>
      <td>18.0</td>
      <td>1</td>
      <td>0</td>
      <td>113773</td>
      <td>53.1000</td>
      <td>D30</td>
      <td>S</td>
    </tr>
    <tr>
      <th>215</th>
      <td>1107</td>
      <td>0</td>
      <td>1</td>
      <td>Head, Mr. Christopher</td>
      <td>male</td>
      <td>42.0</td>
      <td>0</td>
      <td>0</td>
      <td>113038</td>
      <td>42.5000</td>
      <td>B11</td>
      <td>S</td>
    </tr>
    <tr>
      <th>222</th>
      <td>1114</td>
      <td>1</td>
      <td>2</td>
      <td>Cook, Mrs. (Selena Rogers)</td>
      <td>female</td>
      <td>22.0</td>
      <td>0</td>
      <td>0</td>
      <td>W./C. 14266</td>
      <td>10.5000</td>
      <td>F33</td>
      <td>S</td>
    </tr>
    <tr>
      <th>245</th>
      <td>1137</td>
      <td>0</td>
      <td>1</td>
      <td>Kenyon, Mr. Frederick R</td>
      <td>male</td>
      <td>41.0</td>
      <td>1</td>
      <td>0</td>
      <td>17464</td>
      <td>51.8625</td>
      <td>D21</td>
      <td>S</td>
    </tr>
    <tr>
      <th>287</th>
      <td>1179</td>
      <td>0</td>
      <td>1</td>
      <td>Snyder, Mr. John Pillsbury</td>
      <td>male</td>
      <td>24.0</td>
      <td>1</td>
      <td>0</td>
      <td>21228</td>
      <td>82.2667</td>
      <td>B45</td>
      <td>S</td>
    </tr>
    <tr>
      <th>293</th>
      <td>1185</td>
      <td>0</td>
      <td>1</td>
      <td>Dodge, Dr. Washington</td>
      <td>male</td>
      <td>53.0</td>
      <td>1</td>
      <td>1</td>
      <td>33638</td>
      <td>81.8583</td>
      <td>A34</td>
      <td>S</td>
    </tr>
    <tr>
      <th>305</th>
      <td>1197</td>
      <td>1</td>
      <td>1</td>
      <td>Crosby, Mrs. Edward Gifford (Catherine Elizabe...</td>
      <td>female</td>
      <td>64.0</td>
      <td>1</td>
      <td>1</td>
      <td>112901</td>
      <td>26.5500</td>
      <td>B26</td>
      <td>S</td>
    </tr>
    <tr>
      <th>306</th>
      <td>1198</td>
      <td>0</td>
      <td>1</td>
      <td>Allison, Mr. Hudson Joshua Creighton</td>
      <td>male</td>
      <td>30.0</td>
      <td>1</td>
      <td>2</td>
      <td>113781</td>
      <td>151.5500</td>
      <td>C22 C26</td>
      <td>S</td>
    </tr>
    <tr>
      <th>308</th>
      <td>1200</td>
      <td>0</td>
      <td>1</td>
      <td>Hays, Mr. Charles Melville</td>
      <td>male</td>
      <td>55.0</td>
      <td>1</td>
      <td>1</td>
      <td>12749</td>
      <td>93.5000</td>
      <td>B69</td>
      <td>S</td>
    </tr>
    <tr>
      <th>322</th>
      <td>1214</td>
      <td>0</td>
      <td>2</td>
      <td>Nesson, Mr. Israel</td>
      <td>male</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>244368</td>
      <td>13.0000</td>
      <td>F2</td>
      <td>S</td>
    </tr>
    <tr>
      <th>326</th>
      <td>1218</td>
      <td>1</td>
      <td>2</td>
      <td>Becker, Miss. Ruth Elizabeth</td>
      <td>female</td>
      <td>12.0</td>
      <td>2</td>
      <td>1</td>
      <td>230136</td>
      <td>39.0000</td>
      <td>F4</td>
      <td>S</td>
    </tr>
    <tr>
      <th>335</th>
      <td>1227</td>
      <td>0</td>
      <td>1</td>
      <td>Maguire, Mr. John Edward</td>
      <td>male</td>
      <td>30.0</td>
      <td>0</td>
      <td>0</td>
      <td>110469</td>
      <td>26.0000</td>
      <td>C106</td>
      <td>S</td>
    </tr>
    <tr>
      <th>355</th>
      <td>1247</td>
      <td>0</td>
      <td>1</td>
      <td>Julian, Mr. Henry Forbes</td>
      <td>male</td>
      <td>50.0</td>
      <td>0</td>
      <td>0</td>
      <td>113044</td>
      <td>26.0000</td>
      <td>E60</td>
      <td>S</td>
    </tr>
    <tr>
      <th>356</th>
      <td>1248</td>
      <td>1</td>
      <td>1</td>
      <td>Brown, Mrs. John Murray (Caroline Lane Lamson)</td>
      <td>female</td>
      <td>59.0</td>
      <td>2</td>
      <td>0</td>
      <td>11769</td>
      <td>51.4792</td>
      <td>C101</td>
      <td>S</td>
    </tr>
    <tr>
      <th>372</th>
      <td>1264</td>
      <td>0</td>
      <td>1</td>
      <td>Ismay, Mr. Joseph Bruce</td>
      <td>male</td>
      <td>49.0</td>
      <td>0</td>
      <td>0</td>
      <td>112058</td>
      <td>0.0000</td>
      <td>B52 B54 B56</td>
      <td>S</td>
    </tr>
    <tr>
      <th>374</th>
      <td>1266</td>
      <td>1</td>
      <td>1</td>
      <td>Dodge, Mrs. Washington (Ruth Vidaver)</td>
      <td>female</td>
      <td>54.0</td>
      <td>1</td>
      <td>1</td>
      <td>33638</td>
      <td>81.8583</td>
      <td>A34</td>
      <td>S</td>
    </tr>
    <tr>
      <th>378</th>
      <td>1270</td>
      <td>0</td>
      <td>1</td>
      <td>Hipkins, Mr. William Edward</td>
      <td>male</td>
      <td>55.0</td>
      <td>0</td>
      <td>0</td>
      <td>680</td>
      <td>50.0000</td>
      <td>C39</td>
      <td>S</td>
    </tr>
    <tr>
      <th>390</th>
      <td>1282</td>
      <td>0</td>
      <td>1</td>
      <td>Payne, Mr. Vivian Ponsonby</td>
      <td>male</td>
      <td>23.0</td>
      <td>0</td>
      <td>0</td>
      <td>12749</td>
      <td>93.5000</td>
      <td>B24</td>
      <td>S</td>
    </tr>
    <tr>
      <th>391</th>
      <td>1283</td>
      <td>1</td>
      <td>1</td>
      <td>Lines, Mrs. Ernest H (Elizabeth Lindsey James)</td>
      <td>female</td>
      <td>51.0</td>
      <td>0</td>
      <td>1</td>
      <td>PC 17592</td>
      <td>39.4000</td>
      <td>D28</td>
      <td>S</td>
    </tr>
    <tr>
      <th>395</th>
      <td>1287</td>
      <td>1</td>
      <td>1</td>
      <td>Smith, Mrs. Lucien Philip (Mary Eloise Hughes)</td>
      <td>female</td>
      <td>18.0</td>
      <td>1</td>
      <td>0</td>
      <td>13695</td>
      <td>60.0000</td>
      <td>C31</td>
      <td>S</td>
    </tr>
    <tr>
      <th>400</th>
      <td>1292</td>
      <td>1</td>
      <td>1</td>
      <td>Bonnell, Miss. Caroline</td>
      <td>female</td>
      <td>30.0</td>
      <td>0</td>
      <td>0</td>
      <td>36928</td>
      <td>164.8667</td>
      <td>C7</td>
      <td>S</td>
    </tr>
  </tbody>
</table>
</div>




```python
clean_df_titanic[clean_df_titanic['Embarked'] == 'C']
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
      <th>PassengerId</th>
      <th>Survived</th>
      <th>Pclass</th>
      <th>Name</th>
      <th>Sex</th>
      <th>Age</th>
      <th>SibSp</th>
      <th>Parch</th>
      <th>Ticket</th>
      <th>Fare</th>
      <th>Cabin</th>
      <th>Embarked</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>24</th>
      <td>916</td>
      <td>1</td>
      <td>1</td>
      <td>Ryerson, Mrs. Arthur Larned (Emily Maria Borie)</td>
      <td>female</td>
      <td>48.0</td>
      <td>1</td>
      <td>3</td>
      <td>PC 17608</td>
      <td>262.3750</td>
      <td>B57 B59 B63 B66</td>
      <td>C</td>
    </tr>
    <tr>
      <th>26</th>
      <td>918</td>
      <td>1</td>
      <td>1</td>
      <td>Ostby, Miss. Helene Ragnhild</td>
      <td>female</td>
      <td>22.0</td>
      <td>0</td>
      <td>1</td>
      <td>113509</td>
      <td>61.9792</td>
      <td>B36</td>
      <td>C</td>
    </tr>
    <tr>
      <th>34</th>
      <td>926</td>
      <td>0</td>
      <td>1</td>
      <td>Mock, Mr. Philipp Edmund</td>
      <td>male</td>
      <td>30.0</td>
      <td>1</td>
      <td>0</td>
      <td>13236</td>
      <td>57.7500</td>
      <td>C78</td>
      <td>C</td>
    </tr>
    <tr>
      <th>46</th>
      <td>938</td>
      <td>0</td>
      <td>1</td>
      <td>Chevre, Mr. Paul Romaine</td>
      <td>male</td>
      <td>45.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17594</td>
      <td>29.7000</td>
      <td>A9</td>
      <td>C</td>
    </tr>
    <tr>
      <th>48</th>
      <td>940</td>
      <td>1</td>
      <td>1</td>
      <td>Bucknell, Mrs. William Robert (Emma Eliza Ward)</td>
      <td>female</td>
      <td>60.0</td>
      <td>0</td>
      <td>0</td>
      <td>11813</td>
      <td>76.2917</td>
      <td>D15</td>
      <td>C</td>
    </tr>
    <tr>
      <th>59</th>
      <td>951</td>
      <td>1</td>
      <td>1</td>
      <td>Chaudanson, Miss. Victorine</td>
      <td>female</td>
      <td>36.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17608</td>
      <td>262.3750</td>
      <td>B61</td>
      <td>C</td>
    </tr>
    <tr>
      <th>64</th>
      <td>956</td>
      <td>0</td>
      <td>1</td>
      <td>Ryerson, Master. John Borie</td>
      <td>male</td>
      <td>13.0</td>
      <td>2</td>
      <td>2</td>
      <td>PC 17608</td>
      <td>262.3750</td>
      <td>B57 B59 B63 B66</td>
      <td>C</td>
    </tr>
    <tr>
      <th>68</th>
      <td>960</td>
      <td>0</td>
      <td>1</td>
      <td>Tucker, Mr. Gilbert Milligan Jr</td>
      <td>male</td>
      <td>31.0</td>
      <td>0</td>
      <td>0</td>
      <td>2543</td>
      <td>28.5375</td>
      <td>C53</td>
      <td>C</td>
    </tr>
    <tr>
      <th>73</th>
      <td>965</td>
      <td>0</td>
      <td>1</td>
      <td>Ovies y Rodriguez, Mr. Servando</td>
      <td>male</td>
      <td>28.5</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17562</td>
      <td>27.7208</td>
      <td>D43</td>
      <td>C</td>
    </tr>
    <tr>
      <th>74</th>
      <td>966</td>
      <td>1</td>
      <td>1</td>
      <td>Geiger, Miss. Amalie</td>
      <td>female</td>
      <td>35.0</td>
      <td>0</td>
      <td>0</td>
      <td>113503</td>
      <td>211.5000</td>
      <td>C130</td>
      <td>C</td>
    </tr>
    <tr>
      <th>75</th>
      <td>967</td>
      <td>0</td>
      <td>1</td>
      <td>Keeping, Mr. Edwin</td>
      <td>male</td>
      <td>32.5</td>
      <td>0</td>
      <td>0</td>
      <td>113503</td>
      <td>211.5000</td>
      <td>C132</td>
      <td>C</td>
    </tr>
    <tr>
      <th>100</th>
      <td>992</td>
      <td>1</td>
      <td>1</td>
      <td>Stengel, Mrs. Charles Emil Henry (Annie May Mo...</td>
      <td>female</td>
      <td>43.0</td>
      <td>1</td>
      <td>0</td>
      <td>11778</td>
      <td>55.4417</td>
      <td>C116</td>
      <td>C</td>
    </tr>
    <tr>
      <th>112</th>
      <td>1004</td>
      <td>1</td>
      <td>1</td>
      <td>Evans, Miss. Edith Corse</td>
      <td>female</td>
      <td>36.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17531</td>
      <td>31.6792</td>
      <td>A29</td>
      <td>C</td>
    </tr>
    <tr>
      <th>118</th>
      <td>1010</td>
      <td>0</td>
      <td>1</td>
      <td>Beattie, Mr. Thomson</td>
      <td>male</td>
      <td>36.0</td>
      <td>0</td>
      <td>0</td>
      <td>13050</td>
      <td>75.2417</td>
      <td>C6</td>
      <td>C</td>
    </tr>
    <tr>
      <th>122</th>
      <td>1014</td>
      <td>1</td>
      <td>1</td>
      <td>Schabert, Mrs. Paul (Emma Mock)</td>
      <td>female</td>
      <td>35.0</td>
      <td>1</td>
      <td>0</td>
      <td>13236</td>
      <td>57.7500</td>
      <td>C28</td>
      <td>C</td>
    </tr>
    <tr>
      <th>131</th>
      <td>1023</td>
      <td>0</td>
      <td>1</td>
      <td>Gracie, Col. Archibald IV</td>
      <td>male</td>
      <td>53.0</td>
      <td>0</td>
      <td>0</td>
      <td>113780</td>
      <td>28.5000</td>
      <td>C51</td>
      <td>C</td>
    </tr>
    <tr>
      <th>142</th>
      <td>1034</td>
      <td>0</td>
      <td>1</td>
      <td>Ryerson, Mr. Arthur Larned</td>
      <td>male</td>
      <td>61.0</td>
      <td>1</td>
      <td>3</td>
      <td>PC 17608</td>
      <td>262.3750</td>
      <td>B57 B59 B63 B66</td>
      <td>C</td>
    </tr>
    <tr>
      <th>150</th>
      <td>1042</td>
      <td>1</td>
      <td>1</td>
      <td>Earnshaw, Mrs. Boulton (Olive Potter)</td>
      <td>female</td>
      <td>23.0</td>
      <td>0</td>
      <td>1</td>
      <td>11767</td>
      <td>83.1583</td>
      <td>C54</td>
      <td>C</td>
    </tr>
    <tr>
      <th>166</th>
      <td>1058</td>
      <td>0</td>
      <td>1</td>
      <td>Brandeis, Mr. Emil</td>
      <td>male</td>
      <td>48.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17591</td>
      <td>50.4958</td>
      <td>B10</td>
      <td>C</td>
    </tr>
    <tr>
      <th>177</th>
      <td>1069</td>
      <td>0</td>
      <td>1</td>
      <td>Stengel, Mr. Charles Emil Henry</td>
      <td>male</td>
      <td>54.0</td>
      <td>1</td>
      <td>0</td>
      <td>11778</td>
      <td>55.4417</td>
      <td>C116</td>
      <td>C</td>
    </tr>
    <tr>
      <th>179</th>
      <td>1071</td>
      <td>1</td>
      <td>1</td>
      <td>Compton, Mrs. Alexander Taylor (Mary Eliza Ing...</td>
      <td>female</td>
      <td>64.0</td>
      <td>0</td>
      <td>2</td>
      <td>PC 17756</td>
      <td>83.1583</td>
      <td>E45</td>
      <td>C</td>
    </tr>
    <tr>
      <th>181</th>
      <td>1073</td>
      <td>0</td>
      <td>1</td>
      <td>Compton, Mr. Alexander Taylor Jr</td>
      <td>male</td>
      <td>37.0</td>
      <td>1</td>
      <td>1</td>
      <td>PC 17756</td>
      <td>83.1583</td>
      <td>E52</td>
      <td>C</td>
    </tr>
    <tr>
      <th>184</th>
      <td>1076</td>
      <td>1</td>
      <td>1</td>
      <td>Douglas, Mrs. Frederick Charles (Mary Helene B...</td>
      <td>female</td>
      <td>27.0</td>
      <td>1</td>
      <td>1</td>
      <td>PC 17558</td>
      <td>247.5208</td>
      <td>B58 B60</td>
      <td>C</td>
    </tr>
    <tr>
      <th>196</th>
      <td>1088</td>
      <td>0</td>
      <td>1</td>
      <td>Spedden, Master. Robert Douglas</td>
      <td>male</td>
      <td>6.0</td>
      <td>0</td>
      <td>2</td>
      <td>16966</td>
      <td>134.5000</td>
      <td>E34</td>
      <td>C</td>
    </tr>
    <tr>
      <th>202</th>
      <td>1094</td>
      <td>0</td>
      <td>1</td>
      <td>Astor, Col. John Jacob</td>
      <td>male</td>
      <td>47.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17757</td>
      <td>227.5250</td>
      <td>C62 C64</td>
      <td>C</td>
    </tr>
    <tr>
      <th>208</th>
      <td>1100</td>
      <td>1</td>
      <td>1</td>
      <td>Rosenbaum, Miss. Edith Louise</td>
      <td>female</td>
      <td>33.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17613</td>
      <td>27.7208</td>
      <td>A11</td>
      <td>C</td>
    </tr>
    <tr>
      <th>218</th>
      <td>1110</td>
      <td>1</td>
      <td>1</td>
      <td>Widener, Mrs. George Dunton (Eleanor Elkins)</td>
      <td>female</td>
      <td>50.0</td>
      <td>1</td>
      <td>1</td>
      <td>113503</td>
      <td>211.5000</td>
      <td>C80</td>
      <td>C</td>
    </tr>
    <tr>
      <th>234</th>
      <td>1126</td>
      <td>0</td>
      <td>1</td>
      <td>Cumings, Mr. John Bradley</td>
      <td>male</td>
      <td>39.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17599</td>
      <td>71.2833</td>
      <td>C85</td>
      <td>C</td>
    </tr>
    <tr>
      <th>236</th>
      <td>1128</td>
      <td>0</td>
      <td>1</td>
      <td>Warren, Mr. Frank Manley</td>
      <td>male</td>
      <td>64.0</td>
      <td>1</td>
      <td>0</td>
      <td>110813</td>
      <td>75.2500</td>
      <td>D37</td>
      <td>C</td>
    </tr>
    <tr>
      <th>239</th>
      <td>1131</td>
      <td>1</td>
      <td>1</td>
      <td>Douglas, Mrs. Walter Donald (Mahala Dutton)</td>
      <td>female</td>
      <td>48.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17761</td>
      <td>106.4250</td>
      <td>C86</td>
      <td>C</td>
    </tr>
    <tr>
      <th>242</th>
      <td>1134</td>
      <td>0</td>
      <td>1</td>
      <td>Spedden, Mr. Frederic Oakley</td>
      <td>male</td>
      <td>45.0</td>
      <td>1</td>
      <td>1</td>
      <td>16966</td>
      <td>134.5000</td>
      <td>E34</td>
      <td>C</td>
    </tr>
    <tr>
      <th>252</th>
      <td>1144</td>
      <td>0</td>
      <td>1</td>
      <td>Clark, Mr. Walter Miller</td>
      <td>male</td>
      <td>27.0</td>
      <td>1</td>
      <td>0</td>
      <td>13508</td>
      <td>136.7792</td>
      <td>C89</td>
      <td>C</td>
    </tr>
    <tr>
      <th>270</th>
      <td>1162</td>
      <td>0</td>
      <td>1</td>
      <td>McCaffry, Mr. Thomas Francis</td>
      <td>male</td>
      <td>46.0</td>
      <td>0</td>
      <td>0</td>
      <td>13050</td>
      <td>75.2417</td>
      <td>C6</td>
      <td>C</td>
    </tr>
    <tr>
      <th>272</th>
      <td>1164</td>
      <td>1</td>
      <td>1</td>
      <td>Clark, Mrs. Walter Miller (Virginia McDowell)</td>
      <td>female</td>
      <td>26.0</td>
      <td>1</td>
      <td>0</td>
      <td>13508</td>
      <td>136.7792</td>
      <td>C89</td>
      <td>C</td>
    </tr>
    <tr>
      <th>314</th>
      <td>1206</td>
      <td>1</td>
      <td>1</td>
      <td>White, Mrs. John Stuart (Ella Holmes)</td>
      <td>female</td>
      <td>55.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17760</td>
      <td>135.6333</td>
      <td>C32</td>
      <td>C</td>
    </tr>
    <tr>
      <th>316</th>
      <td>1208</td>
      <td>0</td>
      <td>1</td>
      <td>Spencer, Mr. William Augustus</td>
      <td>male</td>
      <td>57.0</td>
      <td>1</td>
      <td>0</td>
      <td>PC 17569</td>
      <td>146.5208</td>
      <td>B78</td>
      <td>C</td>
    </tr>
    <tr>
      <th>321</th>
      <td>1213</td>
      <td>0</td>
      <td>3</td>
      <td>Krekorian, Mr. Neshan</td>
      <td>male</td>
      <td>25.0</td>
      <td>0</td>
      <td>0</td>
      <td>2654</td>
      <td>7.2292</td>
      <td>F E57</td>
      <td>C</td>
    </tr>
    <tr>
      <th>331</th>
      <td>1223</td>
      <td>0</td>
      <td>1</td>
      <td>Dulles, Mr. William Crothers</td>
      <td>male</td>
      <td>39.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17580</td>
      <td>29.7000</td>
      <td>A18</td>
      <td>C</td>
    </tr>
    <tr>
      <th>343</th>
      <td>1235</td>
      <td>1</td>
      <td>1</td>
      <td>Cardeza, Mrs. James Warburton Martinez (Charlo...</td>
      <td>female</td>
      <td>58.0</td>
      <td>0</td>
      <td>1</td>
      <td>PC 17755</td>
      <td>512.3292</td>
      <td>B51 B53 B55</td>
      <td>C</td>
    </tr>
    <tr>
      <th>350</th>
      <td>1242</td>
      <td>1</td>
      <td>1</td>
      <td>Greenfield, Mrs. Leo David (Blanche Strouse)</td>
      <td>female</td>
      <td>45.0</td>
      <td>0</td>
      <td>1</td>
      <td>PC 17759</td>
      <td>63.3583</td>
      <td>D10 D12</td>
      <td>C</td>
    </tr>
    <tr>
      <th>364</th>
      <td>1256</td>
      <td>1</td>
      <td>1</td>
      <td>Harder, Mrs. George Achilles (Dorothy Annan)</td>
      <td>female</td>
      <td>25.0</td>
      <td>1</td>
      <td>0</td>
      <td>11765</td>
      <td>55.4417</td>
      <td>E50</td>
      <td>C</td>
    </tr>
    <tr>
      <th>371</th>
      <td>1263</td>
      <td>1</td>
      <td>1</td>
      <td>Wilson, Miss. Helen Alice</td>
      <td>female</td>
      <td>31.0</td>
      <td>0</td>
      <td>0</td>
      <td>16966</td>
      <td>134.5000</td>
      <td>E39 E41</td>
      <td>C</td>
    </tr>
    <tr>
      <th>397</th>
      <td>1289</td>
      <td>1</td>
      <td>1</td>
      <td>Frolicher-Stehli, Mrs. Maxmillian (Margaretha ...</td>
      <td>female</td>
      <td>48.0</td>
      <td>1</td>
      <td>1</td>
      <td>13567</td>
      <td>79.2000</td>
      <td>B41</td>
      <td>C</td>
    </tr>
    <tr>
      <th>404</th>
      <td>1296</td>
      <td>0</td>
      <td>1</td>
      <td>Frauenthal, Mr. Isaac Gerald</td>
      <td>male</td>
      <td>43.0</td>
      <td>1</td>
      <td>0</td>
      <td>17765</td>
      <td>27.7208</td>
      <td>D40</td>
      <td>C</td>
    </tr>
    <tr>
      <th>405</th>
      <td>1297</td>
      <td>0</td>
      <td>2</td>
      <td>Nourney, Mr. Alfred (Baron von Drachstedt")"</td>
      <td>male</td>
      <td>20.0</td>
      <td>0</td>
      <td>0</td>
      <td>SC/PARIS 2166</td>
      <td>13.8625</td>
      <td>D38</td>
      <td>C</td>
    </tr>
    <tr>
      <th>407</th>
      <td>1299</td>
      <td>0</td>
      <td>1</td>
      <td>Widener, Mr. George Dunton</td>
      <td>male</td>
      <td>50.0</td>
      <td>1</td>
      <td>1</td>
      <td>113503</td>
      <td>211.5000</td>
      <td>C80</td>
      <td>C</td>
    </tr>
    <tr>
      <th>414</th>
      <td>1306</td>
      <td>1</td>
      <td>1</td>
      <td>Oliva y Ocana, Dona. Fermina</td>
      <td>female</td>
      <td>39.0</td>
      <td>0</td>
      <td>0</td>
      <td>PC 17758</td>
      <td>108.9000</td>
      <td>C105</td>
      <td>C</td>
    </tr>
  </tbody>
</table>
</div>




```python
clean_df_titanic[clean_df_titanic['Embarked'] == 'S'].count()
```




    PassengerId    39
    Survived       39
    Pclass         39
    Name           39
    Sex            39
    Age            39
    SibSp          39
    Parch          39
    Ticket         39
    Fare           39
    Cabin          39
    Embarked       39
    dtype: int64




```python
print("out of 87 passenger 39 passenger embark thier journey from Southampton port")
```

    out of 87 passenger 39 passenger embark thier journey from Southampton port
    


```python
clean_df_titanic[clean_df_titanic['Embarked'] == 'C'].count()
```




    PassengerId    47
    Survived       47
    Pclass         47
    Name           47
    Sex            47
    Age            47
    SibSp          47
    Parch          47
    Ticket         47
    Fare           47
    Cabin          47
    Embarked       47
    dtype: int64




```python
print("out of 87 passenger 47 emnbark their journey from Cherbourg port")
```

    out of 87 passenger 47 emnbark their journey from Cherbourg port
    


```python
ls_thirty[ls_thirty['Survived'] == 0].count()
```




    PassengerId    15
    Survived       15
    Pclass         15
    Name           15
    Sex            15
    Age            15
    SibSp          15
    Parch          15
    Ticket         15
    Fare           15
    Cabin          15
    Embarked       15
    dtype: int64



50% people are surrvived below the age of 30 and 50% are dies


```python
gr_thirty[gr_thirty['Survived'] == 1].count()
```




    PassengerId    30
    Survived       30
    Pclass         30
    Name           30
    Sex            30
    Age            30
    SibSp          30
    Parch          30
    Ticket         30
    Fare           30
    Cabin          30
    Embarked       30
    dtype: int64



50% people are surrvived above the age of 30 and 50% are dies

# 65% of the passenger start thier journey from Southampton
out of total people 65% people are coming from Soutnampton port

# 

# 24% of the passenger start thier journey from Cherbourg
out of total people 24% people are coming from Cherbourg port

# 


```python
plt.figure(14,8)
plt.bar(clean_df_titanic.Sex,clean_df_titanic.Age)
plt.xlabel("passenger sex",color="green")
plt.ylabel("passenger age ",color='red')
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[118], line 1
    ----> 1 plt.figure(14,8)
          2 plt.bar(clean_df_titanic.Sex,clean_df_titanic.Age)
          3 plt.xlabel("passenger sex",color="green")
    

    File ~\anaconda3\lib\site-packages\matplotlib\_api\deprecation.py:454, in make_keyword_only.<locals>.wrapper(*args, **kwargs)
        448 if len(args) > name_idx:
        449     warn_deprecated(
        450         since, message="Passing the %(name)s %(obj_type)s "
        451         "positionally is deprecated since Matplotlib %(since)s; the "
        452         "parameter will become keyword-only %(removal)s.",
        453         name=name, obj_type=f"parameter of {func.__name__}()")
    --> 454 return func(*args, **kwargs)
    

    File ~\anaconda3\lib\site-packages\matplotlib\pyplot.py:813, in figure(num, figsize, dpi, facecolor, edgecolor, frameon, FigureClass, clear, **kwargs)
        803 if len(allnums) == max_open_warning >= 1:
        804     _api.warn_external(
        805         f"More than {max_open_warning} figures have been opened. "
        806         f"Figures created through the pyplot interface "
       (...)
        810         f"Consider using `matplotlib.pyplot.close()`.",
        811         RuntimeWarning)
    --> 813 manager = new_figure_manager(
        814     num, figsize=figsize, dpi=dpi,
        815     facecolor=facecolor, edgecolor=edgecolor, frameon=frameon,
        816     FigureClass=FigureClass, **kwargs)
        817 fig = manager.canvas.figure
        818 if fig_label:
    

    File ~\anaconda3\lib\site-packages\matplotlib\pyplot.py:383, in new_figure_manager(*args, **kwargs)
        381 """Create a new figure manager instance."""
        382 _warn_if_gui_out_of_main_thread()
    --> 383 return _get_backend_mod().new_figure_manager(*args, **kwargs)
    

    File ~\anaconda3\lib\site-packages\matplotlib_inline\backend_inline.py:27, in new_figure_manager(num, FigureClass, *args, **kwargs)
         21 def new_figure_manager(num, *args, FigureClass=Figure, **kwargs):
         22     """
         23     Return a new figure manager for a new figure instance.
         24 
         25     This function is part of the API expected by Matplotlib backends.
         26     """
    ---> 27     return new_figure_manager_given_figure(num, FigureClass(*args, **kwargs))
    

    File ~\anaconda3\lib\site-packages\matplotlib\_api\deprecation.py:454, in make_keyword_only.<locals>.wrapper(*args, **kwargs)
        448 if len(args) > name_idx:
        449     warn_deprecated(
        450         since, message="Passing the %(name)s %(obj_type)s "
        451         "positionally is deprecated since Matplotlib %(since)s; the "
        452         "parameter will become keyword-only %(removal)s.",
        453         name=name, obj_type=f"parameter of {func.__name__}()")
    --> 454 return func(*args, **kwargs)
    

    File ~\anaconda3\lib\site-packages\matplotlib\figure.py:2521, in Figure.__init__(self, figsize, dpi, facecolor, edgecolor, linewidth, frameon, subplotpars, tight_layout, constrained_layout, layout, **kwargs)
       2518 if not np.isfinite(figsize).all() or (np.array(figsize) < 0).any():
       2519     raise ValueError('figure size must be positive finite not '
       2520                      f'{figsize}')
    -> 2521 self.bbox_inches = Bbox.from_bounds(0, 0, *figsize)
       2523 self.dpi_scale_trans = Affine2D().scale(dpi)
       2524 # do not use property as it will trigger
    

    TypeError: Value after * must be an iterable, not int


# So , We can say that out of total passenger only 50% survived and other 50% are dies
# in which more are female passenger dies with more than age 30 or 40 compare to male passenger
