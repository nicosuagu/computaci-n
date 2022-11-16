```python
import os
os.getcwd()
```




    'C:\\Users\\Estudiante'




```python
import pandas as pd
import numpy as np
```


```python
plantulas1 = pd.read_excel("sample.xlsx",sheet_name=12,header=0)

```


```python
os.chdir("C:\\Users\\Estudiante\\Documents\\pyjupyter")
```


```python
print (plantulas1)

```

        Parcela  NI  Plantula  Ni  Altura
    0         3  50         1  52      12
    1         3  50         2  52      11
    2         3  50         3  52      12
    3         3  50         4  52      10
    4         3  50         5  52      13
    5         6  50         6  56      10
    6         6  50         7  56       9
    7         6  50         8  56       7
    8         6  50         9  56       9
    9         6  50        10  56       8
    10        6  50        11  56      10
    11        8  50        12  60       6
    12        8  50        13  60       5
    13        8  50        14  60       7
    14        8  50        15  60       5
    15        8  50        16  60       6
    16        8  50        17  60       4
    17       15  50        18  46       7
    18       15  50        19  46       8
    19       15  50        20  46       7
    20       15  50        21  46       7
    21       15  50        22  46       6
    22       22  50        23  49      10
    23       22  50        24  49      11
    24       22  50        25  49      13
    25       22  50        26  49      12
    26       22  50        27  49      12
    27       24  50        28  51      14
    28       24  50        29  51      15
    29       24  50        30  51      13
    30       24  50        31  51      12
    31       24  50        32  51      13
    32       30  50        33  50       6
    33       30  50        34  50       7
    34       30  50        35  50       6
    35       30  50        36  50       8
    36       30  50        37  50       7
    37       32  50        38  61       9
    38       32  50        39  61      10
    39       32  50        40  61       8
    40       32  50        41  61       9
    41       32  50        42  61       9
    42       32  50        43  61      10
    43       33  50        44  60       7
    44       33  50        45  60      10
    45       33  50        46  60       8
    46       33  50        47  60       9
    47       33  50        48  60       9
    48       33  50        49  60      10
    49       50  50        50  45      12
    50       50  50        51  45      11
    51       50  50        52  45      12
    52       50  50        53  45      13
    53       50  50        54  45      12
    54       50  50        55  45      12
    


```python
plantulas7 = pd.read_excel("sample.xlsx",sheet_name="Plantulas",header=0,usecols=[0,2,3,4],
                           names=["IdParcela","IdPlantula","N_i","Altura"],
                           dtype={"IdParcela":str,"IdPlantula":str,"Altura":np.float64})
plantulas7.info()
plantulas7.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 55 entries, 0 to 54
    Data columns (total 4 columns):
     #   Column      Non-Null Count  Dtype  
    ---  ------      --------------  -----  
     0   IdParcela   55 non-null     object 
     1   IdPlantula  55 non-null     object 
     2   N_i         55 non-null     int64  
     3   Altura      55 non-null     float64
    dtypes: float64(1), int64(1), object(2)
    memory usage: 1.8+ KB
    




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
      <th>IdParcela</th>
      <th>IdPlantula</th>
      <th>N_i</th>
      <th>Altura</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>1</td>
      <td>52</td>
      <td>12.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>2</td>
      <td>52</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>3</td>
      <td>52</td>
      <td>12.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>4</td>
      <td>52</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3</td>
      <td>5</td>
      <td>52</td>
      <td>13.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>6</td>
      <td>56</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>7</td>
      <td>56</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6</td>
      <td>8</td>
      <td>56</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>6</td>
      <td>9</td>
      <td>56</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>6</td>
      <td>10</td>
      <td>56</td>
      <td>8.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
stoks1=pd.read_table("stocks.dlm",delimiter=" ", header= 0)
```


```python
print(stoks1)
```

                 A        B      C      D      E      F           G      H
    0          IBM  01DEC05  89,15  89,92  81,56  82,20   5.976.252  81,37
    1          IBM  01NOV05  81,85  89,94  80,64  88,90   5.556.471  88,01
    2          IBM  03OCT05  80,22  84,60  78,70  81,88   7.019.666  80,86
    3          IBM  01SEP05  80,16  82,11  76,93  80,22   5.772.280  79,22
    4          IBM  01AUG05  83,00  84,20  79,87  80,62   4.801.386  79,62
    ..         ...      ...    ...    ...    ...    ...         ...    ...
    694  Microsoft  01DEC86  49,75  50,00  45,25  48,25  33.858.327   0,15
    695  Microsoft  03NOV86  39,00  51,25  39,00  49,75  57.646.989   0,15
    696  Microsoft  01OCT86  28,25  40,25  27,50  38,75  70.845.495   0,12
    697  Microsoft  02SEP86  28,50  31,50  26,25  28,25  13.824.000   0,09
    698  Microsoft  01AUG86  28,50  30,75  27,25  28,50  13.889.828   0,09
    
    [699 rows x 8 columns]
    


```python
stoks2=pd.read_table("stocks.dlm", delimiter=" ", header=0, decimal=",", thousands=".")
```


```python
stoks2.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 699 entries, 0 to 698
    Data columns (total 8 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   A       699 non-null    object 
     1   B       699 non-null    object 
     2   C       699 non-null    float64
     3   D       699 non-null    float64
     4   E       699 non-null    float64
     5   F       699 non-null    float64
     6   G       699 non-null    int64  
     7   H       699 non-null    float64
    dtypes: float64(5), int64(1), object(2)
    memory usage: 43.8+ KB
    


```python
from datetime import datetime
dateparse = lambda x: datetime.strptime(x,"%d%b%y")
```


```python
stocks3 = pd.read_table("stocks.dlm",delimiter=" ",decimal=",",thousands=".",header=0,
                        dtype={"A":str,"B":str,"C":np.float64,"D":np.float64,"E":np.float64,
                              "F":np.float64,"G":np.float64,"H":np.float64},
                        parse_dates=["B"], date_parser=dateparse)

