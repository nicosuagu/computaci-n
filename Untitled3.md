## Clase de 02/11/2022



```python

```

<center><strong><h1 style="color:red;"> Introducción a Python </h1></strong></center>
<center><strong><h2 style="color:black;"> Angelica Mendez Buitrago (amendezb@unal.edu.co) </h2></strong></center>
<center><strong><h3 style="color:blue;"> Universidad Nacional de Colombia </h3></strong></center>
<center><strong><h3 style="color:blue;"> Sede Bogotá </h3></strong></center>
<center><strong><h3 style="color:blue;"> Facultad de Ciencias </h3></strong></center>
<center><strong><h3 style="color:blue;"> Departamento de Estadística </h3></strong></center>

<h1><a style="color:red;" href="https://documentation.sas.com/doc/en/pgmsascdc/9.4_3.5/proc/n045uxf7ll2p5on1ly4at3vpd47e.htm&quot; target="_blank"><strong>1. proc export</strong></a></h1>

<h2 style="color:black;">Importación y exportación de datos</h2>
    

<h1><a style="color:red;">Ejercicio: sashelp.cars</a></h1>

* <p align="justify"> Para pronosticar el rendimiento, en millas por galón, de los vehículos cuando transitan por grandes autopistas se usa con frecuencia la siguiente fórmula:</p>
$$\frac{16850}{{\rm Horsepower}^{0.1278}{\rm Weight}^{0.7081}}$$
<p align="justify"> Cuales son los 5 vehículos en los que la fórmula anterior arroja las mayores sobreestimaciones relativas? Cuales son los 5 vehículos en los que la fórmula anterior arroja las mayores subestimaciones absolutas?</p>

* <p align="justify"> Cree un conjunto de datos solamente con información sobre fabricante, modelo, origen, peso, caballos de fuerza y rendimiento en grandes autopistas, que incluya solamente los vehículos fabricados por Hyundai de modelos Accent, Elantra o Sonata, y en el que exista una variable definida como "High" para los vehículos cuyo peso es mayor a 1.2 toneladas y "Low" para los demás.</p>

<h1><a style="color:red;"> 8. sql (Libreria duckdb) </a></h1>

<h2 style="color:black;">Consulta, transformación, y creación de conjuntos de datos</h2>
<img src="images.png" width="700" height="350">


```python
import os
os.getcwd() 
```




    'C:\\Users\\Estudiante'




```python
os.chdir("C:\\Nano\\Docencia\\Curso")
os.getcwd()
```

<h1><a style="color:red;"> Importación de datos </a></h1>




