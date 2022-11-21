```python
import os
os.chdir("C:\\Users\\Estudiante\\Desktop\\nicolas")
```


```python
import pandas as pd
```


```python
Municipios=pd.read_excel("Municipios.xlsx")

```


```python
Municipios["Municipio2"] = (Municipios["Municipio"]
                            .str.lower()
                            .str.replace("[^a-záéíóúüñ ]","", regex=True)
                            .str.replace(" +"," ", regex=True)
                            .str.strip()
                            .str.title()
                           ) 
Municipios[["Municipio","Municipio2"]].tail(10)
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
      <th>1108</th>
      <td>M*it!ú</td>
      <td>Mitú</td>
    </tr>
    <tr>
      <th>1109</th>
      <td>C!a*#ruru</td>
      <td>Caruru</td>
    </tr>
    <tr>
      <th>1110</th>
      <td>P*a!coa</td>
      <td>Pacoa</td>
    </tr>
    <tr>
      <th>1111</th>
      <td>Tara#?ir&amp;*a'</td>
      <td>Taraira</td>
    </tr>
    <tr>
      <th>1112</th>
      <td>Papuna!ua</td>
      <td>Papunaua</td>
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
</div>




```python
Municipios["Departamento2"] = (Municipios["Departamento"]
                               .str.lower()
                               .str.replace("[^a-záéíóúüñ ]","", regex=True)
                               .str.replace(" +"," ", regex=True)
                               .str.strip()
                               .str.title()
                              ) 
Municipios[["Departamento","Departamento2"]].head(10)
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
      <th>Departamento2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ant%ioqUia</td>
      <td>Antioquia</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ant%ioquia</td>
      <td>Antioquia</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Ant%ioquia</td>
      <td>Antioquia</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ant%io&gt;qUia</td>
      <td>Antioquia</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Antioquia</td>
      <td>Antioquia</td>
    </tr>
    <tr>
      <th>5</th>
      <td>AntioqUia</td>
      <td>Antioquia</td>
    </tr>
    <tr>
      <th>6</th>
      <td>AntioqUia</td>
      <td>Antioquia</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Ant%ioquia</td>
      <td>Antioquia</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Antioq&gt;Uia</td>
      <td>Antioquia</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Ant%ioquia</td>
      <td>Antioquia</td>
    </tr>
  </tbody>
</table>
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
      <td>31302</td>
      <td>77</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1109</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Caruru</td>
      <td>97161</td>
      <td>6368.486418</td>
      <td>3056</td>
      <td>85</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1110</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Pacoa</td>
      <td>97511</td>
      <td>13993.250574</td>
      <td>4229</td>
      <td>91</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1111</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Taraira</td>
      <td>97666</td>
      <td>6510.246561</td>
      <td>2318</td>
      <td>97</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1112</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Papunaua</td>
      <td>97777</td>
      <td>5551.153548</td>
      <td>749</td>
      <td>95</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1113</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Yavaraté</td>
      <td>97889</td>
      <td>4660.405650</td>
      <td>1067</td>
      <td>92</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1114</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Puerto Carreño</td>
      <td>99001</td>
      <td>12204.951401</td>
      <td>20474</td>
      <td>81</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1115</th>
      <td>Vichada</td>
      <td>99</td>
      <td>La Primavera</td>
      <td>99524</td>
      <td>18569.337656</td>
      <td>9799</td>
      <td>85</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1116</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Santa Rosalía</td>
      <td>99624</td>
      <td>3691.869191</td>
      <td>4130</td>
      <td>81</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1117</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Cumaribo</td>
      <td>99773</td>
      <td>65597.212354</td>
      <td>76196</td>
      <td>87</td>
      <td>Región Llano</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios["Departamento"] = Municipios["Departamento2"]
Municipios = Municipios.drop(columns="Departamento2")
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
      <th>Municipio2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Mede&amp;l'lín</td>
      <td>5001</td>
      <td>374.830625</td>
      <td>2483545</td>
      <td>5</td>
      <td>Región Eje Cafetero</td>
      <td>Medellín</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Abej!&amp;orr*al</td>
      <td>5002</td>
      <td>507.134114</td>
      <td>20258</td>
      <td>45</td>
      <td>Región Eje Cafetero</td>
      <td>Abejorral</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>A?br'&amp;iaquí</td>
      <td>5004</td>
      <td>296.955980</td>
      <td>2710</td>
      <td>58</td>
      <td>Región Eje Cafetero</td>
      <td>Abriaquí</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Alej#andr&amp;'ía</td>
      <td>5021</td>
      <td>128.932153</td>
      <td>4669</td>
      <td>48</td>
      <td>Región Eje Cafetero</td>
      <td>Alejandría</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Am#a?&amp;'*gá</td>
      <td>5030</td>
      <td>84.132477</td>
      <td>30777</td>
      <td>28</td>
      <td>Región Eje Cafetero</td>
      <td>Amagá</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Am?al#'*fi</td>
      <td>5031</td>
      <td>1209.126871</td>
      <td>26552</td>
      <td>54</td>
      <td>Región Eje Cafetero</td>
      <td>Amalfi</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Andes*!</td>
      <td>5034</td>
      <td>402.502562</td>
      <td>43713</td>
      <td>38</td>
      <td>Región Eje Cafetero</td>
      <td>Andes</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>&amp;# Angelópoli?s</td>
      <td>5036</td>
      <td>81.876302</td>
      <td>5790</td>
      <td>37</td>
      <td>Región Eje Cafetero</td>
      <td>Angelópolis</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Ang#'ostura</td>
      <td>5038</td>
      <td>338.666482</td>
      <td>11462</td>
      <td>47</td>
      <td>Región Eje Cafetero</td>
      <td>Angostura</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>An*'#?orí</td>
      <td>5040</td>
      <td>1413.773904</td>
      <td>18737</td>
      <td>58</td>
      <td>Región Eje Cafetero</td>
      <td>Anorí</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios["Region2"] = (Municipios["Region"]
                               .str.lower()
                               .str.replace("[^a-záéíóúüñ ]","", regex=True)
                               .str.replace(" +"," ", regex=True)
                               .str.strip()
                               .str.title()
                              ) 
Municipios[["Region","Region2"]].tail(10)
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
      <th>Region</th>
      <th>Region2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1108</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1109</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1110</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1111</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1112</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1113</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1114</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1115</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1116</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
    <tr>
      <th>1117</th>
      <td>Región Llano</td>
      <td>Región Llano</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios["Region"] = Municipios["Region2"]
Municipios = Municipios.drop(columns="Region2")
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
      <th>Municipio2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1108</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>M*it!ú</td>
      <td>97001</td>
      <td>16215.737264</td>
      <td>31302</td>
      <td>77</td>
      <td>Región Llano</td>
      <td>Mitú</td>
    </tr>
    <tr>
      <th>1109</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>C!a*#ruru</td>
      <td>97161</td>
      <td>6368.486418</td>
      <td>3056</td>
      <td>85</td>
      <td>Región Llano</td>
      <td>Caruru</td>
    </tr>
    <tr>
      <th>1110</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>P*a!coa</td>
      <td>97511</td>
      <td>13993.250574</td>
      <td>4229</td>
      <td>91</td>
      <td>Región Llano</td>
      <td>Pacoa</td>
    </tr>
    <tr>
      <th>1111</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Tara#?ir&amp;*a'</td>
      <td>97666</td>
      <td>6510.246561</td>
      <td>2318</td>
      <td>97</td>
      <td>Región Llano</td>
      <td>Taraira</td>
    </tr>
    <tr>
      <th>1112</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Papuna!ua</td>
      <td>97777</td>
      <td>5551.153548</td>
      <td>749</td>
      <td>95</td>
      <td>Región Llano</td>
      <td>Papunaua</td>
    </tr>
    <tr>
      <th>1113</th>
      <td>Vaupés</td>
      <td>97</td>
      <td>Y#*ava'ra?t!é</td>
      <td>97889</td>
      <td>4660.405650</td>
      <td>1067</td>
      <td>92</td>
      <td>Región Llano</td>
      <td>Yavaraté</td>
    </tr>
    <tr>
      <th>1114</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Puerto   Carr#eño'</td>
      <td>99001</td>
      <td>12204.951401</td>
      <td>20474</td>
      <td>81</td>
      <td>Región Llano</td>
      <td>Puerto Carreño</td>
    </tr>
    <tr>
      <th>1115</th>
      <td>Vichada</td>
      <td>99</td>
      <td>La Prima&amp;*'!ve#ra</td>
      <td>99524</td>
      <td>18569.337656</td>
      <td>9799</td>
      <td>85</td>
      <td>Región Llano</td>
      <td>La Primavera</td>
    </tr>
    <tr>
      <th>1116</th>
      <td>Vichada</td>
      <td>99</td>
      <td>Santa   ?Rosalía</td>
      <td>99624</td>
      <td>3691.869191</td>
      <td>4130</td>
      <td>81</td>
      <td>Región Llano</td>
      <td>Santa Rosalía</td>
    </tr>
    <tr>
      <th>1117</th>
      <td>Vichada</td>
      <td>99</td>
      <td>C#u'?mar!ibo</td>
      <td>99773</td>
      <td>65597.212354</td>
      <td>76196</td>
      <td>87</td>
      <td>Región Llano</td>
      <td>Cumaribo</td>
    </tr>
  </tbody>