```


```python
stocks3.info()
stocks3.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 699 entries, 0 to 698
    Data columns (total 8 columns):
     #   Column  Non-Null Count  Dtype         
    ---  ------  --------------  -----         
     0   A       699 non-null    object        
     1   B       699 non-null    datetime64[ns]
     2   C       699 non-null    float64       
     3   D       699 non-null    float64       
     4   E       699 non-null    float64       
     5   F       699 non-null    float64       
     6   G       699 non-null    float64       
     7   H       699 non-null    float64       
    dtypes: datetime64[ns](1), float64(6), object(1)
    memory usage: 43.8+ KB
    




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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
      <th>F</th>
      <th>G</th>
      <th>H</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>IBM</td>
      <td>2005-12-01</td>
      <td>89.15</td>
      <td>89.92</td>
      <td>81.56</td>
      <td>82.20</td>
      <td>5976252.0</td>
      <td>81.37</td>
    </tr>
    <tr>
      <th>1</th>
      <td>IBM</td>
      <td>2005-11-01</td>
      <td>81.85</td>
      <td>89.94</td>
      <td>80.64</td>
      <td>88.90</td>
      <td>5556471.0</td>
      <td>88.01</td>
    </tr>
    <tr>
      <th>2</th>
      <td>IBM</td>
      <td>2005-10-03</td>
      <td>80.22</td>
      <td>84.60</td>
      <td>78.70</td>
      <td>81.88</td>
      <td>7019666.0</td>
      <td>80.86</td>
    </tr>
    <tr>
      <th>3</th>
      <td>IBM</td>
      <td>2005-09-01</td>
      <td>80.16</td>
      <td>82.11</td>
      <td>76.93</td>
      <td>80.22</td>
      <td>5772280.0</td>
      <td>79.22</td>
    </tr>
    <tr>
      <th>4</th>
      <td>IBM</td>
      <td>2005-08-01</td>
      <td>83.00</td>
      <td>84.20</td>
      <td>79.87</td>
      <td>80.62</td>
      <td>4801386.0</td>
      <td>79.62</td>
    </tr>
    <tr>
      <th>5</th>
      <td>IBM</td>
      <td>2005-07-01</td>
      <td>74.30</td>
      <td>85.11</td>
      <td>74.16</td>
      <td>83.46</td>
      <td>8056590.0</td>
      <td>82.23</td>
    </tr>
    <tr>
      <th>6</th>
      <td>IBM</td>
      <td>2005-06-01</td>
      <td>75.57</td>
      <td>77.73</td>
      <td>73.45</td>
      <td>74.20</td>
      <td>6439536.0</td>
      <td>73.10</td>
    </tr>
    <tr>
      <th>7</th>
      <td>IBM</td>
      <td>2005-05-02</td>
      <td>76.88</td>
      <td>78.11</td>
      <td>72.50</td>
      <td>75.55</td>
      <td>6896904.0</td>
      <td>74.43</td>
    </tr>
    <tr>
      <th>8</th>
      <td>IBM</td>
      <td>2005-04-01</td>
      <td>91.49</td>
      <td>91.76</td>
      <td>71.85</td>
      <td>76.38</td>
      <td>10709200.0</td>
      <td>75.05</td>
    </tr>
    <tr>
      <th>9</th>
      <td>IBM</td>
      <td>2005-03-01</td>
      <td>92.64</td>
      <td>93.73</td>
      <td>89.09</td>
      <td>91.38</td>
      <td>5025627.0</td>
      <td>89.79</td>
    </tr>
  </tbody>
</table>
</div>




```python
stocks4 = pd.read_table("stocks.dlm",delimiter=" ",header=0,decimal=",",thousands=".",
                        names=["Stock","Date","Open","High","Low","Close","Volume","AdjClose"],
                        dtype={"Stock":str,"Date":str,"Open":np.float64,"High":np.float64,
                               "Low":np.float64,"Close":np.float64,"Volume":np.float64,
                               "AdjClose":np.float64},
                        parse_dates=["Date"], date_parser=dateparse)
stocks4.info()
stocks4.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 699 entries, 0 to 698
    Data columns (total 8 columns):
     #   Column    Non-Null Count  Dtype         
    ---  ------    --------------  -----         
     0   Stock     699 non-null    object        
     1   Date      699 non-null    datetime64[ns]
     2   Open      699 non-null    float64       
     3   High      699 non-null    float64       
     4   Low       699 non-null    float64       
     5   Close     699 non-null    float64       
     6   Volume    699 non-null    float64       
     7   AdjClose  699 non-null    float64       
    dtypes: datetime64[ns](1), float64(6), object(1)
    memory usage: 43.8+ KB
    




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
      <th>Stock</th>
      <th>Date</th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>AdjClose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>IBM</td>
      <td>2005-12-01</td>
      <td>89.15</td>
      <td>89.92</td>
      <td>81.56</td>
      <td>82.20</td>
      <td>5976252.0</td>
      <td>81.37</td>
    </tr>
    <tr>
      <th>1</th>
      <td>IBM</td>
      <td>2005-11-01</td>
      <td>81.85</td>
      <td>89.94</td>
      <td>80.64</td>
      <td>88.90</td>
      <td>5556471.0</td>
      <td>88.01</td>
    </tr>
    <tr>
      <th>2</th>
      <td>IBM</td>
      <td>2005-10-03</td>
      <td>80.22</td>
      <td>84.60</td>
      <td>78.70</td>
      <td>81.88</td>
      <td>7019666.0</td>
      <td>80.86</td>
    </tr>
    <tr>
      <th>3</th>
      <td>IBM</td>
      <td>2005-09-01</td>
      <td>80.16</td>
      <td>82.11</td>
      <td>76.93</td>
      <td>80.22</td>
      <td>5772280.0</td>
      <td>79.22</td>
    </tr>
    <tr>
      <th>4</th>
      <td>IBM</td>
      <td>2005-08-01</td>
      <td>83.00</td>
      <td>84.20</td>
      <td>79.87</td>
      <td>80.62</td>
      <td>4801386.0</td>
      <td>79.62</td>
    </tr>
    <tr>
      <th>5</th>
      <td>IBM</td>
      <td>2005-07-01</td>
      <td>74.30</td>
      <td>85.11</td>
      <td>74.16</td>
      <td>83.46</td>
      <td>8056590.0</td>
      <td>82.23</td>
    </tr>
    <tr>
      <th>6</th>
      <td>IBM</td>
      <td>2005-06-01</td>
      <td>75.57</td>
      <td>77.73</td>
      <td>73.45</td>
      <td>74.20</td>
      <td>6439536.0</td>
      <td>73.10</td>
    </tr>
    <tr>
      <th>7</th>
      <td>IBM</td>
      <td>2005-05-02</td>
      <td>76.88</td>
      <td>78.11</td>
      <td>72.50</td>
      <td>75.55</td>
      <td>6896904.0</td>
      <td>74.43</td>
    </tr>
    <tr>
      <th>8</th>
      <td>IBM</td>
      <td>2005-04-01</td>
      <td>91.49</td>
      <td>91.76</td>
      <td>71.85</td>
      <td>76.38</td>
      <td>10709200.0</td>
      <td>75.05</td>
    </tr>
    <tr>
      <th>9</th>
      <td>IBM</td>
      <td>2005-03-01</td>
      <td>92.64</td>
      <td>93.73</td>
      <td>89.09</td>
      <td>91.38</td>
      <td>5025627.0</td>
      <td>89.79</td>
    </tr>
  </tbody>
</table>
</div>




```python
stocks3 = pd.read_table("stocks.dlm",delimiter=" ",decimal=",",thousands=".",header=0,
                        dtype={"A":str,"B":str,"C":np.float64,"D":np.float64,"E":np.float64,
                              "F":np.float64,"G":np.float64,"H":np.float64},
                        parse_dates=["B"], date_parser=dateparse,nrows=500)