```python
import pandas as pd
import numpy as np
pd.options.display.float_format = '{:,.2f}'.format

help(pd.read_excel)
```

    Help on function read_excel in module pandas.io.excel._base:
    
    read_excel(io, sheet_name=0, header=0, names=None, index_col=None, usecols=None, squeeze=False, dtype=None, engine=None, converters=None, true_values=None, false_values=None, skiprows=None, nrows=None, na_values=None, keep_default_na=True, na_filter=True, verbose=False, parse_dates=False, date_parser=None, thousands=None, comment=None, skipfooter=0, convert_float=True, mangle_dupe_cols=True, storage_options: Union[Dict[str, Any], NoneType] = None)
        Read an Excel file into a pandas DataFrame.
        
        Supports `xls`, `xlsx`, `xlsm`, `xlsb`, `odf`, `ods` and `odt` file extensions
        read from a local filesystem or URL. Supports an option to read
        a single sheet or a list of sheets.
        
        Parameters
        ----------
        io : str, bytes, ExcelFile, xlrd.Book, path object, or file-like object
            Any valid string path is acceptable. The string could be a URL. Valid
            URL schemes include http, ftp, s3, and file. For file URLs, a host is
            expected. A local file could be: ``file://localhost/path/to/table.xlsx``.
        
            If you want to pass in a path object, pandas accepts any ``os.PathLike``.
        
            By file-like object, we refer to objects with a ``read()`` method,
            such as a file handle (e.g. via builtin ``open`` function)
            or ``StringIO``.
        sheet_name : str, int, list, or None, default 0
            Strings are used for sheet names. Integers are used in zero-indexed
            sheet positions. Lists of strings/integers are used to request
            multiple sheets. Specify None to get all sheets.
        
            Available cases:
        
            * Defaults to ``0``: 1st sheet as a `DataFrame`
            * ``1``: 2nd sheet as a `DataFrame`
            * ``"Sheet1"``: Load sheet with name "Sheet1"
            * ``[0, 1, "Sheet5"]``: Load first, second and sheet named "Sheet5"
              as a dict of `DataFrame`
            * None: All sheets.
        
        header : int, list of int, default 0
            Row (0-indexed) to use for the column labels of the parsed
            DataFrame. If a list of integers is passed those row positions will
            be combined into a ``MultiIndex``. Use None if there is no header.
        names : array-like, default None
            List of column names to use. If file contains no header row,
            then you should explicitly pass header=None.
        index_col : int, list of int, default None
            Column (0-indexed) to use as the row labels of the DataFrame.
            Pass None if there is no such column.  If a list is passed,
            those columns will be combined into a ``MultiIndex``.  If a
            subset of data is selected with ``usecols``, index_col
            is based on the subset.
        usecols : int, str, list-like, or callable default None
            * If None, then parse all columns.
            * If str, then indicates comma separated list of Excel column letters
              and column ranges (e.g. "A:E" or "A,C,E:F"). Ranges are inclusive of
              both sides.
            * If list of int, then indicates list of column numbers to be parsed.
            * If list of string, then indicates list of column names to be parsed.
        
              .. versionadded:: 0.24.0
        
            * If callable, then evaluate each column name against it and parse the
              column if the callable returns ``True``.
        
            Returns a subset of the columns according to behavior above.
        
              .. versionadded:: 0.24.0
        
        squeeze : bool, default False
            If the parsed data only contains one column then return a Series.
        dtype : Type name or dict of column -> type, default None
            Data type for data or columns. E.g. {'a': np.float64, 'b': np.int32}
            Use `object` to preserve data as stored in Excel and not interpret dtype.
            If converters are specified, they will be applied INSTEAD
            of dtype conversion.
        engine : str, default None
            If io is not a buffer or path, this must be set to identify io.
            Supported engines: "xlrd", "openpyxl", "odf", "pyxlsb".
            Engine compatibility :
        
            - "xlrd" supports old-style Excel files (.xls).
            - "openpyxl" supports newer Excel file formats.
            - "odf" supports OpenDocument file formats (.odf, .ods, .odt).
            - "pyxlsb" supports Binary Excel files.
        
            .. versionchanged:: 1.2.0
                The engine `xlrd <https://xlrd.readthedocs.io/en/latest/>`_
                now only supports old-style ``.xls`` files.
                When ``engine=None``, the following logic will be
                used to determine the engine:
        
               - If ``path_or_buffer`` is an OpenDocument format (.odf, .ods, .odt),
                 then `odf <https://pypi.org/project/odfpy/>`_ will be used.
               - Otherwise if ``path_or_buffer`` is an xls format,
                 ``xlrd`` will be used.
               - Otherwise if `openpyxl <https://pypi.org/project/openpyxl/>`_ is installed,
                 then ``openpyxl`` will be used.
               - Otherwise if ``xlrd >= 2.0`` is installed, a ``ValueError`` will be raised.
               - Otherwise ``xlrd`` will be used and a ``FutureWarning`` will be raised. This
                 case will raise a ``ValueError`` in a future version of pandas.
        
        converters : dict, default None
            Dict of functions for converting values in certain columns. Keys can
            either be integers or column labels, values are functions that take one
            input argument, the Excel cell content, and return the transformed
            content.
        true_values : list, default None
            Values to consider as True.
        false_values : list, default None
            Values to consider as False.
        skiprows : list-like, int, or callable, optional
            Line numbers to skip (0-indexed) or number of lines to skip (int) at the
            start of the file. If callable, the callable function will be evaluated
            against the row indices, returning True if the row should be skipped and
            False otherwise. An example of a valid callable argument would be ``lambda
            x: x in [0, 2]``.
        nrows : int, default None
            Number of rows to parse.
        na_values : scalar, str, list-like, or dict, default None
            Additional strings to recognize as NA/NaN. If dict passed, specific
            per-column NA values. By default the following values are interpreted
            as NaN: '', '#N/A', '#N/A N/A', '#NA', '-1.#IND', '-1.#QNAN', '-NaN', '-nan',
            '1.#IND', '1.#QNAN', '<NA>', 'N/A', 'NA', 'NULL', 'NaN', 'n/a',
            'nan', 'null'.
        keep_default_na : bool, default True
            Whether or not to include the default NaN values when parsing the data.
            Depending on whether `na_values` is passed in, the behavior is as follows:
        
            * If `keep_default_na` is True, and `na_values` are specified, `na_values`
              is appended to the default NaN values used for parsing.
            * If `keep_default_na` is True, and `na_values` are not specified, only
              the default NaN values are used for parsing.
            * If `keep_default_na` is False, and `na_values` are specified, only
              the NaN values specified `na_values` are used for parsing.
            * If `keep_default_na` is False, and `na_values` are not specified, no
              strings will be parsed as NaN.
        
            Note that if `na_filter` is passed in as False, the `keep_default_na` and
            `na_values` parameters will be ignored.
        na_filter : bool, default True
            Detect missing value markers (empty strings and the value of na_values). In
            data without any NAs, passing na_filter=False can improve the performance
            of reading a large file.
        verbose : bool, default False
            Indicate number of NA values placed in non-numeric columns.
        parse_dates : bool, list-like, or dict, default False
            The behavior is as follows:
        
            * bool. If True -> try parsing the index.
            * list of int or names. e.g. If [1, 2, 3] -> try parsing columns 1, 2, 3
              each as a separate date column.
            * list of lists. e.g.  If [[1, 3]] -> combine columns 1 and 3 and parse as
              a single date column.
            * dict, e.g. {'foo' : [1, 3]} -> parse columns 1, 3 as date and call
              result 'foo'
        
            If a column or index contains an unparseable date, the entire column or
            index will be returned unaltered as an object data type. If you don`t want to
            parse some cells as date just change their type in Excel to "Text".
            For non-standard datetime parsing, use ``pd.to_datetime`` after ``pd.read_excel``.
        
            Note: A fast-path exists for iso8601-formatted dates.
        date_parser : function, optional
            Function to use for converting a sequence of string columns to an array of
            datetime instances. The default uses ``dateutil.parser.parser`` to do the
            conversion. Pandas will try to call `date_parser` in three different ways,
            advancing to the next if an exception occurs: 1) Pass one or more arrays
            (as defined by `parse_dates`) as arguments; 2) concatenate (row-wise) the
            string values from the columns defined by `parse_dates` into a single array
            and pass that; and 3) call `date_parser` once for each row using one or
            more strings (corresponding to the columns defined by `parse_dates`) as
            arguments.
        thousands : str, default None
            Thousands separator for parsing string columns to numeric.  Note that
            this parameter is only necessary for columns stored as TEXT in Excel,
            any numeric columns will automatically be parsed, regardless of display
            format.
        comment : str, default None
            Comments out remainder of line. Pass a character or characters to this
            argument to indicate comments in the input file. Any data between the
            comment string and the end of the current line is ignored.
        skipfooter : int, default 0
            Rows at the end to skip (0-indexed).
        convert_float : bool, default True
            Convert integral floats to int (i.e., 1.0 --> 1). If False, all numeric
            data will be read in as floats: Excel stores all numbers as floats
            internally.
        mangle_dupe_cols : bool, default True
            Duplicate columns will be specified as 'X', 'X.1', ...'X.N', rather than
            'X'...'X'. Passing in False will cause data to be overwritten if there
            are duplicate names in the columns.
        storage_options : dict, optional
            Extra options that make sense for a particular storage connection, e.g.
            host, port, username, password, etc., if using a URL that will
            be parsed by ``fsspec``, e.g., starting "s3://", "gcs://". An error
            will be raised if providing this argument with a local path or
            a file-like buffer. See the fsspec and backend storage implementation
            docs for the set of allowed keys and values.
        
            .. versionadded:: 1.2.0
        
        Returns
        -------
        DataFrame or dict of DataFrames
            DataFrame from the passed in Excel file. See notes in sheet_name
            argument for more information on when a dict of DataFrames is returned.
        
        See Also
        --------
        DataFrame.to_excel : Write DataFrame to an Excel file.
        DataFrame.to_csv : Write DataFrame to a comma-separated values (csv) file.
        read_csv : Read a comma-separated values (csv) file into DataFrame.
        read_fwf : Read a table of fixed-width formatted lines into DataFrame.
        
        Examples
        --------
        The file can be read using the file name as string or an open file object:
        
        >>> pd.read_excel('tmp.xlsx', index_col=0)  # doctest: +SKIP
               Name  Value
        0   string1      1
        1   string2      2
        2  #Comment      3
        
        >>> pd.read_excel(open('tmp.xlsx', 'rb'),
        ...               sheet_name='Sheet3')  # doctest: +SKIP
           Unnamed: 0      Name  Value
        0           0   string1      1
        1           1   string2      2
        2           2  #Comment      3
        
        Index and header can be specified via the `index_col` and `header` arguments
        
        >>> pd.read_excel('tmp.xlsx', index_col=None, header=None)  # doctest: +SKIP
             0         1      2
        0  NaN      Name  Value
        1  0.0   string1      1
        2  1.0   string2      2
        3  2.0  #Comment      3
        
        Column types are inferred but can be explicitly specified
        
        >>> pd.read_excel('tmp.xlsx', index_col=0,
        ...               dtype={'Name': str, 'Value': float})  # doctest: +SKIP
               Name  Value
        0   string1    1.0
        1   string2    2.0
        2  #Comment    3.0
        
        True, False, and NA values, and thousands separators have defaults,
        but can be explicitly specified, too. Supply the values you would like
        as strings or lists of strings!
        
        >>> pd.read_excel('tmp.xlsx', index_col=0,
        ...               na_values=['string1', 'string2'])  # doctest: +SKIP
               Name  Value
        0       NaN      1
        1       NaN      2
        2  #Comment      3
        
        Comment lines in the excel input file can be skipped using the `comment` kwarg
        
        >>> pd.read_excel('tmp.xlsx', index_col=0, comment='#')  # doctest: +SKIP
              Name  Value
        0  string1    1.0
        1  string2    2.0
        2     None    NaN
    
    

## Ejemplo 1


```python
plantulas1 = pd.read_excel("sample.xlsx",sheet_name=12,header=0)
plantulas1.info()
plantulas1.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 55 entries, 0 to 54
    Data columns (total 5 columns):
     #   Column    Non-Null Count  Dtype
    ---  ------    --------------  -----
     0   Parcela   55 non-null     int64
     1   NI        55 non-null     int64
     2   Plantula  55 non-null     int64
     3   Ni        55 non-null     int64
     4   Altura    55 non-null     int64
    dtypes: int64(5)
    memory usage: 2.3 KB
    




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
      <th>Parcela</th>
      <th>NI</th>
      <th>Plantula</th>
      <th>Ni</th>
      <th>Altura</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>50</td>
      <td>1</td>
      <td>52</td>
      <td>12</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>50</td>
      <td>2</td>
      <td>52</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>50</td>
      <td>3</td>
      <td>52</td>
      <td>12</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>50</td>
      <td>4</td>
      <td>52</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3</td>
      <td>50</td>
      <td>5</td>
      <td>52</td>
      <td>13</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>50</td>
      <td>6</td>
      <td>56</td>
      <td>10</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>50</td>
      <td>7</td>
      <td>56</td>
      <td>9</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6</td>
      <td>50</td>
      <td>8</td>
      <td>56</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>6</td>
      <td>50</td>
      <td>9</td>
      <td>56</td>
      <td>9</td>
    </tr>
    <tr>
      <th>9</th>
      <td>6</td>
      <td>50</td>
      <td>10</td>
      <td>56</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>