</table>
</div>




```python
def tipo(x): 
    if x[2:5]=="001" and x!="25001": return("Capital")
    else: return("Otros")

```


```python
Municipios["Tipo"] = Municipios["Depmun"].apply(tipo)

Municipios.info()
Municipios.head(10)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-23-234b5283a0da> in <module>
    ----> 1 Municipios["Tipo"] = Municipios["Depmun"].apply(tipo)
          2 
          3 Municipios.info()
          4 Municipios.head(10)
    

    C:\Anaconda\lib\site-packages\pandas\core\series.py in apply(self, func, convert_dtype, args, **kwds)
       4136             else:
       4137                 values = self.astype(object)._values
    -> 4138                 mapped = lib.map_infer(values, f, convert=convert_dtype)
       4139 
       4140         if len(mapped) and isinstance(mapped[0], Series):
    

    pandas\_libs\lib.pyx in pandas._libs.lib.map_infer()
    

    <ipython-input-22-1262a4bfbf43> in tipo(x)
          1 def tipo(x):
    ----> 2     if x[2:5]=="001" and x!="25001": return("Capital")
          3     else: return("Otros")
    

    TypeError: 'int' object is not subscriptable



```python
import numpy as np
```


```python

```


```python
print(Municipios)

```

         Departamento  Dep       Municipio  Depmun    Superficie  Poblacion  \
    0       Antioquia    5        Medellín    5001    374.830625    2483545   
    1       Antioquia    5       Abejorral    5002    507.134114      20258   
    2       Antioquia    5        Abriaquí    5004    296.955980       2710   
    3       Antioquia    5      Alejandría    5021    128.932153       4669   
    4       Antioquia    5           Amagá    5030     84.132477      30777   
    ...           ...  ...             ...     ...           ...        ...   
    1113       Vaupés   97        Yavaraté   97889   4660.405650       1067   
    1114      Vichada   99  Puerto Carreño   99001  12204.951401      20474   
    1115      Vichada   99    La Primavera   99524  18569.337656       9799   
    1116      Vichada   99   Santa Rosalía   99624   3691.869191       4130   
    1117      Vichada   99        Cumaribo   99773  65597.212354      76196   
    
          Irural               Region  
    0          5  Región Eje Cafetero  
    1         45  Región Eje Cafetero  
    2         58  Región Eje Cafetero  
    3         48  Región Eje Cafetero  
    4         28  Región Eje Cafetero  
    ...      ...                  ...  
    1113      92         Región Llano  
    1114      81         Región Llano  
    1115      85         Región Llano  
    1116      81         Región Llano  
    1117      87         Región Llano  
    
    [1118 rows x 8 columns]
    


```python
long = Municipios["Municipio"].str.len()
largos = (Municipios
          .query("@long > @long.quantile(0.99)")
          .loc[:,["Departamento","Depmun","Municipio"]]
          .reset_index(drop=True)
         )
largos
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
      <th>Depmun</th>
      <th>Municipio</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Córdoba</td>
      <td>23675</td>
      <td>San Bernardo Del Viento</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Cundinamarca</td>
      <td>25645</td>
      <td>San Antonio Del Tequendama</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Cundinamarca</td>
      <td>25843</td>
      <td>Villa De San Diego De Ubate</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Chocó</td>
      <td>27135</td>
      <td>El Cantón Del San Pablo</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Chocó</td>
      <td>27250</td>
      <td>El Litoral Del San Juan</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Magdalena</td>
      <td>47692</td>
      <td>San Sebastián De Buenavista</td>
    </tr>
  </tbody>
</table>
</div>




```python
cortos = (Municipios
          .query("@long <= @long.quantile(0.01)")
          .loc[:,["Departamento","Depmun","Municipio"]]
          .reset_index(drop=True)
         )
cortos
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
      <th>Depmun</th>
      <th>Municipio</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Antioquia</td>
      <td>5044</td>
      <td>Anza</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Antioquia</td>
      <td>5885</td>
      <td>Yalí</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Atlántico</td>
      <td>8770</td>
      <td>Suan</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Bolívar</td>
      <td>13006</td>
      <td>Achí</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Boyacá</td>
      <td>15362</td>
      <td>Iza</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Boyacá</td>
      <td>15480</td>
      <td>Muzo</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Boyacá</td>
      <td>15514</td>
      <td>Páez</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Boyacá</td>
      <td>15533</td>
      <td>Paya</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Boyacá</td>
      <td>15762</td>
      <td>Sora</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Boyacá</td>
      <td>15814</td>
      <td>Toca</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Boyacá</td>
      <td>15822</td>
      <td>Tota</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Boyacá</td>
      <td>15837</td>
      <td>Tuta</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Cauca</td>
      <td>19355</td>
      <td>Inzá</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Cauca</td>
      <td>19517</td>
      <td>Páez</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Cundinamarca</td>
      <td>25175</td>
      <td>Chía</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Cundinamarca</td>
      <td>25214</td>
      <td>Cota</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Cundinamarca</td>
      <td>25299</td>
      <td>Gama</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Cundinamarca</td>
      <td>25488</td>
      <td>Nilo</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Cundinamarca</td>
      <td>25580</td>
      <td>Pulí</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Cundinamarca</td>
      <td>25758</td>
      <td>Sopó</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Cundinamarca</td>
      <td>25779</td>
      <td>Susa</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Cundinamarca</td>
      <td>25797</td>
      <td>Tena</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Cundinamarca</td>
      <td>25845</td>
      <td>Une</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Chocó</td>
      <td>27745</td>
      <td>Sipí</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Chocó</td>
      <td>27787</td>
      <td>Tadó</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Huila</td>
      <td>41016</td>
      <td>Aipe</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Huila</td>
      <td>41349</td>
      <td>Hobo</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Nariño</td>
      <td>52352</td>
      <td>Iles</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Norte De Santander</td>
      <td>54810</td>
      <td>Tibú</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Risaralda</td>
      <td>66045</td>
      <td>Apía</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Santander</td>
      <td>68344</td>
      <td>Hato</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Santander</td>
      <td>68500</td>
      <td>Oiba</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Santander</td>
      <td>68820</td>
      <td>Tona</td>
    </tr>
    <tr>
      <th>33</th>
      <td>Valle Del Cauca</td>
      <td>76001</td>
      <td>Cali</td>
    </tr>
    <tr>
      <th>34</th>
      <td>Valle Del Cauca</td>
      <td>76823</td>
      <td>Toro</td>
    </tr>
    <tr>
      <th>35</th>
      <td>Arauca</td>
      <td>81794</td>
      <td>Tame</td>
    </tr>
    <tr>
      <th>36</th>
      <td>Casanare</td>
      <td>85139</td>
      <td>Maní</td>
    </tr>
    <tr>
      <th>37</th>
      <td>Casanare</td>
      <td>85263</td>
      <td>Pore</td>
    </tr>
    <tr>
      <th>38</th>
      <td>Vaupés</td>
      <td>97001</td>
      <td>Mitú</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios.describe()
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
      <th>Dep</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1118.000000</td>
      <td>1118.000000</td>
      <td>1117.000000</td>
      <td>1.118000e+03</td>
      <td>1118.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>38.349732</td>
      <td>38783.118068</td>
      <td>1020.431805</td>
      <td>4.409563e+04</td>
      <td>46.781753</td>
    </tr>
    <tr>
      <th>std</th>
      <td>26.610898</td>
      <td>26597.777329</td>
      <td>3217.701240</td>
      <td>2.603443e+05</td>
      <td>12.696186</td>
    </tr>
    <tr>
      <th>min</th>
      <td>5.000000</td>
      <td>5001.000000</td>
      <td>15.835319</td>
      <td>2.880000e+02</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>15.000000</td>
      <td>15677.250000</td>
      <td>132.755936</td>
      <td>6.614000e+03</td>
      <td>40.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>25.000000</td>
      <td>25844.000000</td>
      <td>287.043717</td>
      <td>1.279650e+04</td>
      <td>46.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>66.000000</td>
      <td>66588.500000</td>
      <td>704.100287</td>
      <td>2.750175e+04</td>
      <td>52.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>99.000000</td>
      <td>99773.000000</td>
      <td>65597.212354</td>
      <td>7.592871e+06</td>
      <td>100.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios.describe(percentiles=[0.1,0.25,0.5,0.75,0.9])
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
      <th>Dep</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1118.000000</td>
      <td>1118.000000</td>
      <td>1117.000000</td>
      <td>1.118000e+03</td>
      <td>1118.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>38.349732</td>
      <td>38783.118068</td>
      <td>1020.431805</td>
      <td>4.409563e+04</td>
      <td>46.781753</td>
    </tr>
    <tr>
      <th>std</th>
      <td>26.610898</td>
      <td>26597.777329</td>
      <td>3217.701240</td>
      <td>2.603443e+05</td>
      <td>12.696186</td>
    </tr>
    <tr>
      <th>min</th>
      <td>5.000000</td>
      <td>5001.000000</td>
      <td>15.835319</td>
      <td>2.880000e+02</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>10%</th>
      <td>5.000000</td>
      <td>5831.600000</td>
      <td>72.567740</td>
      <td>3.584400e+03</td>
      <td>34.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>15.000000</td>
      <td>15677.250000</td>
      <td>132.755936</td>
      <td>6.614000e+03</td>
      <td>40.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>25.000000</td>
      <td>25844.000000</td>
      <td>287.043717</td>
      <td>1.279650e+04</td>
      <td>46.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>66.000000</td>
      <td>66588.500000</td>
      <td>704.100287</td>
      <td>2.750175e+04</td>
      <td>52.000000</td>
    </tr>
    <tr>
      <th>90%</th>
      <td>76.000000</td>
      <td>76067.800000</td>
      <td>1643.209218</td>
      <td>5.822760e+04</td>
      <td>59.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>99.000000</td>
      <td>99773.000000</td>
      <td>65597.212354</td>
      <td>7.592871e+06</td>
      <td>100.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios.describe(include="object")
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
      <th>Municipio</th>
      <th>Region</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1118</td>
      <td>1118</td>
      <td>1118</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>33</td>
      <td>1030</td>
      <td>6</td>
    </tr>
    <tr>
      <th>top</th>
      <td>Antioquia</td>
      <td>Villanueva</td>
      <td>Región Centro Oriente</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>125</td>
      <td>4</td>
      <td>367</td>
    </tr>
  </tbody>
</table>
</div>




```python
def summary(y,include='numeric'):
    def numer(x):
        x2 = x.dropna()
        a = x.isna().sum()
        b = x2.mean()
        c = x2.std()
        d = c/b
        e = x2.skew()
        f = x2.kurt()
        g = x2.min()
        h = np.quantile(x2,0.25)
        i = x2.median()
        j = np.quantile(x2,0.75)
        k = x2.max()
        l = pd.Series({"Missings":a,"Mean":b,"St.dev":c,"Coef.var":d,"Skewness":e,
                       "Kurtosis":f,"Min":g,"%25":h,"Median":i,"%75":j,"Max":k})
        return(l)
    if include == 'numeric': 
        numerics = y.select_dtypes(include='number')
        if len(numerics.columns) > 0: return(numerics.apply(numer)) 
        else: print('Error. There are not numeric-type columns!!')
    if include == 'object':    
        objects = y.select_dtypes(include='object')
        if len(objects.columns) > 0: return(objects.describe(include="object"))
        else: print('Error. There are not object-type columns!!')