stocks3.info()
stocks3.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 500 entries, 0 to 499
    Data columns (total 8 columns):
     #   Column  Non-Null Count  Dtype         
    ---  ------  --------------  -----         
     0   A       500 non-null    object        
     1   B       500 non-null    datetime64[ns]
     2   C       500 non-null    float64       
     3   D       500 non-null    float64       
     4   E       500 non-null    float64       
     5   F       500 non-null    float64       
     6   G       500 non-null    float64       
     7   H       500 non-null    float64       
    dtypes: datetime64[ns](1), float64(6), object(1)
    memory usage: 31.4+ KB
    




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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
      <th>F</th>
      <th>G</th>
      <th>H</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>IBM</td>
      <td>2005-12-01</td>
      <td>89.15</td>
      <td>89.92</td>
      <td>81.56</td>
      <td>82.20</td>
      <td>5976252.0</td>
      <td>81.37</td>
    </tr>
    <tr>
      <th>1</th>
      <td>IBM</td>
      <td>2005-11-01</td>
      <td>81.85</td>
      <td>89.94</td>
      <td>80.64</td>
      <td>88.90</td>
      <td>5556471.0</td>
      <td>88.01</td>
    </tr>
    <tr>
      <th>2</th>
      <td>IBM</td>
      <td>2005-10-03</td>
      <td>80.22</td>
      <td>84.60</td>
      <td>78.70</td>
      <td>81.88</td>
      <td>7019666.0</td>
      <td>80.86</td>
    </tr>
    <tr>
      <th>3</th>
      <td>IBM</td>
      <td>2005-09-01</td>
      <td>80.16</td>
      <td>82.11</td>
      <td>76.93</td>
      <td>80.22</td>
      <td>5772280.0</td>
      <td>79.22</td>
    </tr>
    <tr>
      <th>4</th>
      <td>IBM</td>
      <td>2005-08-01</td>
      <td>83.00</td>
      <td>84.20</td>
      <td>79.87</td>
      <td>80.62</td>
      <td>4801386.0</td>
      <td>79.62</td>
    </tr>
    <tr>
      <th>5</th>
      <td>IBM</td>
      <td>2005-07-01</td>
      <td>74.30</td>
      <td>85.11</td>
      <td>74.16</td>
      <td>83.46</td>
      <td>8056590.0</td>
      <td>82.23</td>
    </tr>
    <tr>
      <th>6</th>
      <td>IBM</td>
      <td>2005-06-01</td>
      <td>75.57</td>
      <td>77.73</td>
      <td>73.45</td>
      <td>74.20</td>
      <td>6439536.0</td>
      <td>73.10</td>
    </tr>
    <tr>
      <th>7</th>
      <td>IBM</td>
      <td>2005-05-02</td>
      <td>76.88</td>
      <td>78.11</td>
      <td>72.50</td>
      <td>75.55</td>
      <td>6896904.0</td>
      <td>74.43</td>
    </tr>
    <tr>
      <th>8</th>
      <td>IBM</td>
      <td>2005-04-01</td>
      <td>91.49</td>
      <td>91.76</td>
      <td>71.85</td>
      <td>76.38</td>
      <td>10709200.0</td>
      <td>75.05</td>
    </tr>
    <tr>
      <th>9</th>
      <td>IBM</td>
      <td>2005-03-01</td>
      <td>92.64</td>
      <td>93.73</td>
      <td>89.09</td>
      <td>91.38</td>
      <td>5025627.0</td>
      <td>89.79</td>
    </tr>
  </tbody>
</table>
</div>



help(pd.read_table)


```python
Municipios = pd.read_excel("Municipios.xlsx",dtype={"Irural":np.float64,"Dep":str,
                                                    "Poblacion":np.float64,"Depmun":str})
Municipios.info()
Municipios.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1118 entries, 0 to 1117
    Data columns (total 8 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  1118 non-null   object 
     1   Dep           1118 non-null   object 
     2   Municipio     1118 non-null   object 
     3   Depmun        1118 non-null   object 
     4   Superficie    1117 non-null   float64
     5   Poblacion     1118 non-null   float64
     6   Irural        1118 non-null   float64
     7   Region        1118 non-null   object 
    dtypes: float64(3), object(5)
    memory usage: 70.0+ KB
    




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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ant%ioqUia</td>
      <td>05</td>
      <td>Mede&amp;l'lín</td>
      <td>05001</td>
      <td>374.830625</td>
      <td>2483545.0</td>
      <td>5.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ant%ioquia</td>
      <td>05</td>
      <td>Abej!&amp;orr*al</td>
      <td>05002</td>
      <td>507.134114</td>
      <td>20258.0</td>
      <td>45.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Ant%ioquia</td>
      <td>05</td>
      <td>A?br'&amp;iaquí</td>
      <td>05004</td>
      <td>296.955980</td>
      <td>2710.0</td>
      <td>58.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ant%io&gt;qUia</td>
      <td>05</td>
      <td>Alej#andr&amp;'ía</td>
      <td>05021</td>
      <td>128.932153</td>
      <td>4669.0</td>
      <td>48.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Am#a?&amp;'*gá</td>
      <td>05030</td>
      <td>84.132477</td>
      <td>30777.0</td>
      <td>28.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>5</th>
      <td>AntioqUia</td>
      <td>05</td>
      <td>Am?al#'*fi</td>
      <td>05031</td>
      <td>1209.126871</td>
      <td>26552.0</td>
      <td>54.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>6</th>
      <td>AntioqUia</td>
      <td>05</td>
      <td>Andes*!</td>
      <td>05034</td>
      <td>402.502562</td>
      <td>43713.0</td>
      <td>38.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Ant%ioquia</td>
      <td>05</td>
      <td>&amp;# Angelópoli?s</td>
      <td>05036</td>
      <td>81.876302</td>
      <td>5790.0</td>
      <td>37.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Antioq&gt;Uia</td>
      <td>05</td>
      <td>Ang#'ostura</td>
      <td>05038</td>
      <td>338.666482</td>
      <td>11462.0</td>
      <td>47.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Ant%ioquia</td>
      <td>05</td>
      <td>An*'#?orí</td>
      <td>05040</td>
      <td>1413.773904</td>
      <td>18737.0</td>
      <td>58.0</td>
      <td>Región Eje Cafetero</td>
    </tr>
  </tbody>
</table>
</div>




```python
def missings(x):
            a = sum(x.isna())
            b = 100*np.mean(x.isna())
            c = pd.Series({"Missings": a,"%Missings": b})
            return(c)