## Ejemplo 2


```python
plantulas2 = pd.read_excel("sample.xlsx",sheet_name="Plantulas",header=0)
plantulas2.info()
plantulas2.tail(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 55 entries, 0 to 54
    Data columns (total 5 columns):
     #   Column    Non-Null Count  Dtype
    ---  ------    --------------  -----
     0   Parcela   55 non-null     int64
     1   NI        55 non-null     int64
     2   Plantula  55 non-null     int64
     3   Ni        55 non-null     int64
     4   Altura    55 non-null     int64
    dtypes: int64(5)
    memory usage: 2.3 KB
    




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
      <th>Parcela</th>
      <th>NI</th>
      <th>Plantula</th>
      <th>Ni</th>
      <th>Altura</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>45</th>
      <td>33</td>
      <td>50</td>
      <td>46</td>
      <td>60</td>
      <td>8</td>
    </tr>
    <tr>
      <th>46</th>
      <td>33</td>
      <td>50</td>
      <td>47</td>
      <td>60</td>
      <td>9</td>
    </tr>
    <tr>
      <th>47</th>
      <td>33</td>
      <td>50</td>
      <td>48</td>
      <td>60</td>
      <td>9</td>
    </tr>
    <tr>
      <th>48</th>
      <td>33</td>
      <td>50</td>
      <td>49</td>
      <td>60</td>
      <td>10</td>
    </tr>
    <tr>
      <th>49</th>
      <td>50</td>
      <td>50</td>
      <td>50</td>
      <td>45</td>
      <td>12</td>
    </tr>
    <tr>
      <th>50</th>
      <td>50</td>
      <td>50</td>
      <td>51</td>
      <td>45</td>
      <td>11</td>
    </tr>
    <tr>
      <th>51</th>
      <td>50</td>
      <td>50</td>
      <td>52</td>
      <td>45</td>
      <td>12</td>
    </tr>
    <tr>
      <th>52</th>
      <td>50</td>
      <td>50</td>
      <td>53</td>
      <td>45</td>
      <td>13</td>
    </tr>
    <tr>
      <th>53</th>
      <td>50</td>
      <td>50</td>
      <td>54</td>
      <td>45</td>
      <td>12</td>
    </tr>
    <tr>
      <th>54</th>
      <td>50</td>
      <td>50</td>
      <td>55</td>
      <td>45</td>
      <td>12</td>
    </tr>
  </tbody>
</table>
</div>



## Ejemplo 3



```python
plantulas3 = pd.read_excel("sample.xlsx",sheet_name="Plantulas",usecols="A:C,E",header=0)
plantulas3.info()
plantulas3.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 55 entries, 0 to 54
    Data columns (total 4 columns):
     #   Column    Non-Null Count  Dtype
    ---  ------    --------------  -----
     0   Parcela   55 non-null     int64
     1   NI        55 non-null     int64
     2   Plantula  55 non-null     int64
     3   Altura    55 non-null     int64
    dtypes: int64(4)
    memory usage: 1.8 KB
    




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
      <th>Parcela</th>
      <th>NI</th>
      <th>Plantula</th>
      <th>Altura</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>50</td>
      <td>1</td>
      <td>12</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>50</td>
      <td>2</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>50</td>
      <td>3</td>
      <td>12</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>50</td>
      <td>4</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3</td>
      <td>50</td>
      <td>5</td>
      <td>13</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>50</td>
      <td>6</td>
      <td>10</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>50</td>
      <td>7</td>
      <td>9</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6</td>
      <td>50</td>
      <td>8</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>6</td>
      <td>50</td>
      <td>9</td>
      <td>9</td>
    </tr>
    <tr>
      <th>9</th>
      <td>6</td>
      <td>50</td>
      <td>10</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