```


```python
summary(Municipios,include="numeric")
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
      <th>Dep</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Missings</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>0.000000e+00</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>Mean</th>
      <td>38.349732</td>
      <td>38783.118068</td>
      <td>1020.431805</td>
      <td>4.409563e+04</td>
      <td>46.781753</td>
    </tr>
    <tr>
      <th>St.dev</th>
      <td>26.610898</td>
      <td>26597.777329</td>
      <td>3217.701240</td>
      <td>2.603443e+05</td>
      <td>12.696186</td>
    </tr>
    <tr>
      <th>Coef.var</th>
      <td>0.693900</td>
      <td>0.685808</td>
      <td>3.153274</td>
      <td>5.904084e+00</td>
      <td>0.271392</td>
    </tr>
    <tr>
      <th>Skewness</th>
      <td>0.446924</td>
      <td>0.447253</td>
      <td>10.853250</td>
      <td>2.337790e+01</td>
      <td>0.704839</td>
    </tr>
    <tr>
      <th>Kurtosis</th>
      <td>-1.131617</td>
      <td>-1.128569</td>
      <td>174.834870</td>
      <td>6.454863e+02</td>
      <td>3.343991</td>
    </tr>
    <tr>
      <th>Min</th>
      <td>5.000000</td>
      <td>5001.000000</td>
      <td>15.835319</td>
      <td>2.880000e+02</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>%25</th>
      <td>15.000000</td>
      <td>15677.250000</td>
      <td>132.755936</td>
      <td>6.614000e+03</td>
      <td>40.000000</td>
    </tr>
    <tr>
      <th>Median</th>
      <td>25.000000</td>
      <td>25844.000000</td>
      <td>287.043717</td>
      <td>1.279650e+04</td>
      <td>46.000000</td>
    </tr>
    <tr>
      <th>%75</th>
      <td>66.000000</td>
      <td>66588.500000</td>
      <td>704.100287</td>
      <td>2.750175e+04</td>
      <td>52.000000</td>
    </tr>
    <tr>
      <th>Max</th>
      <td>99.000000</td>
      <td>99773.000000</td>
      <td>65597.212354</td>
      <td>7.592871e+06</td>
      <td>100.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
xx=summary(Municipios,include="object")

xx.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Index: 4 entries, count to freq
    Data columns (total 3 columns):
     #   Column        Non-Null Count  Dtype 
    ---  ------        --------------  ----- 
     0   Departamento  4 non-null      object
     1   Municipio     4 non-null      object
     2   Region        4 non-null      object
    dtypes: object(3)
    memory usage: 128.0+ bytes
    


```python
def summary(y,include='numeric'):
    def numer(x):
        x2 = x.dropna()
        a = x.isna().sum()
        b = x2.mean()
        c = x2.std()
        d = c/b
        e = x2.skew()
        f = x2.kurt()
        g = x2.min()
        h = np.quantile(x2,0.25)
        i = x2.median()
        j = np.quantile(x2,0.75)
        k = x2.max()

        moda =x2.mode()
        l = pd.Series({"Missings":a,"Mean":b,"St.dev":c,"Coef.var":d,"Skewness":e,
                       "Kurtosis":f,"Min":g,"%25":h,"Median":i,"%75":j,"Max":k,"moda":moda})
        return(l)
    if include == 'numeric': 
        numerics = y.select_dtypes(include='number')
        if len(numerics.columns) > 0: return(numerics.apply(numer)) 
        else: print('Error. There are not numeric-type columns!!')
    if include == 'object':    
        objects = y.select_dtypes(include='object')
        if len(objects.columns) > 0: return(objects.describe(include="object"))
        else: print('Error. There are not object-type columns!!')
```