```


```python
Municipios.apply(missings, axis=0)
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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Missings</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.000000</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>%Missings</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.089445</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
</div>



help(pd.Series)


```python
Municipios.apply(missings, axis=1).query("Missings > 0")
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
      <th>Missings</th>
      <th>%Missings</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1097</th>
      <td>1.0</td>
      <td>12.5</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1118 entries, 0 to 1117
    Data columns (total 8 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  1118 non-null   object 
     1   Dep           1118 non-null   object 
     2   Municipio     1118 non-null   object 
     3   Depmun        1118 non-null   object 
     4   Superficie    1117 non-null   float64
     5   Poblacion     1118 non-null   float64
     6   Irural        1118 non-null   float64
     7   Region        1118 non-null   object 
    dtypes: float64(3), object(5)
    memory usage: 70.0+ KB
    


```python
Municipios["Municipio2"] = (Municipios["Municipio"]
                            .str.lower()
                            .str.replace("[^a-záéíóúüñ ]","", regex=True)
                            .str.replace(" +"," ", regex=True)
                            .str.strip()
                            .str.title()
                           ) 
```


```python
Municipios.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1118 entries, 0 to 1117
    Data columns (total 9 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  1118 non-null   object 
     1   Dep           1118 non-null   object 
     2   Municipio     1118 non-null   object 
     3   Depmun        1118 non-null   object 
     4   Superficie    1117 non-null   float64
     5   Poblacion     1118 non-null   float64
     6   Irural        1118 non-null   float64
     7   Region        1118 non-null   object 
     8   Municipio2    1118 non-null   object 
    dtypes: float64(3), object(6)
    memory usage: 78.7+ KB
    


```python
Municipios[["Municipio","Municipio2"]]
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
      <th>Municipio</th>
      <th>Municipio2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Mede&amp;l'lín</td>
      <td>Medellín</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Abej!&amp;orr*al</td>
      <td>Abejorral</td>
    </tr>
    <tr>
      <th>2</th>
      <td>A?br'&amp;iaquí</td>
      <td>Abriaquí</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Alej#andr&amp;'ía</td>
      <td>Alejandría</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Am#a?&amp;'*gá</td>
      <td>Amagá</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1113</th>
      <td>Y#*ava'ra?t!é</td>
      <td>Yavaraté</td>
    </tr>
    <tr>
      <th>1114</th>
      <td>Puerto   Carr#eño'</td>
      <td>Puerto Carreño</td>
    </tr>
    <tr>
      <th>1115</th>
      <td>La Prima&amp;*'!ve#ra</td>
      <td>La Primavera</td>
    </tr>
    <tr>
      <th>1116</th>
      <td>Santa   ?Rosalía</td>
      <td>Santa Rosalía</td>
    </tr>
    <tr>
      <th>1117</th>
      <td>C#u'?mar!ibo</td>
      <td>Cumaribo</td>
    </tr>
  </tbody>
</table>
<p>1118 rows × 2 columns</p>
</div>




```python
Municipios["Municipio"] = Municipios["Municipio2"]
Municipios = Municipios.drop(columns="Municipio2")
Municipios.tail(10)
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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1108</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Mitú</td>
      <td>97001</td>
      <td>16215.737264</td>
      <td>31302.0</td>
      <td>77.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1109</th>
      <td>Va%Up&gt;és</td>
      <td>97</td>
      <td>Caruru</td>
      <td>97161</td>
      <td>6368.486418</td>
      <td>3056.0</td>
      <td>85.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1110</th>
      <td>Vaup&gt;és</td>
      <td>97</td>
      <td>Pacoa</td>
      <td>97511</td>
      <td>13993.250574</td>
      <td>4229.0</td>
      <td>91.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1111</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Taraira</td>
      <td>97666</td>
      <td>6510.246561</td>
      <td>2318.0</td>
      <td>97.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1112</th>
      <td>Va%Upés</td>
      <td>97</td>
      <td>Papunaua</td>
      <td>97777</td>
      <td>5551.153548</td>
      <td>749.0</td>
      <td>95.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1113</th>
      <td>Vaup&gt;és</td>
      <td>97</td>
      <td>Yavaraté</td>
      <td>97889</td>
      <td>4660.405650</td>
      <td>1067.0</td>
      <td>92.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1114</th>
      <td>Vi%ch&gt;ada</td>
      <td>99</td>
      <td>Puerto Carreño</td>
      <td>99001</td>
      <td>12204.951401</td>
      <td>20474.0</td>
      <td>81.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1115</th>
      <td>Vichada</td>
      <td>99</td>
      <td>La Primavera</td>
      <td>99524</td>
      <td>18569.337656</td>
      <td>9799.0</td>
      <td>85.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1116</th>
      <td>Vi%ch&gt;ada</td>
      <td>99</td>
      <td>Santa Rosalía</td>
      <td>99624</td>
      <td>3691.869191</td>
      <td>4130.0</td>
      <td>81.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1117</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Cumaribo</td>
      <td>99773</td>
      <td>65597.212354</td>
      <td>76196.0</td>
      <td>87.0</td>
      <td>Región Llano</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios["Departamento2"] = (Municipios["Departamento"]
                            .str.lower()
                            .str.replace("[^a-záéíóúüñ ]","", regex=True)
                            .str.replace(" +"," ", regex=True)
                            .str.strip()
                            .str.title()
                           ) 

```


```python
Municipios["Departamento"] = Municipios["Departamento2"]
Municipios = Municipios.drop(columns="Departamento2")

```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    C:\Anaconda\lib\site-packages\pandas\core\indexes\base.py in get_loc(self, key, method, tolerance)
       3079             try:
    -> 3080                 return self._engine.get_loc(casted_key)
       3081             except KeyError as err:
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.PyObjectHashTable.get_item()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.PyObjectHashTable.get_item()
    

    KeyError: 'Departamento2'

    
    The above exception was the direct cause of the following exception:
    

    KeyError                                  Traceback (most recent call last)

    <ipython-input-73-684491d09298> in <module>
    ----> 1 Municipios["Departamento"] = Municipios["Departamento2"]
          2 Municipios = Municipios.drop(columns="Departamento2")
          3 Municipios.tail(100)
    

    C:\Anaconda\lib\site-packages\pandas\core\frame.py in __getitem__(self, key)
       3022             if self.columns.nlevels > 1:
       3023                 return self._getitem_multilevel(key)
    -> 3024             indexer = self.columns.get_loc(key)
       3025             if is_integer(indexer):
       3026                 indexer = [indexer]
    

    C:\Anaconda\lib\site-packages\pandas\core\indexes\base.py in get_loc(self, key, method, tolerance)
       3080                 return self._engine.get_loc(casted_key)
       3081             except KeyError as err:
    -> 3082                 raise KeyError(key) from err
       3083 
       3084         if tolerance is not None:
    

    KeyError: 'Departamento2'



```python
Municipios.tail(100)
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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1018</th>
      <td>Valle Del Cauca</td>
      <td>76</td>
      <td>El Dovio</td>
      <td>76250</td>
      <td>235.410117</td>
      <td>8711.0</td>
      <td>44.0</td>
      <td>Región Pacífico</td>
    </tr>
    <tr>
      <th>1019</th>
      <td>Valle Del Cauca</td>
      <td>76</td>
      <td>Florida</td>
      <td>76275</td>
      <td>401.550211</td>
      <td>57696.0</td>
      <td>36.0</td>
      <td>Región Pacífico</td>
    </tr>
    <tr>
      <th>1020</th>
      <td>Valle Del Cauca</td>
      <td>76</td>
      <td>Ginebra</td>
      <td>76306</td>
      <td>268.732723</td>
      <td>22908.0</td>
      <td>40.0</td>
      <td>Región Pacífico</td>
    </tr>
    <tr>
      <th>1021</th>
      <td>Valle Del Cauca</td>
      <td>76</td>
      <td>Guacarí</td>
      <td>76318</td>
      <td>162.499075</td>
      <td>33405.0</td>
      <td>32.0</td>
      <td>Región Pacífico</td>
    </tr>
    <tr>
      <th>1022</th>
      <td>Valle Del Cauca</td>
      <td>76</td>
      <td>Jamundí</td>
      <td>76364</td>
      <td>628.964341</td>
      <td>164159.0</td>
      <td>36.0</td>
      <td>Región Pacífico</td>
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
    </tr>
    <tr>
      <th>1113</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Yavaraté</td>
      <td>97889</td>
      <td>4660.405650</td>
      <td>1067.0</td>
      <td>92.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1114</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Puerto Carreño</td>
      <td>99001</td>
      <td>12204.951401</td>
      <td>20474.0</td>
      <td>81.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1115</th>
      <td>Vichada</td>
      <td>99</td>
      <td>La Primavera</td>
      <td>99524</td>
      <td>18569.337656</td>
      <td>9799.0</td>
      <td>85.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1116</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Santa Rosalía</td>
      <td>99624</td>
      <td>3691.869191</td>
      <td>4130.0</td>
      <td>81.0</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1117</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Cumaribo</td>
      <td>99773</td>
      <td>65597.212354</td>
      <td>76196.0</td>
      <td>87.0</td>
      <td>Región Llano</td>
    </tr>
  </tbody>
</table>
<p>100 rows × 8 columns</p>
</div>




```python
Municipios["Region"] = (Municipios["Region"]
                               .str.lower()
                               .str.replace("[^a-záéíóúüñ ]","", regex=True)
                               .str.replace(" +"," ", regex=True)
                               .str.strip()
                               .str.title()
                              ) 
Municipios["Region"]= (Municipios["Region"].str.replace("Región ","", regex=True))

```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-79-690a58d17c52> in <module>
          7                               ) 
          8 Municipios["Region"]= (Municipios["Region"].str.replace("Región ","", regex=True))
    ----> 9 Municipios(10)
    

    TypeError: 'DataFrame' object is not callable