## Ejemplo 4
```


```python
plantulas3 = pd.read_excel("sample.xlsx",sheet_name="Plantulas",usecols="A:C,E",header=0)
plantulas3.info()
plantulas3.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 55 entries, 0 to 54
    Data columns (total 4 columns):
     #   Column    Non-Null Count  Dtype
    ---  ------    --------------  -----
     0   Parcela   55 non-null     int64
     1   NI        55 non-null     int64
     2   Plantula  55 non-null     int64
     3   Altura    55 non-null     int64
    dtypes: int64(4)
    memory usage: 1.8 KB
    




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
      <th>Parcela</th>
      <th>NI</th>
      <th>Plantula</th>
      <th>Altura</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>50</td>
      <td>1</td>
      <td>12</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>50</td>
      <td>2</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>50</td>
      <td>3</td>
      <td>12</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>50</td>
      <td>4</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3</td>
      <td>50</td>
      <td>5</td>
      <td>13</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>50</td>
      <td>6</td>
      <td>10</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>50</td>
      <td>7</td>
      <td>9</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6</td>
      <td>50</td>
      <td>8</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>6</td>
      <td>50</td>
      <td>9</td>
      <td>9</td>
    </tr>
    <tr>
      <th>9</th>
      <td>6</td>
      <td>50</td>
      <td>10</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>