```python
summary(Municipios, include="numeric")
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
      <th>Dep</th>
      <th>Depmun</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>Irural</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Missings</th>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>Mean</th>
      <td>38.349732</td>
      <td>38783.118068</td>
      <td>1020.431805</td>
      <td>44095.628801</td>
      <td>46.781753</td>
    </tr>
    <tr>
      <th>St.dev</th>
      <td>26.610898</td>
      <td>26597.777329</td>
      <td>3217.70124</td>
      <td>260344.317959</td>
      <td>12.696186</td>
    </tr>
    <tr>
      <th>Coef.var</th>
      <td>0.6939</td>
      <td>0.685808</td>
      <td>3.153274</td>
      <td>5.904084</td>
      <td>0.271392</td>
    </tr>
    <tr>
      <th>Skewness</th>
      <td>0.446924</td>
      <td>0.447253</td>
      <td>10.85325</td>
      <td>23.377897</td>
      <td>0.704839</td>
    </tr>
    <tr>
      <th>Kurtosis</th>
      <td>-1.131617</td>
      <td>-1.128569</td>
      <td>174.83487</td>
      <td>645.486336</td>
      <td>3.343991</td>
    </tr>
    <tr>
      <th>Min</th>
      <td>5</td>
      <td>5001</td>
      <td>15.835319</td>
      <td>288</td>
      <td>0</td>
    </tr>
    <tr>
      <th>%25</th>
      <td>15.0</td>
      <td>15677.25</td>
      <td>132.755936</td>
      <td>6614.0</td>
      <td>40.0</td>
    </tr>
    <tr>
      <th>Median</th>
      <td>25.0</td>
      <td>25844.0</td>
      <td>287.043717</td>
      <td>12796.5</td>
      <td>46.0</td>
    </tr>
    <tr>
      <th>%75</th>
      <td>66.0</td>
      <td>66588.5</td>
      <td>704.100287</td>
      <td>27501.75</td>
      <td>52.0</td>
    </tr>
    <tr>
      <th>Max</th>
      <td>99</td>
      <td>99773</td>
      <td>65597.212354</td>
      <td>7592871</td>
      <td>100</td>
    </tr>
    <tr>
      <th>moda</th>
      <td>0    5
dtype: int64</td>
      <td>0        5001
1        5002
2        5004
3   ...</td>
      <td>0          15.835319
1          19.649555
2   ...</td>
      <td>0      2883
1      4537
2      5146
3      517...</td>
      <td>0    48
dtype: int64</td>
    </tr>
  </tbody>
</table>
</div>




```python
Municipios.to_pickle("Municipios.pkl")
del Municipios
```


```python
Municipios = pd.read_pickle("Municipios.pkl")
Municipios.info()
Municipios.head(15)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1118 entries, 0 to 1117
    Data columns (total 8 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  1118 non-null   object 
     1   Dep           1118 non-null   int64  
     2   Municipio     1118 non-null   object 
     3   Depmun        1118 non-null   int64  
     4   Superficie    1117 non-null   float64
     5   Poblacion     1118 non-null   int64  
     6   Irural        1118 non-null   int64  
     7   Region        1118 non-null   object 
    dtypes: float64(1), int64(4), object(3)
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
      <td>Antioquia</td>
      <td>5</td>
      <td>Medellín</td>
      <td>5001</td>
      <td>374.830625</td>
      <td>2483545</td>
      <td>5</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Abejorral</td>
      <td>5002</td>
      <td>507.134114</td>
      <td>20258</td>
      <td>45</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Abriaquí</td>
      <td>5004</td>
      <td>296.955980</td>
      <td>2710</td>
      <td>58</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Alejandría</td>
      <td>5021</td>
      <td>128.932153</td>
      <td>4669</td>
      <td>48</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Amagá</td>
      <td>5030</td>
      <td>84.132477</td>
      <td>30777</td>
      <td>28</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Amalfi</td>
      <td>5031</td>
      <td>1209.126871</td>
      <td>26552</td>
      <td>54</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Andes</td>
      <td>5034</td>
      <td>402.502562</td>
      <td>43713</td>
      <td>38</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Angelópolis</td>
      <td>5036</td>
      <td>81.876302</td>
      <td>5790</td>
      <td>37</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Angostura</td>
      <td>5038</td>
      <td>338.666482</td>
      <td>11462</td>
      <td>47</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Anorí</td>
      <td>5040</td>
      <td>1413.773904</td>
      <td>18737</td>
      <td>58</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Santafé De Antioquia</td>
      <td>5042</td>
      <td>525.601375</td>
      <td>26598</td>
      <td>45</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Anza</td>
      <td>5044</td>
      <td>255.923314</td>
      <td>7085</td>
      <td>48</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Apartadó</td>
      <td>5045</td>
      <td>535.172377</td>
      <td>124647</td>
      <td>34</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Arboletes</td>
      <td>5051</td>
      <td>754.251902</td>
      <td>29942</td>
      <td>48</td>
      <td>Región Eje Cafetero</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>Argelia</td>
      <td>5055</td>
      <td>245.341782</td>
      <td>7577</td>
      <td>46</td>
      <td>Región Eje Cafetero</td>
    </tr>
  </tbody>
</table>
</div>




```python
from mismacrospython import onewayfreq, twowayfreq
help(pd.crosstab)
```

    Help on function crosstab in module pandas.core.reshape.pivot:
    
    crosstab(index, columns, values=None, rownames=None, colnames=None, aggfunc=None, margins=False, margins_name: str = 'All', dropna: bool = True, normalize=False) -> 'DataFrame'
        Compute a simple cross tabulation of two (or more) factors. By default
        computes a frequency table of the factors unless an array of values and an
        aggregation function are passed.
        
        Parameters
        ----------
        index : array-like, Series, or list of arrays/Series
            Values to group by in the rows.
        columns : array-like, Series, or list of arrays/Series
            Values to group by in the columns.
        values : array-like, optional
            Array of values to aggregate according to the factors.
            Requires `aggfunc` be specified.
        rownames : sequence, default None
            If passed, must match number of row arrays passed.
        colnames : sequence, default None
            If passed, must match number of column arrays passed.
        aggfunc : function, optional
            If specified, requires `values` be specified as well.
        margins : bool, default False
            Add row/column margins (subtotals).
        margins_name : str, default 'All'
            Name of the row/column that will contain the totals
            when margins is True.
        dropna : bool, default True
            Do not include columns whose entries are all NaN.
        normalize : bool, {'all', 'index', 'columns'}, or {0,1}, default False
            Normalize by dividing all values by the sum of values.
        
            - If passed 'all' or `True`, will normalize over all values.
            - If passed 'index' will normalize over each row.
            - If passed 'columns' will normalize over each column.
            - If margins is `True`, will also normalize margin values.
        
        Returns
        -------
        DataFrame
            Cross tabulation of the data.
        
        See Also
        --------
        DataFrame.pivot : Reshape data based on column values.
        pivot_table : Create a pivot table as a DataFrame.
        
        Notes
        -----
        Any Series passed will have their name attributes used unless row or column
        names for the cross-tabulation are specified.
        
        Any input passed containing Categorical data will have **all** of its
        categories included in the cross-tabulation, even if the actual data does
        not contain any instances of a particular category.
        
        In the event that there aren't overlapping indexes an empty DataFrame will
        be returned.
        
        Examples
        --------
        >>> a = np.array(["foo", "foo", "foo", "foo", "bar", "bar",
        ...               "bar", "bar", "foo", "foo", "foo"], dtype=object)
        >>> b = np.array(["one", "one", "one", "two", "one", "one",
        ...               "one", "two", "two", "two", "one"], dtype=object)
        >>> c = np.array(["dull", "dull", "shiny", "dull", "dull", "shiny",
        ...               "shiny", "dull", "shiny", "shiny", "shiny"],
        ...              dtype=object)
        >>> pd.crosstab(a, [b, c], rownames=['a'], colnames=['b', 'c'])
        b   one        two
        c   dull shiny dull shiny
        a
        bar    1     2    1     0
        foo    2     2    1     2
        
        Here 'c' and 'f' are not represented in the data and will not be
        shown in the output because dropna is True by default. Set
        dropna=False to preserve categories with no data.
        
        >>> foo = pd.Categorical(['a', 'b'], categories=['a', 'b', 'c'])
        >>> bar = pd.Categorical(['d', 'e'], categories=['d', 'e', 'f'])
        >>> pd.crosstab(foo, bar)
        col_0  d  e
        row_0
        a      1  0
        b      0  1
        >>> pd.crosstab(foo, bar, dropna=False)
        col_0  d  e  f
        row_0
        a      1  0  0
        b      0  1  0
        c      0  0  0
    
    


```python
onewayfreq(rows="Region",data=Municipios,ord="level")  

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
      <th>Region</th>
      <th>Frequency</th>
      <th>Percent</th>
      <th>CumulativeFrequency</th>
      <th>CumulativePercent</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Región Caribe</td>
      <td>194</td>
      <td>17.352415</td>
      <td>194</td>
      <td>17.352415</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Región Centro Oriente</td>
      <td>367</td>
      <td>32.826476</td>
      <td>561</td>
      <td>50.178891</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Región Centro Sur</td>
      <td>124</td>
      <td>11.091234</td>
      <td>685</td>
      <td>61.270125</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Región Eje Cafetero</td>
      <td>178</td>
      <td>15.921288</td>
      <td>863</td>
      <td>77.191413</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Región Llano</td>
      <td>78</td>
      <td>6.976744</td>
      <td>941</td>
      <td>84.168157</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Región Pacífico</td>
      <td>177</td>
      <td>15.831843</td>
      <td>1118</td>
      <td>100.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.crosstab(Municipios.Region,"Result",colnames=" ").sort_values("Result",ascending=False)
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
      <th>Result</th>
    </tr>
    <tr>
      <th>Region</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Región Centro Oriente</th>
      <td>367</td>
    </tr>
    <tr>
      <th>Región Caribe</th>
      <td>194</td>
    </tr>
    <tr>
      <th>Región Eje Cafetero</th>
      <td>178</td>
    </tr>
    <tr>
      <th>Región Pacífico</th>
      <td>177</td>
    </tr>
    <tr>
      <th>Región Centro Sur</th>
      <td>124</td>
    </tr>
    <tr>
      <th>Región Llano</th>
      <td>78</td>
    </tr>
  </tbody>
</table>
</div>




```python
onewayfreq(rows="Region",data=Municipios,ord="level",cum=False)
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
      <th>Region</th>
      <th>Frequency</th>
      <th>Percent</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Región Caribe</td>
      <td>194</td>
      <td>17.352415</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Región Centro Oriente</td>
      <td>367</td>
      <td>32.826476</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Región Centro Sur</td>
      <td>124</td>
      <td>11.091234</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Región Eje Cafetero</td>
      <td>178</td>
      <td>15.921288</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Región Llano</td>
      <td>78</td>
      <td>6.976744</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Región Pacífico</td>
      <td>177</td>
      <td>15.831843</td>
    </tr>
  </tbody>
</table>
</div>




```python
onewayfreq(rows="Region",weight="Poblacion",data=Municipios,ord="-freq", cum= False)
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
      <th>Region</th>
      <th>Frequency</th>
      <th>Percent</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Región Llano</td>
      <td>2048306</td>
      <td>4.154871</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Región Centro Sur</td>
      <td>3284811</td>
      <td>6.663050</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Región Pacífico</td>
      <td>8134239</td>
      <td>16.499834</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Región Eje Cafetero</td>
      <td>9058916</td>
      <td>18.375488</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Región Caribe</td>
      <td>11060389</td>
      <td>22.435361</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Región Centro Oriente</td>
      <td>15712252</td>
      <td>31.871396</td>
    </tr>
  </tbody>
</table>
</div>




```python
onewayfreq(rows="Departamento",weight="Poblacion",data=Municipios.query("Municipios.Región =='Región pacífico'"),ord="freq")
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    C:\Anaconda\lib\site-packages\pandas\core\computation\scope.py in resolve(self, key, is_local)
        200             if self.has_resolvers:
    --> 201                 return self.resolvers[key]
        202 
    

    C:\Anaconda\lib\collections\__init__.py in __getitem__(self, key)
        897                 pass
    --> 898         return self.__missing__(key)            # support subclasses that define __missing__
        899 
    

    C:\Anaconda\lib\collections\__init__.py in __missing__(self, key)
        889     def __missing__(self, key):
    --> 890         raise KeyError(key)
        891 
    

    KeyError: 'Municipios'

    
    During handling of the above exception, another exception occurred:
    

    KeyError                                  Traceback (most recent call last)

    C:\Anaconda\lib\site-packages\pandas\core\computation\scope.py in resolve(self, key, is_local)
        211                 # e.g., df[df > 0]
    --> 212                 return self.temps[key]
        213             except KeyError as err:
    

    KeyError: 'Municipios'

    
    The above exception was the direct cause of the following exception:
    

    UndefinedVariableError                    Traceback (most recent call last)

    <ipython-input-81-7b7409eafc8d> in <module>
    ----> 1 onewayfreq(rows="Departamento",weight="Poblacion",data=Municipios.query("Municipios.Región =='Región pacífico'"),ord="freq")
    

    C:\Anaconda\lib\site-packages\pandas\core\frame.py in query(self, expr, inplace, **kwargs)
       3467         kwargs["level"] = kwargs.pop("level", 0) + 1
       3468         kwargs["target"] = None
    -> 3469         res = self.eval(expr, **kwargs)
       3470 
       3471         try:
    

    C:\Anaconda\lib\site-packages\pandas\core\frame.py in eval(self, expr, inplace, **kwargs)
       3597         kwargs["resolvers"] = kwargs.get("resolvers", ()) + tuple(resolvers)
       3598 
    -> 3599         return _eval(expr, inplace=inplace, **kwargs)
       3600 
       3601     def select_dtypes(self, include=None, exclude=None) -> DataFrame:
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\eval.py in eval(expr, parser, engine, truediv, local_dict, global_dict, resolvers, level, target, inplace)
        340         )
        341 
    --> 342         parsed_expr = Expr(expr, engine=engine, parser=parser, env=env)
        343 
        344         # construct the engine and evaluate the parsed expression
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in __init__(self, expr, engine, parser, env, level)
        796         self.parser = parser
        797         self._visitor = PARSERS[parser](self.env, self.engine, self.parser)
    --> 798         self.terms = self.parse()
        799 
        800     @property
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in parse(self)
        815         Parse an expression.
        816         """
    --> 817         return self._visitor.visit(self.expr)
        818 
        819     @property
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit(self, node, **kwargs)
        399         method = "visit_" + type(node).__name__
        400         visitor = getattr(self, method)
    --> 401         return visitor(node, **kwargs)
        402 
        403     def visit_Module(self, node, **kwargs):
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit_Module(self, node, **kwargs)
        405             raise SyntaxError("only a single expression is allowed")
        406         expr = node.body[0]
    --> 407         return self.visit(expr, **kwargs)
        408 
        409     def visit_Expr(self, node, **kwargs):
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit(self, node, **kwargs)
        399         method = "visit_" + type(node).__name__
        400         visitor = getattr(self, method)
    --> 401         return visitor(node, **kwargs)
        402 
        403     def visit_Module(self, node, **kwargs):
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit_Expr(self, node, **kwargs)
        408 
        409     def visit_Expr(self, node, **kwargs):
    --> 410         return self.visit(node.value, **kwargs)
        411 
        412     def _rewrite_membership_op(self, node, left, right):
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit(self, node, **kwargs)
        399         method = "visit_" + type(node).__name__
        400         visitor = getattr(self, method)
    --> 401         return visitor(node, **kwargs)
        402 
        403     def visit_Module(self, node, **kwargs):
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit_Compare(self, node, **kwargs)
        708             op = self.translate_In(ops[0])
        709             binop = ast.BinOp(op=op, left=node.left, right=comps[0])
    --> 710             return self.visit(binop)
        711 
        712         # recursive case: we have a chained comparison, a CMP b CMP c, etc.
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit(self, node, **kwargs)
        399         method = "visit_" + type(node).__name__
        400         visitor = getattr(self, method)
    --> 401         return visitor(node, **kwargs)
        402 
        403     def visit_Module(self, node, **kwargs):
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit_BinOp(self, node, **kwargs)
        520 
        521     def visit_BinOp(self, node, **kwargs):
    --> 522         op, op_class, left, right = self._maybe_transform_eq_ne(node)
        523         left, right = self._maybe_downcast_constants(left, right)
        524         return self._maybe_evaluate_binop(op, op_class, left, right)
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in _maybe_transform_eq_ne(self, node, left, right)
        440     def _maybe_transform_eq_ne(self, node, left=None, right=None):
        441         if left is None:
    --> 442             left = self.visit(node.left, side="left")
        443         if right is None:
        444             right = self.visit(node.right, side="right")
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit(self, node, **kwargs)
        399         method = "visit_" + type(node).__name__
        400         visitor = getattr(self, method)
    --> 401         return visitor(node, **kwargs)
        402 
        403     def visit_Module(self, node, **kwargs):
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit_Attribute(self, node, **kwargs)
        629         if isinstance(ctx, ast.Load):
        630             # resolve the value
    --> 631             resolved = self.visit(value).value
        632             try:
        633                 v = getattr(resolved, attr)
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit(self, node, **kwargs)
        399         method = "visit_" + type(node).__name__
        400         visitor = getattr(self, method)
    --> 401         return visitor(node, **kwargs)
        402 
        403     def visit_Module(self, node, **kwargs):
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\expr.py in visit_Name(self, node, **kwargs)
        533 
        534     def visit_Name(self, node, **kwargs):
    --> 535         return self.term_type(node.id, self.env, **kwargs)
        536 
        537     def visit_NameConstant(self, node, **kwargs):
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\ops.py in __init__(self, name, env, side, encoding)
         84         tname = str(name)
         85         self.is_local = tname.startswith(LOCAL_TAG) or tname in DEFAULT_GLOBALS
    ---> 86         self._value = self._resolve_name()
         87         self.encoding = encoding
         88 
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\ops.py in _resolve_name(self)
        101 
        102     def _resolve_name(self):
    --> 103         res = self.env.resolve(self.local_name, is_local=self.is_local)
        104         self.update(res)
        105 
    

    C:\Anaconda\lib\site-packages\pandas\core\computation\scope.py in resolve(self, key, is_local)
        215                 from pandas.core.computation.ops import UndefinedVariableError
        216 
    --> 217                 raise UndefinedVariableError(key, is_local) from err
        218 
        219     def swapkey(self, old_key: str, new_key: str, new_value=None):
    

    UndefinedVariableError: name 'Municipios' is not defined



```python
onewayfreq(rows="Region",weight="Superficie",data=Municipios,ord="freq")   
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
      <th>Region</th>
      <th>Frequency</th>
      <th>Percent</th>
      <th>CumulativeFrequency</th>
      <th>CumulativePercent</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Región Llano</td>
      <td>434000.024944</td>
      <td>38.076112</td>
      <td>4.340000e+05</td>
      <td>38.076112</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Región Centro Sur</td>
      <td>267857.406873</td>
      <td>23.499926</td>
      <td>7.018574e+05</td>
      <td>61.576038</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Región Pacífico</td>
      <td>131660.385197</td>
      <td>11.550957</td>
      <td>8.335178e+05</td>
      <td>73.126995</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Región Caribe</td>
      <td>131034.591860</td>
      <td>11.496054</td>
      <td>9.645524e+05</td>
      <td>84.623049</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Región Centro Oriente</td>
      <td>99549.641780</td>
      <td>8.733786</td>
      <td>1.064102e+06</td>
      <td>93.356835</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Región Eje Cafetero</td>
      <td>75720.275955</td>
      <td>6.643165</td>
      <td>1.139822e+06</td>
      <td>100.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.crosstab(Municipios.Region,"Result",values=Municipios.Superficie,aggfunc=sum,colnames=" ").sort_values("Result",ascending=False)
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
      <th>Result</th>
    </tr>
    <tr>
      <th>Region</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Región Llano</th>
      <td>434000.024944</td>
    </tr>
    <tr>
      <th>Región Centro Sur</th>
      <td>267857.406873</td>
    </tr>
    <tr>
      <th>Región Pacífico</th>
      <td>131660.385197</td>
    </tr>
    <tr>
      <th>Región Caribe</th>
      <td>131034.591860</td>
    </tr>
    <tr>
      <th>Región Centro Oriente</th>
      <td>99549.641780</td>
    </tr>
    <tr>
      <th>Región Eje Cafetero</th>
      <td>75720.275955</td>
    </tr>
  </tbody>
</table>
</div>




```python
twowayfreq(rows="Region",columns="Zona",data=Municipios,ord="freq",rowpercent=True,colpercent=True)
```

    Frequency
    Row percent
    Col percent
     
    




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
      <th>Region  /  Zona</th>
      <th>Rural</th>
      <th>Urbano</th>
      <th>Total</th>
    </tr>
    <tr>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Región Centro Oriente</td>
      <td>273.000000</td>
      <td>94.000000</td>
      <td>367.000000</td>
    </tr>
    <tr>
      <th>1</th>
      <td></td>
      <td>74.386921</td>
      <td>25.613079</td>
      <td>100.000000</td>
    </tr>
    <tr>
      <th>2</th>
      <td></td>
      <td>33.211679</td>
      <td>31.756757</td>
      <td>32.826476</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Región Caribe</td>
      <td>140.000000</td>
      <td>54.000000</td>
      <td>194.000000</td>
    </tr>
    <tr>
      <th>4</th>
      <td></td>
      <td>72.164948</td>
      <td>27.835052</td>
      <td>100.000000</td>
    </tr>
    <tr>
      <th>5</th>
      <td></td>
      <td>17.031630</td>
      <td>18.243243</td>
      <td>17.352415</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Región Eje Cafetero</td>
      <td>102.000000</td>
      <td>76.000000</td>
      <td>178.000000</td>
    </tr>
    <tr>
      <th>7</th>
      <td></td>
      <td>57.303371</td>
      <td>42.696629</td>
      <td>100.000000</td>
    </tr>
    <tr>
      <th>8</th>
      <td></td>
      <td>12.408759</td>
      <td>25.675676</td>
      <td>15.921288</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Región Pacífico</td>
      <td>121.000000</td>
      <td>56.000000</td>
      <td>177.000000</td>
    </tr>
    <tr>
      <th>10</th>
      <td></td>
      <td>68.361582</td>
      <td>31.638418</td>
      <td>100.000000</td>
    </tr>
    <tr>
      <th>11</th>
      <td></td>
      <td>14.720195</td>
      <td>18.918919</td>
      <td>15.831843</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Región Centro Sur</td>
      <td>110.000000</td>
      <td>14.000000</td>
      <td>124.000000</td>
    </tr>
    <tr>
      <th>13</th>
      <td></td>
      <td>88.709677</td>
      <td>11.290323</td>
      <td>100.000000</td>
    </tr>
    <tr>
      <th>14</th>
      <td></td>
      <td>13.381995</td>
      <td>4.729730</td>
      <td>11.091234</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Región Llano</td>
      <td>76.000000</td>
      <td>2.000000</td>
      <td>78.000000</td>
    </tr>
    <tr>
      <th>16</th>
      <td></td>
      <td>97.435897</td>
      <td>2.564103</td>
      <td>100.000000</td>
    </tr>
    <tr>
      <th>17</th>
      <td></td>
      <td>9.245742</td>
      <td>0.675676</td>
      <td>6.976744</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Total</td>
      <td>822.000000</td>
      <td>296.000000</td>
      <td>1118.000000</td>
    </tr>
    <tr>
      <th>19</th>
      <td></td>
      <td>73.524150</td>
      <td>26.475850</td>
      <td>100.000000</td>
    </tr>
    <tr>
      <th>20</th>
      <td></td>
      <td>100.000000</td>
      <td>100.000000</td>
      <td>100.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
def zona(x): 
    if x  > 40: return("Rural")
    if x <= 40: return("Urbano")
    
Municipios["Zona"] = Municipios["Irural"].apply(zona)
Municipios.loc[Municipios["Irural"] >  40,"Zona2"] = "Rural" 
Municipios.loc[Municipios["Irural"] <= 40,"Zona2"] = "Urbano"
Municipios["Zona"].equals(Municipios["Zona2"])
Municipios = Municipios.drop(columns="Zona2")
```


```python
twowayfreq(rows="Region",columns="Zona",weight="Superficie",data=Municipios,ord="freq",rowpercent=True,colpercent=True)
```

    Frequency
    Row percent
    Col percent
     
    




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
      <th>Region  /  Zona</th>
      <th>Rural</th>
      <th>Urbano</th>
      <th>Total</th>
    </tr>
    <tr>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Región Llano</td>
      <td>4.323658e+05</td>
      <td>1634.191141</td>
      <td>4.340000e+05</td>
    </tr>
    <tr>
      <th>1</th>
      <td></td>
      <td>9.962346e+01</td>
      <td>0.376542</td>
      <td>1.000000e+02</td>
    </tr>
    <tr>
      <th>2</th>
      <td></td>
      <td>4.063276e+01</td>
      <td>2.157617</td>
      <td>3.807611e+01</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Región Centro Sur</td>
      <td>2.620089e+05</td>
      <td>5848.459198</td>
      <td>2.678574e+05</td>
    </tr>
    <tr>
      <th>4</th>
      <td></td>
      <td>9.781658e+01</td>
      <td>2.183423</td>
      <td>1.000000e+02</td>
    </tr>
    <tr>
      <th>5</th>
      <td></td>
      <td>2.462301e+01</td>
      <td>7.721701</td>
      <td>2.349993e+01</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Región Pacífico</td>
      <td>1.139543e+05</td>
      <td>17706.071649</td>
      <td>1.316604e+05</td>
    </tr>
    <tr>
      <th>7</th>
      <td></td>
      <td>8.655171e+01</td>
      <td>13.448291</td>
      <td>1.000000e+02</td>
    </tr>
    <tr>
      <th>8</th>
      <td></td>
      <td>1.070917e+01</td>
      <td>23.377265</td>
      <td>1.155096e+01</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Región Caribe</td>
      <td>1.091550e+05</td>
      <td>21879.637605</td>
      <td>1.310346e+05</td>
    </tr>
    <tr>
      <th>10</th>
      <td></td>
      <td>8.330240e+01</td>
      <td>16.697604</td>
      <td>1.000000e+02</td>
    </tr>
    <tr>
      <th>11</th>
      <td></td>
      <td>1.025814e+01</td>
      <td>28.887610</td>
      <td>1.149605e+01</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Región Centro Oriente</td>
      <td>8.443118e+04</td>
      <td>15118.462392</td>
      <td>9.954964e+04</td>
    </tr>
    <tr>
      <th>13</th>
      <td></td>
      <td>8.481314e+01</td>
      <td>15.186858</td>
      <td>1.000000e+02</td>
    </tr>
    <tr>
      <th>14</th>
      <td></td>
      <td>7.934651e+00</td>
      <td>19.960854</td>
      <td>8.733786e+00</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Región Eje Cafetero</td>
      <td>6.216654e+04</td>
      <td>13553.737943</td>
      <td>7.572028e+04</td>
    </tr>
    <tr>
      <th>16</th>
      <td></td>
      <td>8.210025e+01</td>
      <td>17.899747</td>
      <td>1.000000e+02</td>
    </tr>
    <tr>
      <th>17</th>
      <td></td>
      <td>5.842271e+00</td>
      <td>17.894953</td>
      <td>6.643165e+00</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Total</td>
      <td>1.064082e+06</td>
      <td>75740.559927</td>
      <td>1.139822e+06</td>
    </tr>
    <tr>
      <th>19</th>
      <td></td>
      <td>9.335506e+01</td>
      <td>6.644944</td>
      <td>1.000000e+02</td>
    </tr>
    <tr>
      <th>20</th>
      <td></td>
      <td>1.000000e+02</td>
      <td>100.000000</td>
      <td>1.000000e+02</td>
    </tr>
  </tbody>
</table>
</div>



## PANDAAAS


```python
!pip install duckdb
import duckdb
con = duckdb.connect(database=':memory:')
```

    Collecting duckdb
      Downloading duckdb-0.6.0-cp38-cp38-win_amd64.whl (9.0 MB)
    Requirement already satisfied: numpy>=1.14 in c:\anaconda\lib\site-packages (from duckdb) (1.20.1)
    Installing collected packages: duckdb
    Successfully installed duckdb-0.6.0
    

      WARNING: Retrying (Retry(total=4, connect=None, read=None, redirect=None, status=None)) after connection broken by 'ReadTimeoutError("HTTPSConnectionPool(host='files.pythonhosted.org', port=443): Read timed out. (read timeout=15)")': /packages/06/ed/11e96ae3faf62e83d0cf95962b7b8611f00dda0dcdf39b9402cbe6122ab9/duckdb-0.6.0-cp38-cp38-win_amd64.whl
    


```python
E1 = con.execute("""select   Departamento, Dep, Depmun, Municipio, Superficie, Poblacion
                    from     Municipios
                    where    Dep in ('05','17') and Poblacion > 20000
                    order by Dep asc, Poblacion desc""").df()

E1.info()
E1.head()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 10 entries, 0 to 9
    Data columns (total 6 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  10 non-null     object 
     1   Dep           10 non-null     int64  
     2   Depmun        10 non-null     int64  
     3   Municipio     10 non-null     object 
     4   Superficie    10 non-null     float64
     5   Poblacion     10 non-null     int64  
    dtypes: float64(1), int64(3), object(2)
    memory usage: 608.0+ bytes
    




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
      <th>Depmun</th>
      <th>Municipio</th>
      <th>Superficie</th>
      <th>Poblacion</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Caldas</td>
      <td>17</td>
      <td>17001</td>
      <td>Manizales</td>
      <td>441.001655</td>
      <td>440608</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Caldas</td>
      <td>17</td>
      <td>17380</td>
      <td>La Dorada</td>
      <td>549.236341</td>
      <td>72972</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Caldas</td>
      <td>17</td>
      <td>17873</td>
      <td>Villamaría</td>
      <td>455.065833</td>
      <td>66189</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Caldas</td>
      <td>17</td>
      <td>17174</td>
      <td>Chinchiná</td>
      <td>109.372658</td>
      <td>51773</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Caldas</td>
      <td>17</td>
      <td>17614</td>
      <td>Riosucio</td>
      <td>384.169470</td>
      <td>51371</td>
    </tr>
  </tbody>
</table>
</div>




```python
e1 = (Municipios
      .loc[:,["Departamento","Dep","Depmun","Municipio","Superficie","Poblacion"]] 
      .query("Poblacion > 20000 & Dep in ('05','17')")
      .sort_values(by=["Dep","Poblacion"],ascending=[True,False]).reset_index(drop=True)
     )

e1.info()

E1.equals(e1)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 0 entries
    Data columns (total 6 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  0 non-null      object 
     1   Dep           0 non-null      int64  
     2   Depmun        0 non-null      int64  
     3   Municipio     0 non-null      object 
     4   Superficie    0 non-null      float64
     5   Poblacion     0 non-null      int64  
    dtypes: float64(1), int64(3), object(2)
    memory usage: 124.0+ bytes
    




    False




```python
e1.head(10)
print(Municipios)
```

         Departamento  Dep       Municipio  Depmun    Superficie  Poblacion  \
    0       Antioquia    5        Medellín    5001    374.830625    2483545   
    1       Antioquia    5       Abejorral    5002    507.134114      20258   
    2       Antioquia    5        Abriaquí    5004    296.955980       2710   
    3       Antioquia    5      Alejandría    5021    128.932153       4669   
    4       Antioquia    5           Amagá    5030     84.132477      30777   
    ...           ...  ...             ...     ...           ...        ...   
    1113       Vaupés   97        Yavaraté   97889   4660.405650       1067   
    1114      Vichada   99  Puerto Carreño   99001  12204.951401      20474   
    1115      Vichada   99    La Primavera   99524  18569.337656       9799   
    1116      Vichada   99   Santa Rosalía   99624   3691.869191       4130   
    1117      Vichada   99        Cumaribo   99773  65597.212354      76196   
    
          Irural               Region    Zona  
    0          5  Región Eje Cafetero  Urbano  
    1         45  Región Eje Cafetero   Rural  
    2         58  Región Eje Cafetero   Rural  
    3         48  Región Eje Cafetero   Rural  
    4         28  Región Eje Cafetero  Urbano  
    ...      ...                  ...     ...  
    1113      92         Región Llano   Rural  
    1114      81         Región Llano   Rural  
    1115      85         Región Llano   Rural  
    1116      81         Región Llano   Rural  
    1117      87         Región Llano   Rural  
    
    [1118 rows x 9 columns]
    


```python
e2 = Municipios.copy()
e2["denspoblC"] = pd.cut(e2["denspobl"],[np.NINF,30,85,np.inf],labels=["Baja","Media","Alta"]).astype("object")

e2 = (e2
      .loc[:,["Departamento","Dep","Depmun","Municipio","Superficie","Poblacion", "denspoblC"]] 
      .query("Dep not in ('15','68') & Superficie < 300")
      .sort_values(by=["Dep","Poblacion"],ascending=[True,False]).reset_index(drop=True)
     )

e2.info()
e2.head(10)

```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 572 entries, 0 to 571
    Data columns (total 7 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Departamento  572 non-null    object 
     1   Dep           572 non-null    int64  
     2   Depmun        572 non-null    int64  
     3   Municipio     572 non-null    object 
     4   Superficie    572 non-null    float64
     5   Poblacion     572 non-null    int64  
     6   denspoblC     572 non-null    object 
    dtypes: float64(1), int64(3), object(3)
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
      <th>Departamento</th>
      <th>Dep</th>
      <th>Depmun</th>
      <th>Municipio</th>
      <th>Superficie</th>
      <th>Poblacion</th>
      <th>denspoblC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5088</td>
      <td>Bello</td>
      <td>147.758418</td>
      <td>538527</td>
      <td>Alta</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5360</td>
      <td>Itagui</td>
      <td>19.649555</td>
      <td>283794</td>
      <td>Alta</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5266</td>
      <td>Envigado</td>
      <td>77.996703</td>
      <td>236114</td>
      <td>Alta</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5615</td>
      <td>Rionegro</td>
      <td>195.940149</td>
      <td>139553</td>
      <td>Alta</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5631</td>
      <td>Sabaneta</td>
      <td>15.835319</td>
      <td>85484</td>
      <td>Alta</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5129</td>
      <td>Caldas</td>
      <td>132.755936</td>
      <td>81658</td>
      <td>Alta</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5212</td>
      <td>Copacabana</td>
      <td>67.760717</td>
      <td>80000</td>
      <td>Alta</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5380</td>
      <td>La Estrella</td>
      <td>36.631794</td>
      <td>73696</td>
      <td>Alta</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5376</td>
      <td>La Ceja</td>
      <td>132.714953</td>
      <td>66746</td>
      <td>Alta</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Antioquia</td>
      <td>5</td>
      <td>5440</td>
      <td>Marinilla</td>
      <td>114.871201</td>
      <td>66399</td>
      <td>Alta</td>
    </tr>
  </tbody>
</table>
</div>




```python
(Municipios
 .groupby("Depmun")
 .agg(conteo=("Depmun","count")).reset_index()
 .query("conteo > 1")
)
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
      <th>Depmun</th>
      <th>conteo</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
</table>
</div>




```python
def rango(x): 
    return(x.max()- x.min())

(Municipios
 .groupby(["Dep","Departamento"])
 .agg(conteo=("Depmun","count"),
      rango=("Superficie",rango)).reset_index()
 .query("conteo > 1")

 
)

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
      <th>Dep</th>
      <th>Departamento</th>
      <th>conteo</th>
      <th>rango</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5</td>
      <td>Antioquia</td>
      <td>125</td>
      <td>2903.700011</td>
    </tr>
    <tr>
      <th>1</th>
      <td>8</td>
      <td>Atlántico</td>
      <td>23</td>
      <td>353.316322</td>
    </tr>
    <tr>
      <th>3</th>
      <td>13</td>
      <td>Bolívar</td>
      <td>45</td>
      <td>2340.513566</td>
    </tr>
    <tr>
      <th>4</th>
      <td>15</td>
      <td>Boyacá</td>
      <td>123</td>
      <td>1488.248322</td>
    </tr>
    <tr>
      <th>5</th>
      <td>17</td>
      <td>Caldas</td>
      <td>27</td>
      <td>721.289264</td>
    </tr>
    <tr>
      <th>6</th>
      <td>18</td>
      <td>Caquetá</td>
      <td>16</td>
      <td>41909.425361</td>
    </tr>
    <tr>
      <th>7</th>
      <td>19</td>
      <td>Cauca</td>
      <td>41</td>
      <td>3562.718390</td>
    </tr>
    <tr>
      <th>8</th>
      <td>20</td>
      <td>Cesar</td>
      <td>25</td>
      <td>4112.785680</td>
    </tr>
    <tr>
      <th>9</th>
      <td>23</td>
      <td>Córdoba</td>
      <td>28</td>
      <td>4849.454400</td>
    </tr>
    <tr>
      <th>10</th>
      <td>25</td>
      <td>Cundinamarca</td>
      <td>116</td>
      <td>1153.692083</td>
    </tr>
    <tr>
      <th>11</th>
      <td>27</td>
      <td>Chocó</td>
      <td>30</td>
      <td>7429.791089</td>
    </tr>
    <tr>
      <th>12</th>
      <td>41</td>
      <td>Huila</td>
      <td>37</td>
      <td>1504.528175</td>
    </tr>
    <tr>
      <th>13</th>
      <td>44</td>
      <td>La Guajira</td>
      <td>15</td>
      <td>7706.467280</td>
    </tr>
    <tr>
      <th>14</th>
      <td>47</td>
      <td>Magdalena</td>
      <td>30</td>
      <td>2237.655583</td>
    </tr>
    <tr>
      <th>15</th>
      <td>50</td>
      <td>Meta</td>
      <td>29</td>
      <td>17132.742083</td>
    </tr>
    <tr>
      <th>16</th>
      <td>52</td>
      <td>Nariño</td>
      <td>64</td>
      <td>3586.198018</td>
    </tr>
    <tr>
      <th>17</th>
      <td>54</td>
      <td>Norte De Santander</td>
      <td>40</td>
      <td>2635.127514</td>
    </tr>
    <tr>
      <th>18</th>
      <td>63</td>
      <td>Quindío</td>
      <td>12</td>
      <td>308.861849</td>
    </tr>
    <tr>
      <th>19</th>
      <td>66</td>
      <td>Risaralda</td>
      <td>14</td>
      <td>580.966600</td>
    </tr>
    <tr>
      <th>20</th>
      <td>68</td>
      <td>Santander</td>
      <td>87</td>
      <td>3154.594097</td>
    </tr>
    <tr>
      <th>21</th>
      <td>70</td>
      <td>Sucre</td>
      <td>26</td>
      <td>1437.607802</td>
    </tr>
    <tr>
      <th>22</th>
      <td>73</td>
      <td>Tolima</td>
      <td>47</td>
      <td>2037.052107</td>
    </tr>
    <tr>
      <th>23</th>
      <td>76</td>
      <td>Valle Del Cauca</td>
      <td>42</td>
      <td>6250.549379</td>
    </tr>
    <tr>
      <th>24</th>
      <td>81</td>
      <td>Arauca</td>
      <td>7</td>
      <td>4842.862681</td>
    </tr>
    <tr>
      <th>25</th>
      <td>85</td>
      <td>Casanare</td>
      <td>19</td>
      <td>11933.815462</td>
    </tr>
    <tr>
      <th>26</th>
      <td>86</td>
      <td>Putumayo</td>
      <td>13</td>
      <td>10842.602196</td>
    </tr>
    <tr>
      <th>27</th>
      <td>88</td>
      <td>San Andrés</td>
      <td>2</td>
      <td>4.855334</td>
    </tr>
    <tr>
      <th>28</th>
      <td>91</td>
      <td>Amazonas</td>
      <td>11</td>
      <td>15434.737560</td>
    </tr>
    <tr>
      <th>29</th>
      <td>94</td>
      <td>Guainía</td>
      <td>9</td>
      <td>14791.327905</td>
    </tr>
    <tr>
      <th>30</th>
      <td>95</td>
      <td>Guaviare</td>
      <td>4</td>
      <td>4326.289349</td>
    </tr>
    <tr>
      <th>31</th>
      <td>97</td>
      <td>Vaupés</td>
      <td>6</td>
      <td>11555.331614</td>
    </tr>
    <tr>
      <th>32</th>
      <td>99</td>
      <td>Vichada</td>
      <td>4</td>
      <td>61905.343163</td>
    </tr>
  </tbody>
</table>
</div>




```python
def wtmean(x):
    w = Municipios.loc[x.index,"Poblacion"]
    return(sum(x*w)/sum(w))

def cases(x):
    out = "Mediano"
    if sum(x) < 300000:  out= "Pequeño"
    if sum(x) > 1500000: out= "Grande"
    return(out)    

e6 = (Municipios
      .groupby(["Dep","Departamento"])
      .agg(nmunicipios=("Depmun","count"),
           totpob=("Poblacion","sum"),
           totsup=("Superficie","sum"),
           Irural=("Irural",wtmean),
           totpobC=("Poblacion",cases)).reset_index()
      .eval('''denspob = totpob/totsup''')
      .sort_values(by=["totpob"],ascending=False).reset_index(drop=True)
     )

e6 = e6[["Dep","Departamento","nmunicipios","totpob","totsup","Irural","denspob","totpobC"]]
e6.info()
e6.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 33 entries, 0 to 32
    Data columns (total 8 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Dep           33 non-null     int64  
     1   Departamento  33 non-null     object 
     2   nmunicipios   33 non-null     int64  
     3   totpob        33 non-null     int64  
     4   totsup        33 non-null     float64
     5   Irural        33 non-null     float64
     6   denspob       33 non-null     float64
     7   totpobC       33 non-null     object 
    dtypes: float64(3), int64(3), object(2)
    memory usage: 2.2+ KB
    




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
      <th>nmunicipios</th>
      <th>totpob</th>
      <th>totsup</th>
      <th>Irural</th>
      <th>denspob</th>
      <th>totpobC</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>11</td>
      <td>Bogotá D C</td>
      <td>1</td>
      <td>7592871</td>
      <td>1622.852605</td>
      <td>6.000000</td>
      <td>4678.718805</td>
      <td>Grande</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>Antioquia</td>
      <td>125</td>
      <td>6550206</td>
      <td>62804.708984</td>
      <td>21.318767</td>
      <td>104.294823</td>
      <td>Grande</td>
    </tr>
    <tr>
      <th>2</th>
      <td>76</td>
      <td>Valle Del Cauca</td>
      <td>42</td>
      <td>4506768</td>
      <td>20665.544525</td>
      <td>22.575783</td>
      <td>218.081261</td>
      <td>Grande</td>
    </tr>
    <tr>
      <th>3</th>
      <td>25</td>
      <td>Cundinamarca</td>
      <td>116</td>
      <td>3085522</td>
      <td>22370.488731</td>
      <td>26.532552</td>
      <td>137.928234</td>
      <td>Grande</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8</td>
      <td>Atlántico</td>
      <td>23</td>
      <td>2638151</td>
      <td>3315.752105</td>
      <td>10.927528</td>
      <td>795.641808</td>
      <td>Grande</td>
    </tr>
    <tr>
      <th>5</th>
      <td>68</td>
      <td>Santander</td>
      <td>87</td>
      <td>2237587</td>
      <td>30561.497859</td>
      <td>29.392340</td>
      <td>73.215881</td>
      <td>Grande</td>
    </tr>
    <tr>
      <th>6</th>
      <td>13</td>
      <td>Bolívar</td>
      <td>45</td>
      <td>2120925</td>
      <td>26302.809942</td>
      <td>31.395768</td>
      <td>80.634921</td>
      <td>Grande</td>
    </tr>
    <tr>
      <th>7</th>
      <td>23</td>
      <td>Córdoba</td>
      <td>28</td>
      <td>1741111</td>
      <td>24454.516177</td>
      <td>41.885961</td>
      <td>71.197933</td>
      <td>Grande</td>
    </tr>
    <tr>
      <th>8</th>
      <td>52</td>
      <td>Nariño</td>
      <td>64</td>
      <td>1628981</td>
      <td>31497.572567</td>
      <td>40.664683</td>
      <td>51.717668</td>
      <td>Grande</td>
    </tr>
    <tr>
      <th>9</th>
      <td>54</td>
      <td>Norte De Santander</td>
      <td>40</td>
      <td>1565362</td>
      <td>21856.754453</td>
      <td>36.188063</td>
      <td>71.619142</td>
      <td>Grande</td>
    </tr>
  </tbody>
</table>
</div>




```python
(Municipios
 .groupby(["Region"])
 .agg(Superficie=("Superficie","sum")).reset_index()
 .sort_values(by=["Superficie"],ascending=False).reset_index(drop=True)
 .head(n=1)
)
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
      <th>Region</th>
      <th>Superficie</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Región Llano</td>
      <td>434000.024944</td>
    </tr>
  </tbody>
</table>
</div>




```python
e8 = (Municipios
      .query("Irural > 60")
      .groupby(["Dep","Departamento"])
      .agg(nmunicipios=("Depmun","count"),
           totpob=("Poblacion","sum"),
           totsup=("Superficie","sum")).reset_index()
      .sort_values(by=["totpob"],ascending=False)
      .eval('''denspob=totpob/totsup''')
     )

e8.info()
e8.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 17 entries, 6 to 8
    Data columns (total 6 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   Dep           17 non-null     int64  
     1   Departamento  17 non-null     object 
     2   nmunicipios   17 non-null     int64  
     3   totpob        17 non-null     int64  
     4   totsup        17 non-null     float64
     5   denspob       17 non-null     float64
    dtypes: float64(2), int64(3), object(1)
    memory usage: 952.0+ bytes
    




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
      <th>nmunicipios</th>
      <th>totpob</th>
      <th>totsup</th>
      <th>denspob</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6</th>
      <td>50</td>
      <td>Meta</td>
      <td>12</td>
      <td>207857</td>
      <td>74457.928754</td>
      <td>2.791603</td>
    </tr>
    <tr>
      <th>5</th>
      <td>27</td>
      <td>Chocó</td>
      <td>8</td>
      <td>153096</td>
      <td>26448.168537</td>
      <td>5.788529</td>
    </tr>
    <tr>
      <th>10</th>
      <td>85</td>
      <td>Casanare</td>
      <td>12</td>
      <td>146548</td>
      <td>37493.091910</td>
      <td>3.908667</td>
    </tr>
    <tr>
      <th>3</th>
      <td>18</td>
      <td>Caquetá</td>
      <td>6</td>
      <td>133736</td>
      <td>78392.489517</td>
      <td>1.705980</td>
    </tr>
    <tr>
      <th>16</th>
      <td>99</td>
      <td>Vichada</td>
      <td>4</td>
      <td>110599</td>
      <td>100063.370602</td>
      <td>1.105290</td>
    </tr>
    <tr>
      <th>14</th>
      <td>95</td>
      <td>Guaviare</td>
      <td>4</td>
      <td>84716</td>
      <td>55575.233166</td>
      <td>1.524348</td>
    </tr>
    <tr>
      <th>12</th>
      <td>91</td>
      <td>Amazonas</td>
      <td>11</td>
      <td>77753</td>
      <td>109497.053795</td>
      <td>0.710092</td>
    </tr>
    <tr>
      <th>11</th>
      <td>86</td>
      <td>Putumayo</td>
      <td>2</td>
      <td>65053</td>
      <td>15483.468374</td>
      <td>4.201449</td>
    </tr>
    <tr>
      <th>9</th>
      <td>81</td>
      <td>Arauca</td>
      <td>3</td>
      <td>55471</td>
      <td>12912.738238</td>
      <td>4.295836</td>
    </tr>
    <tr>
      <th>13</th>
      <td>94</td>
      <td>Guainía</td>
      <td>9</td>
      <td>49473</td>
      <td>71289.354481</td>
      <td>0.693975</td>
    </tr>
  </tbody>
</table>
</div>




```python
Repetidos = (Municipios
             .groupby("Municipio")
             .agg(reps=("Municipio","count")).reset_index()
             .query("reps > 1")
             .sort_values(by=["reps"],ascending=False).reset_index(drop=True) 
            )
reps = Repetidos["Municipio"]
Repetidos.info()
Repetidos.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 69 entries, 0 to 68
    Data columns (total 2 columns):
     #   Column     Non-Null Count  Dtype 
    ---  ------     --------------  ----- 
     0   Municipio  69 non-null     object
     1   reps       69 non-null     int64 
    dtypes: int64(1), object(1)
    memory usage: 1.2+ KB
    




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
      <th>reps</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Villanueva</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>La Unión</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Córdoba</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Sucre</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Santa Bárbara</td>
      <td>3</td>
    </tr>
    <tr>
      <th>5</th>
      <td>San Pedro</td>
      <td>3</td>
    </tr>
    <tr>
      <th>6</th>
      <td>San Francisco</td>
      <td>3</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Sabanalarga</td>
      <td>3</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Nariño</td>
      <td>3</td>
    </tr>
    <tr>
      <th>9</th>
      <td>La Victoria</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>