```python
Municipios.head(10)
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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Medellín</td>
      <td>05001</td>
      <td>374.830625</td>
      <td>2483545.0</td>
      <td>5.0</td>
      <td>Eje Cafetero</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Abejorral</td>
      <td>05002</td>
      <td>507.134114</td>
      <td>20258.0</td>
      <td>45.0</td>
      <td>Eje Cafetero</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Abriaquí</td>
      <td>05004</td>
      <td>296.955980</td>
      <td>2710.0</td>
      <td>58.0</td>
      <td>Eje Cafetero</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Alejandría</td>
      <td>05021</td>
      <td>128.932153</td>
      <td>4669.0</td>
      <td>48.0</td>
      <td>Eje Cafetero</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Amagá</td>
      <td>05030</td>
      <td>84.132477</td>
      <td>30777.0</td>
      <td>28.0</td>
      <td>Eje Cafetero</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Amalfi</td>
      <td>05031</td>
      <td>1209.126871</td>
      <td>26552.0</td>
      <td>54.0</td>
      <td>Eje Cafetero</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Andes</td>
      <td>05034</td>
      <td>402.502562</td>
      <td>43713.0</td>
      <td>38.0</td>
      <td>Eje Cafetero</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Angelópolis</td>
      <td>05036</td>
      <td>81.876302</td>
      <td>5790.0</td>
      <td>37.0</td>
      <td>Eje Cafetero</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Angostura</td>
      <td>05038</td>
      <td>338.666482</td>
      <td>11462.0</td>
      <td>47.0</td>
      <td>Eje Cafetero</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Anorí</td>
      <td>05040</td>
      <td>1413.773904</td>
      <td>18737.0</td>
      <td>58.0</td>
      <td>Eje Cafetero</td>
    </tr>
  </tbody>
</table>
</div>




```python
def tipo(x): 
    if x[2:5]=="001" and x!="25001": return("Capital")
    else: return("Otros")
Municipios["Tipo"] = Municipios["Depmun"].apply(tipo)
```


```python
Municipios.tail(10)
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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
      <th>Tipo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1108</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Mitú</td>
      <td>97001</td>
      <td>16215.737264</td>
      <td>31302.0</td>
      <td>77.0</td>
      <td>Llano</td>
      <td>Capital</td>
    </tr>
    <tr>
      <th>1109</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Caruru</td>
      <td>97161</td>
      <td>6368.486418</td>
      <td>3056.0</td>
      <td>85.0</td>
      <td>Llano</td>
      <td>Otros</td>
    </tr>
    <tr>
      <th>1110</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Pacoa</td>
      <td>97511</td>
      <td>13993.250574</td>
      <td>4229.0</td>
      <td>91.0</td>
      <td>Llano</td>
      <td>Otros</td>
    </tr>
    <tr>
      <th>1111</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Taraira</td>
      <td>97666</td>
      <td>6510.246561</td>
      <td>2318.0</td>
      <td>97.0</td>
      <td>Llano</td>
      <td>Otros</td>
    </tr>
    <tr>
      <th>1112</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Papunaua</td>
      <td>97777</td>
      <td>5551.153548</td>
      <td>749.0</td>
      <td>95.0</td>
      <td>Llano</td>
      <td>Otros</td>
    </tr>
    <tr>
      <th>1113</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Yavaraté</td>
      <td>97889</td>
      <td>4660.405650</td>
      <td>1067.0</td>
      <td>92.0</td>
      <td>Llano</td>
      <td>Otros</td>
    </tr>
    <tr>
      <th>1114</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Puerto Carreño</td>
      <td>99001</td>
      <td>12204.951401</td>
      <td>20474.0</td>
      <td>81.0</td>
      <td>Llano</td>
      <td>Capital</td>
    </tr>
    <tr>
      <th>1115</th>
      <td>Vichada</td>
      <td>99</td>
      <td>La Primavera</td>
      <td>99524</td>
      <td>18569.337656</td>
      <td>9799.0</td>
      <td>85.0</td>
      <td>Llano</td>
      <td>Otros</td>
    </tr>
    <tr>
      <th>1116</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Santa Rosalía</td>
      <td>99624</td>
      <td>3691.869191</td>
      <td>4130.0</td>
      <td>81.0</td>
      <td>Llano</td>
      <td>Otros</td>
    </tr>
    <tr>
      <th>1117</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Cumaribo</td>
      <td>99773</td>
      <td>65597.212354</td>
      <td>76196.0</td>
      <td>87.0</td>
      <td>Llano</td>
      <td>Otros</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios["denspobl"] = Municipios["Poblacion"]/Municipios["Superficie"]