## Ejemplo 4


```python
plantulas4 = pd.read_excel("sample.xlsx",sheet_name="Plantulas",nrows=35,header=0)
plantulas4.info()
plantulas4.head(10)
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 35 entries, 0 to 34
    Data columns (total 5 columns):
     #   Column    Non-Null Count  Dtype
    ---  ------    --------------  -----
     0   Parcela   35 non-null     int64
     1   NI        35 non-null     int64
     2   Plantula  35 non-null     int64
     3   Ni        35 non-null     int64
     4   Altura    35 non-null     int64
    dtypes: int64(5)
    memory usage: 1.5 KB
    




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
      <th>Parcela</th>
      <th>NI</th>
      <th>Plantula</th>
      <th>Ni</th>
      <th>Altura</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>50</td>
      <td>1</td>
      <td>52</td>
      <td>12</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>50</td>
      <td>2</td>
      <td>52</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>50</td>
      <td>3</td>
      <td>52</td>
      <td>12</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>50</td>
      <td>4</td>
      <td>52</td>
      <td>10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3</td>
      <td>50</td>
      <td>5</td>
      <td>52</td>
      <td>13</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>50</td>
      <td>6</td>
      <td>56</td>
      <td>10</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>50</td>
      <td>7</td>
      <td>56</td>
      <td>9</td>
    </tr>
    <tr>
      <th>7</th>
      <td>6</td>
      <td>50</td>
      <td>8</td>
      <td>56</td>
      <td>7</td>
    </tr>
    <tr>
      <th>8</th>
      <td>6</td>
      <td>50</td>
      <td>9</td>
      <td>56</td>
      <td>9</td>
    </tr>
    <tr>
      <th>9</th>
      <td>6</td>
      <td>50</td>
      <td>10</td>
      <td>56</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>



# Ejemplo 6


#### hola

###### Hola


```python

```