```


```python
Municipios.tail(10)
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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
      <th>Tipo</th>
      <th>denspobl</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1108</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Mitú</td>
      <td>97001</td>
      <td>16215.737264</td>
      <td>31302.0</td>
      <td>77.0</td>
      <td>Llano</td>
      <td>Capital</td>
      <td>1.930347</td>
    </tr>
    <tr>
      <th>1109</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Caruru</td>
      <td>97161</td>
      <td>6368.486418</td>
      <td>3056.0</td>
      <td>85.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.479863</td>
    </tr>
    <tr>
      <th>1110</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Pacoa</td>
      <td>97511</td>
      <td>13993.250574</td>
      <td>4229.0</td>
      <td>91.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.302217</td>
    </tr>
    <tr>
      <th>1111</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Taraira</td>
      <td>97666</td>
      <td>6510.246561</td>
      <td>2318.0</td>
      <td>97.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.356054</td>
    </tr>
    <tr>
      <th>1112</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Papunaua</td>
      <td>97777</td>
      <td>5551.153548</td>
      <td>749.0</td>
      <td>95.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.134927</td>
    </tr>
    <tr>
      <th>1113</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Yavaraté</td>
      <td>97889</td>
      <td>4660.405650</td>
      <td>1067.0</td>
      <td>92.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.228950</td>
    </tr>
    <tr>
      <th>1114</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Puerto Carreño</td>
      <td>99001</td>
      <td>12204.951401</td>
      <td>20474.0</td>
      <td>81.0</td>
      <td>Llano</td>
      <td>Capital</td>
      <td>1.677516</td>
    </tr>
    <tr>
      <th>1115</th>
      <td>Vichada</td>
      <td>99</td>
      <td>La Primavera</td>
      <td>99524</td>
      <td>18569.337656</td>
      <td>9799.0</td>
      <td>85.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.527698</td>
    </tr>
    <tr>
      <th>1116</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Santa Rosalía</td>
      <td>99624</td>
      <td>3691.869191</td>
      <td>4130.0</td>
      <td>81.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>1.118675</td>
    </tr>
    <tr>
      <th>1117</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Cumaribo</td>
      <td>99773</td>
      <td>65597.212354</td>
      <td>76196.0</td>
      <td>87.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>1.161574</td>
    </tr>
  </tbody>
</table>
</div>




```python
import warnings
warnings.filterwarnings("ignore", 'This pattern has match groups')
```


```python
def zona(x): 
    if x  > 40: return("Rural")
    if x <= 40: return("Urbano")
    
Municipios["Zona"] = Municipios["Irural"].apply(zona)
```


```python
Municipios.loc[Municipios["Irural"] >  40,"Zona2"] = "Rural" 
Municipios.loc[Municipios["Irural"] <= 40,"Zona2"] = "Urbano"
```


```python
Municipios["Zona"].equals(Municipios["Zona2"])
```




    True




```python
Municipios = Municipios.drop(columns="Zona2")
```


```python
Municipios.tail(10)
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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
      <th>Tipo</th>
      <th>denspobl</th>
      <th>Zona</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1108</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Mitú</td>
      <td>97001</td>
      <td>16215.737264</td>
      <td>31302.0</td>
      <td>77.0</td>
      <td>Llano</td>
      <td>Capital</td>
      <td>1.930347</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1109</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Caruru</td>
      <td>97161</td>
      <td>6368.486418</td>
      <td>3056.0</td>
      <td>85.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.479863</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1110</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Pacoa</td>
      <td>97511</td>
      <td>13993.250574</td>
      <td>4229.0</td>
      <td>91.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.302217</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1111</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Taraira</td>
      <td>97666</td>
      <td>6510.246561</td>
      <td>2318.0</td>
      <td>97.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.356054</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1112</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Papunaua</td>
      <td>97777</td>
      <td>5551.153548</td>
      <td>749.0</td>
      <td>95.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.134927</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1113</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Yavaraté</td>
      <td>97889</td>
      <td>4660.405650</td>
      <td>1067.0</td>
      <td>92.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.228950</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1114</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Puerto Carreño</td>
      <td>99001</td>
      <td>12204.951401</td>
      <td>20474.0</td>
      <td>81.0</td>
      <td>Llano</td>
      <td>Capital</td>
      <td>1.677516</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1115</th>
      <td>Vichada</td>
      <td>99</td>
      <td>La Primavera</td>
      <td>99524</td>
      <td>18569.337656</td>
      <td>9799.0</td>
      <td>85.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.527698</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1116</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Santa Rosalía</td>
      <td>99624</td>
      <td>3691.869191</td>
      <td>4130.0</td>
      <td>81.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>1.118675</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1117</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Cumaribo</td>
      <td>99773</td>
      <td>65597.212354</td>
      <td>76196.0</td>
      <td>87.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>1.161574</td>
      <td>Rural</td>
    </tr>
  </tbody>
</table>
</div>




```python
santos = (Municipios
          .query("Municipio.str.contains('(^| )San( |ta |to )').values")
          .loc[:,["Departamento","Depmun","Municipio"]]
         .reset_index(drop = True)
         )
santos.info()
santos.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 111 entries, 0 to 110
    Data columns (total 3 columns):
     #   Column        Non-Null Count  Dtype 
    ---  ------        --------------  ----- 
     0   Departamento  111 non-null    object
     1   Depmun        111 non-null    object
     2   Municipio     111 non-null    object
    dtypes: object(3)
    memory usage: 2.7+ KB
    




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
      <th>Departamento</th>
      <th>Depmun</th>
      <th>Municipio</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Antioquia</td>
      <td>05647</td>
      <td>San Andrés De Cuerquía</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Antioquia</td>
      <td>05649</td>
      <td>San Carlos</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Antioquia</td>
      <td>05652</td>
      <td>San Francisco</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Antioquia</td>
      <td>05656</td>
      <td>San Jerónimo</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Antioquia</td>
      <td>05658</td>
      <td>San José De La Montaña</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Antioquia</td>
      <td>05659</td>
      <td>San Juan De Urabá</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Antioquia</td>
      <td>05660</td>
      <td>San Luis</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Antioquia</td>
      <td>05664</td>
      <td>San Pedro</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Antioquia</td>
      <td>05665</td>
      <td>San Pedro De Uraba</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Antioquia</td>
      <td>05667</td>
      <td>San Rafael</td>
    </tr>
  </tbody>
</table>
</div>




```python
vocales = (Municipios
           .query("Municipio.str.contains('(^(A|Á).*(a|á)$)|(^(E|É).*(e|é)$)|(^(I|Í).*(i|í)$)|(^(O|Ó).*(o|ó)$)|(^(U|Ú).*(u|ú)$)').values")
           .loc[:,["Dep","Departamento","Depmun","Municipio"]]
           .reset_index(drop=True)
          )
vocales.info()
vocales.head()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 39 entries, 0 to 38
    Data columns (total 4 columns):
     #   Column        Non-Null Count  Dtype 
    ---  ------        --------------  ----- 
     0   Dep           39 non-null     object
     1   Departamento  39 non-null     object
     2   Depmun        39 non-null     object
     3   Municipio     39 non-null     object
    dtypes: object(4)
    memory usage: 1.3+ KB
    




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
      <th>Dep</th>
      <th>Departamento</th>
      <th>Depmun</th>
      <th>Municipio</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>05</td>
      <td>Antioquia</td>
      <td>05021</td>
      <td>Alejandría</td>
    </tr>
    <tr>
      <th>1</th>
      <td>05</td>
      <td>Antioquia</td>
      <td>05030</td>
      <td>Amagá</td>
    </tr>
    <tr>
      <th>2</th>
      <td>05</td>
      <td>Antioquia</td>
      <td>05038</td>
      <td>Angostura</td>
    </tr>
    <tr>
      <th>3</th>
      <td>05</td>
      <td>Antioquia</td>
      <td>05044</td>
      <td>Anza</td>
    </tr>
    <tr>
      <th>4</th>
      <td>05</td>
      <td>Antioquia</td>
      <td>05055</td>
      <td>Argelia</td>
    </tr>
  </tbody>
</table>
</div>




```python
iguales = Municipios["Municipio"].str.lower().str.get(0) == Municipios["Municipio"].str.get(-1)
consonantes = (Municipios
               .query("@iguales & Municipio.str.contains('^[^A|^E|^I|^O|^U]').values")
               .reset_index(drop=True)
              )
consonantes.info()
consonantes.head(15)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 17 entries, 0 to 16
    Data columns (total 11 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  17 non-null     object 
     1   Dep           17 non-null     object 
     2   Municipio     17 non-null     object 
     3   Depmun        17 non-null     object 
     4   Superficie    17 non-null     float64
     5   Poblacion     17 non-null     float64
     6   Irural        17 non-null     float64
     7   Region        17 non-null     object 
     8   Tipo          17 non-null     object 
     9   denspobl      17 non-null     float64
     10  Zona          17 non-null     object 
    dtypes: float64(4), object(7)
    memory usage: 1.6+ KB
    




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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
      <th>Tipo</th>
      <th>denspobl</th>
      <th>Zona</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>San Carlos</td>
      <td>05649</td>
      <td>717.814571</td>
      <td>15940.0</td>
      <td>51.0</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>22.206292</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>San Luis</td>
      <td>05660</td>
      <td>425.619074</td>
      <td>13035.0</td>
      <td>51.0</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>30.625977</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Santa Rosa De Osos</td>
      <td>05686</td>
      <td>864.778914</td>
      <td>37143.0</td>
      <td>47.0</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>42.950862</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Atlántico</td>
      <td>08</td>
      <td>Santo Tomás</td>
      <td>08685</td>
      <td>65.003006</td>
      <td>31027.0</td>
      <td>28.0</td>
      <td>Caribe</td>
      <td>Otros</td>
      <td>477.316388</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Bolívar</td>
      <td>13</td>
      <td>Regidor</td>
      <td>13580</td>
      <td>183.452689</td>
      <td>6983.0</td>
      <td>47.0</td>
      <td>Caribe</td>
      <td>Otros</td>
      <td>38.064310</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Boyacá</td>
      <td>15</td>
      <td>Nuevo Colón</td>
      <td>15494</td>
      <td>51.396797</td>
      <td>5172.0</td>
      <td>38.0</td>
      <td>Centro Oriente</td>
      <td>Otros</td>
      <td>100.628838</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Córdoba</td>
      <td>23</td>
      <td>San Carlos</td>
      <td>23678</td>
      <td>446.820634</td>
      <td>27174.0</td>
      <td>47.0</td>
      <td>Caribe</td>
      <td>Otros</td>
      <td>60.816350</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Cundinamarca</td>
      <td>25</td>
      <td>Nemocón</td>
      <td>25486</td>
      <td>98.365040</td>
      <td>13868.0</td>
      <td>38.0</td>
      <td>Centro Oriente</td>
      <td>Otros</td>
      <td>140.985049</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Nariño</td>
      <td>52</td>
      <td>Sapuyes</td>
      <td>52720</td>
      <td>115.548511</td>
      <td>7277.0</td>
      <td>46.0</td>
      <td>Pacífico</td>
      <td>Otros</td>
      <td>62.977878</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Norte De Santander</td>
      <td>54</td>
      <td>Silos</td>
      <td>54743</td>
      <td>316.855408</td>
      <td>6380.0</td>
      <td>54.0</td>
      <td>Centro Oriente</td>
      <td>Otros</td>
      <td>20.135367</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Santander</td>
      <td>68</td>
      <td>Sabana De Torres</td>
      <td>68655</td>
      <td>1402.870009</td>
      <td>33887.0</td>
      <td>55.0</td>
      <td>Centro Oriente</td>
      <td>Otros</td>
      <td>24.155481</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Santander</td>
      <td>68</td>
      <td>San Andrés</td>
      <td>68669</td>
      <td>281.558855</td>
      <td>8613.0</td>
      <td>48.0</td>
      <td>Centro Oriente</td>
      <td>Otros</td>
      <td>30.590407</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Sucre</td>
      <td>70</td>
      <td>Sampués</td>
      <td>70670</td>
      <td>213.937701</td>
      <td>47746.0</td>
      <td>35.0</td>
      <td>Caribe</td>
      <td>Otros</td>
      <td>223.177120</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Sucre</td>
      <td>70</td>
      <td>San Marcos</td>
      <td>70708</td>
      <td>970.354812</td>
      <td>59254.0</td>
      <td>46.0</td>
      <td>Caribe</td>
      <td>Otros</td>
      <td>61.064262</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Tolima</td>
      <td>73</td>
      <td>San Luis</td>
      <td>73678</td>
      <td>412.226227</td>
      <td>13481.0</td>
      <td>44.0</td>
      <td>Centro Sur</td>
      <td>Otros</td>
      <td>32.702917</td>
      <td>Rural</td>
    </tr>
  </tbody>
</table>
</div>




```python
Aes = (Municipios
       .query("Municipio.str.contains('^A.{2}e').values")
       .drop(columns=["Poblacion","Superficie","Irural"])
       .reset_index(drop=True)
      )
Aes.info()
Aes.head(15) 
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 15 entries, 0 to 14
    Data columns (total 8 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  15 non-null     object 
     1   Dep           15 non-null     object 
     2   Municipio     15 non-null     object 
     3   Depmun        15 non-null     object 
     4   Region        15 non-null     object 
     5   Tipo          15 non-null     object 
     6   denspobl      15 non-null     float64
     7   Zona          15 non-null     object 
    dtypes: float64(1), object(7)
    memory usage: 1.1+ KB
    




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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Region</th>
      <th>Tipo</th>
      <th>denspobl</th>
      <th>Zona</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Andes</td>
      <td>05034</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>108.603035</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Angelópolis</td>
      <td>05036</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>70.716433</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Argelia</td>
      <td>05055</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>30.883447</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Armenia</td>
      <td>05059</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>46.045195</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Boyacá</td>
      <td>15</td>
      <td>Almeida</td>
      <td>15022</td>
      <td>Centro Oriente</td>
      <td>Otros</td>
      <td>31.991195</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Caldas</td>
      <td>17</td>
      <td>Anserma</td>
      <td>17042</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>174.067773</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Cauca</td>
      <td>19</td>
      <td>Argelia</td>
      <td>19050</td>
      <td>Pacífico</td>
      <td>Otros</td>
      <td>33.998987</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Cundinamarca</td>
      <td>25</td>
      <td>Arbeláez</td>
      <td>25053</td>
      <td>Centro Oriente</td>
      <td>Otros</td>
      <td>75.986259</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Huila</td>
      <td>41</td>
      <td>Aipe</td>
      <td>41016</td>
      <td>Centro Sur</td>
      <td>Otros</td>
      <td>20.563562</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Huila</td>
      <td>41</td>
      <td>Algeciras</td>
      <td>41020</td>
      <td>Centro Sur</td>
      <td>Otros</td>
      <td>38.152315</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Norte De Santander</td>
      <td>54</td>
      <td>Abrego</td>
      <td>54003</td>
      <td>Centro Oriente</td>
      <td>Otros</td>
      <td>23.872839</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Quindío</td>
      <td>63</td>
      <td>Armenia</td>
      <td>63001</td>
      <td>Eje Cafetero</td>
      <td>Capital</td>
      <td>2468.347129</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Tolima</td>
      <td>73</td>
      <td>Armero</td>
      <td>73055</td>
      <td>Centro Sur</td>
      <td>Otros</td>
      <td>27.993955</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Valle Del Cauca</td>
      <td>76</td>
      <td>Ansermanuevo</td>
      <td>76041</td>
      <td>Pacífico</td>
      <td>Otros</td>
      <td>56.794681</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Valle Del Cauca</td>
      <td>76</td>
      <td>Argelia</td>
      <td>76054</td>
      <td>Pacífico</td>
      <td>Otros</td>
      <td>57.910012</td>
      <td>Rural</td>
    </tr>
  </tbody>
</table>
</div>




```python
Mas4 = (Municipios
        .query("Municipio.str.count(' ').values == 1")
        .reset_index(drop=True)
       )
Mas4.info()
Mas4
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 220 entries, 0 to 219
    Data columns (total 11 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  220 non-null    object 
     1   Dep           220 non-null    object 
     2   Municipio     220 non-null    object 
     3   Depmun        220 non-null    object 
     4   Superficie    220 non-null    float64
     5   Poblacion     220 non-null    float64
     6   Irural        220 non-null    float64
     7   Region        220 non-null    object 
     8   Tipo          220 non-null    object 
     9   denspobl      220 non-null    float64
     10  Zona          220 non-null    object 
    dtypes: float64(4), object(7)
    memory usage: 19.0+ KB
    




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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Municipio</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
      <th>Region</th>
      <th>Tipo</th>
      <th>denspobl</th>
      <th>Zona</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Ciudad Bolívar</td>
      <td>05101</td>
      <td>260.446108</td>
      <td>26160.0</td>
      <td>38.0</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>100.443044</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Don Matías</td>
      <td>05237</td>
      <td>203.332311</td>
      <td>19332.0</td>
      <td>39.0</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>95.075888</td>
      <td>Urbano</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>El Bagre</td>
      <td>05250</td>
      <td>1560.248872</td>
      <td>52925.0</td>
      <td>51.0</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>33.920871</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>Gómez Plata</td>
      <td>05310</td>
      <td>332.204629</td>
      <td>9828.0</td>
      <td>48.0</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>29.584175</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Antioquia</td>
      <td>05</td>
      <td>La Ceja</td>
      <td>05376</td>
      <td>132.714953</td>
      <td>66746.0</td>
      <td>28.0</td>
      <td>Eje Cafetero</td>
      <td>Otros</td>
      <td>502.927505</td>
      <td>Urbano</td>
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
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>215</th>
      <td>Guainía</td>
      <td>94</td>
      <td>Pana Pana</td>
      <td>94887</td>
      <td>10227.146784</td>
      <td>1959.0</td>
      <td>93.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.191549</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>216</th>
      <td>Guaviare</td>
      <td>95</td>
      <td>El Retorno</td>
      <td>95025</td>
      <td>12442.225771</td>
      <td>13684.0</td>
      <td>77.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>1.099803</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>217</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Puerto Carreño</td>
      <td>99001</td>
      <td>12204.951401</td>
      <td>20474.0</td>
      <td>81.0</td>
      <td>Llano</td>
      <td>Capital</td>
      <td>1.677516</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>218</th>
      <td>Vichada</td>
      <td>99</td>
      <td>La Primavera</td>
      <td>99524</td>
      <td>18569.337656</td>
      <td>9799.0</td>
      <td>85.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>0.527698</td>
      <td>Rural</td>
    </tr>
    <tr>
      <th>219</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Santa Rosalía</td>
      <td>99624</td>
      <td>3691.869191</td>
      <td>4130.0</td>
      <td>81.0</td>
      <td>Llano</td>
      <td>Otros</td>
      <td>1.118675</td>
      <td>Rural</td>
    </tr>
  </tbody>
</table>
<p>220 rows × 11 columns</p>
</div>




```python

```
