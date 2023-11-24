
<h1 align="center">
<p align="center">  The Ultimate Pandas Guide: Simplifying Data Operations
   
<br>
    <br>
<!-- PROJECT LOGO -->

  <kbd>
  <a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=DDF4CBF9&background=1F25E6D0&center=true&vCenter=true&random=false&width=435&lines=A+Simple+Pandas+DataFrame+CheatSheet" alt="Typing SVG" /></a>
  </kbd>
  <p align='center'>
    <a href='https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations'>
        <img alt='total stars' title='Total stars on This Project' src='https://custom-icon-badges.herokuapp.com/badge/dynamic/json?logo=star&color=5&labelColor=488207&label=Stars&style=for-the-badge&query=%24.stars&url=https://api.github-star-counter.workers.dev/user/Data-Portofolio'/>
     <a href='https://github.com/astutir'>
        <img alt='Follow Me on GitHub' title='Follow Me on GitHub' src='https://custom-icon-badges.herokuapp.com/github/followers/astutir?style=for-the-badge&&label=GitHub&logo=Github&color=pink'/>
    <a href='https://www.linkedin.com/in/a-rahmawati' target='_blank'>
        <img src='https://img.shields.io/badge/linkedin%20-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white'/>
    <a href='mailto:astutirahmarubi@gmail.com' target='_blank'>
        <img src='https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white'/>
 </p>

 </h1>

Welcome to My repository! This comprehensive guide serves as your key to mastering the powerful Pandas library, simplifying data operations, and unleashing the full potential of your data analysis tasks.

**About This Guide:**

Pandas is a go-to library for data manipulation, analysis, and transformation. However, its rich set of functions can be intimidating for beginners. This guide is designed to make your journey with Pandas both accessible and enjoyable. It offers a hands-on approach, packed with practical tips, tricks, and real-world examples to help you become proficient in using Pandas for a wide range of tasks.

# Table of Contents

   
1. [Make DataFrame ](#Make-DataFrame)
2. [Read and Write Data](#Read-and-Write-Data)
3. [Info and Statistics](#Info-and-Statistics)
4. [Categorical Data Info](#Categorical-Data-Info)
5. [Data Selection](#Data-Selection)
6. [Data Manipulation](#Data-Manipulation)
7. [Aggregation and Grouping](#Aggregation-and-Grouping)
8. [Merging and Joining](#Merging-and-Joining)
9. [Data Filling and Replacement](#Data-Filling-and-Replacement)
10. [String Operations](#String-Operations)
11. [Datetime Operations](#Datetime-Operations)
12. [Data Type Conversion](#Data-Type-Conversion)
13. [Format Method](#Format-Method)
14. 


<a name="Make-DataFrame"></a>
# 1. Make DataFrame
- `pd.DataFrame()`: function in Pandas allows you to create a DataFrame by specifying the data and various parameters. 

```python
import pandas as pd

# Sample data
data = {'ProductID': [101, 102, 103, 104],
        'ProductName': ['Laptop', 'Tablet', 'Phone', 'Printer'],
        'Price': [999.99, 299.99, 499.99, 149.99]}

# Define the row index and column names
index_labels = ['A', 'B', 'C', 'D']
column_names = ['ProductID', 'ProductName', 'Price']

# Create the DataFrame
df = pd.DataFrame(data, index=index_labels, columns=column_names)

# Display the DataFrame
print(df)
```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/44e51992-b36b-4a8d-93af-6436d597301a)

<a name="Read-and-Write-Data"></a>
# 2. Read and Write Data:

- `pd.read_csv()`: Explore the world of data with ease! Read data from a CSV file and convert it into a DataFrame.
  
```python
import pandas as pd

# Contoh: Membaca file CSV dengan delimiter (pemisah) titik koma, membatasi kolom, dan menangani tanggal
file_path = 'path/to/your/another_file.csv'

# Membaca CSV dengan menggunakan titik koma sebagai delimiter, membatasi kolom, dan menangani tanggal
df = pd.read_csv(file_path, sep=';', skiprows=2, parse_dates=['Tanggal'], na_values='Not Available', usecols=['Tanggal', 'Column1', 'Column2'])

# Menampilkan lima baris pertama dari DataFrame
print(df.head())
```

#### **_Penjelasan:_**

>`sep=';'`: Menggunakan titik koma (`;`) sebagai delimiter dalam file CSV.
>`skiprows=2`: Mengabaikan dua baris pertama dalam file CSV.
>`parse_dates=['Tanggal']`: Mengonversi kolom 'Tanggal' menjadi tipe data datetime.
>`na_values='Not Available'`: Menggantikan nilai 'Not Available' dengan nilai NaN untuk menangani nilai yang hilang.
>`usecols=['Tanggal', 'Column1', 'Column2']`: Membatasi pembacaan hanya pada kolom-kolom yang disebutkan dalam daftar tersebut.

- **pd.read_excel()**: Bring the world of spreadsheets into your DataFrame with pd.read_excel().
- **df.to_csv()**: Save your analysis results back to a shareable CSV format.
- **df.to_excel()**: Showcase your hard work in a neatly formatted Excel file.
- **df.to_sql()**: Let Pandas assist you in saving your DataFrame to your SQL database.
  
<a name="Info-and-Statistics"></a>
# 3. Info and Statistics:

- **df.info()**: Hand over control to Pandas to provide a comprehensive summary of your DataFrame's structure.
- **df.head()**: Take a sneak peek at your initial data to gain a quick understanding.
- **df.tail()**: Scroll through the tail end of your data to inspect the outcomes.
- **df.describe()**: Display statistical prowess with pd.describe() and uncover all the details.
- **df.shape**: Observe your DataFrame's dimensions, how many rows and columns it has.
- **df.columns**: Create a list of column names in the blink of an eye.
- **df.dtypes**: Use dtypes to reveal the secrets of column data types.
- **df.isnull()**: Let Pandas unveil the places where your data is missing.

<a name="Categorical-Data-Info"></a>
# 4. Categorical Data Info:

### **`df.unique()`**
Metode ini digunakan untuk mendapatkan nilai unik dari suatu Series (kolom dalam DataFrame). Ini memberikan daftar nilai yang berbeda dari kolom tersebut.

```python
import pandas as pd

# Creating a larger DataFrame with multiple columns
data = {
    'Category': ['A', 'B', 'A', 'C', 'B', 'D', 'A', 'C'],
    'Count': [10, 5, 8, 12, 5, 7, 10, 15],
    'Status': ['Active', 'Inactive', 'Active', 'Active', 'Inactive', 'Active', 'Inactive', 'Active']
}
df = pd.DataFrame(data)

# Print the output of df.iteritems()
print("Output of df.iteritems():")
for column_name, column_values in df.iteritems():
    print(f"Column Name: {column_name}")
    print(column_values)
    print()

# Get unique values and their index for each column using enumerate
for column_name, column_values in df.iteritems():
    unique_values = column_values.unique()
    print(f"\nUnique values in '{column_name}' column:")
    
    for index, value in enumerate(unique_values):
        print(f"  Index {index}: {value}")
```

#### Output:

```
Output of df.iteritems():
Column Name: Category
0    A
1    B
2    A
3    C
4    B
5    D
6    A
7    C
Name: Category, dtype: object

Column Name: Count
0    10
1     5
2     8
3    12
4     5
5     7
6    10
7    15
Name: Count, dtype: int64

Column Name: Status
0       Active
1     Inactive
2       Active
3       Active
4     Inactive
5       Active
6     Inactive
7       Active
Name: Status, dtype: object


Unique values in 'Category' column:
  Index 0: A
  Index 1: B
  Index 2: C
  Index 3: D

Unique values in 'Count' column:
  Index 0: 10
  Index 1: 5
  Index 2: 8
  Index 3: 12
  Index 4: 7
  Index 5: 15

Unique values in 'Status' column:
  Index 0: Active
  Index 1: Inactive
```
<details> 
    <summary align="center">
       🥇 More Details about `df.iteritems()` & `enumerate`! 
    </summary>
   
### `df.iteritems()`

`df.iteritems()` adalah metode pada Pandas untuk mengiterasi melalui kolom-kolom dalam DataFrame. Metode ini memberikan pasangan (nama_kolom, Series) untuk setiap kolom, memungkinkan akses ke nilai-nilai dalam kolom tersebut.

Dalam contoh ini:

```python
for nama_kolom, nilai_kolom in df.iteritems():
    print(f"Nama Kolom: {nama_kolom}")
    print(f"Isi Kolom:")
    print(nilai_kolom)
    print()
```

Loop ini berjalan melalui setiap kolom DataFrame (`df`), mencetak nama kolom dan nilai kolom (sebagai objek Series). Dalam contoh ini, `nilai_kolom` berisi nilai-nilai kolom.

### `enumerate`

`enumerate` adalah fungsi Python yang memberikan indeks dan nilai saat mengiterasi melalui suatu iterable. Berguna untuk mendapatkan kedua informasi tersebut selama iterasi.

Dalam contoh ini:

```python
for indeks, nilai in enumerate(nilai_unik):
    print(f"  Indeks {indeks}: {nilai}")
```

Loop ini mengiterasi melalui nilai-nilai unik dari suatu kolom (dengan `unique()`), mencetak indeks dan nilai untuk setiap elemen. `nilai_unik` berisi nilai-nilai unik tersebut.

Secara keseluruhan, `df.iteritems()` digunakan untuk iterasi kolom-kolom, dan `enumerate` digunakan di dalam loop untuk mendapatkan indeks dan nilai dari setiap nilai unik dalam suatu kolom. Ini memberikan ringkasan lebih detail dari DataFrame, termasuk nilai unik dan indeks mereka untuk setiap kolom.

</details>

### **`df.nunique()`**
Metode ini mengembalikan jumlah nilai unik dalam suatu Series. Ini memberikan informasi tentang seberapa bervariasinya data dalam kolom.

#### Example:

Your code looks correct for calculating the number of unique values in the 'Category' column using the `nunique()` method. If you want to improve readability, you might consider formatting the output using an f-string. Here's your code with a slight improvement in formatting:

```python
import pandas as pd

# Assuming you have a DataFrame df with a 'Category' column
data = {'Category': ['A', 'B', 'A', 'C', 'B', 'D', 'A', 'C']}
df = pd.DataFrame(data)

# Calculate the number of unique values in 'Category' column
num_unique_values = df['Category'].nunique()

# Print the result with formatted output
print(f"Number of unique values in 'Category' column: {num_unique_values}")
```

Output:

```
Number of unique values in 'Category' column: 3
```
    
### **`df.value_counts()`**
Metode ini menghitung frekuensi masing-masing nilai dalam suatu Series. Ini memberikan wawasan tentang seberapa sering masing-masing nilai muncul dalam data.

#### Example:

```python
import pandas as pd

# Assuming you have a DataFrame df with a 'Category' column
data = {'Category': ['A', 'B', 'A', 'C', 'B', 'D', 'A', 'C']}
df = pd.DataFrame(data)

# Get value counts for each unique value in 'Category' column
value_counts = df['Category'].value_counts()

# Print formatted output for better readability
print("Value counts for each unique value in 'Category' column:")
for category, count in value_counts.items():
    print(f"{category}: {count}")
```

Output:

```
Value counts for each unique value in 'Category' column:
A: 3
B: 2
C: 2
D: 1
```
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Data-Selection"></a>
# 5. Data Selection:

- `df['column']`: Pick and extract the necessary column from the DataFrame.
- `df[['column1', 'column2']]`: Bundle your data by selecting multiple columns at once.

### Example
```python
import pandas as pd

# Create a DataFrame
data = {'Nama': ['Alice', 'Bob', 'Charlie', 'David'],
        'Usia': [25, 30, 35, 28],
        'Kota': ['Jakarta', 'Surabaya', 'Bandung', 'Medan'],
        'Pekerjaan': ['Guru', 'Dokter', 'Insinyur', 'Desainer']}

df = pd.DataFrame(data)

# Definisi fungsi untuk menentukan status
def determine_status(row):
    if row['Usia'] >= 30:
        return 'Dewasa'
    elif row['Usia'] < 30 and row['Pekerjaan'] != 'Dokter':
        return 'Muda'
    else:
        return 'Undefined'

# Menambahkan kolom baru berdasarkan fungsi
df['Status'] = df.apply(lambda row: determine_status(row), axis=1)

# Menampilkan data yang memenuhi kriteria tertentu
result_complex_filter = df[(df['Usia'] > 25) & (df['Pekerjaan'] == 'Dokter')]

# Menampilkan hasil
print("DataFrame Asli:")
print(df)
print("\nDataFrame setelah filter yang kompleks:")
print(result_complex_filter)
```

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/b1c999cf-6b51-4ec9-948b-5f174e2e0671)

- `df.loc[]`: Perform selection based on row and column labels.
- `df.iloc[]`: Execute selection based on row and column indices.

### Example 1:

```python
import pandas as pd

# Create a DataFrame
data = {'Nama': ['Alice', 'Bob', 'Charlie', 'David'],
        'Usia': [25, 30, 35, 28],
        'Kota': ['Jakarta', 'Surabaya', 'Bandung', 'Medan'],
        'Pekerjaan': ['Guru', 'Dokter', 'Insinyur', 'Dokter']}

df = pd.DataFrame(data)

# Seleksi kompleks dengan df.loc[]
result_loc = df.loc[(df['Usia'] > 25) & (df['Pekerjaan'] == 'Dokter'), ['Nama', 'Usia', 'Kota']]

# Seleksi kompleks dengan df.iloc[]
result_iloc = df.iloc[(df['Usia'] > 25).index & (df['Pekerjaan'] == 'Dokter').index, [0, 1, 2]]

# Menampilkan hasil
print("DataFrame Asli:")
print(df)
print("\nDataFrame hasil seleksi menggunakan df.loc[]:")
print(result_loc)
print("\nDataFrame hasil seleksi menggunakan df.iloc[]:")
print(result_iloc)
```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c32fcb4c-e25a-4aeb-bc80-acafad31c503)

---
### Example2:
```python
import pandas as pd

# Create a DataFrame
data = {'Nama': ['Alice', 'Bob', 'Charlie', 'David'],
        'Usia': [25, 30, 35, 28],
        'Kota': ['Jakarta', 'Surabaya', 'Bandung', 'Medan']}

df = pd.DataFrame(data)

# Menambahkan kolom baru berdasarkan kriteria
df['Status'] = df['Usia'].apply(lambda x: 'Dewasa' if x >= 30 else 'Muda')

# Menambahkan kolom dengan panjang karakter nama
df['Panjang_Nama'] = df['Nama'].apply(len)

# Menampilkan data yang memenuhi kriteria tertentu
result_filtered = df[df['Usia'] > 25]

# Menyimpan DataFrame ke file CSV
df.to_csv('dataframe_example.csv', index=False)

# Membaca DataFrame dari file CSV
df_from_csv = pd.read_csv('dataframe_example.csv')

# Menampilkan hasil
print("DataFrame Asli:")
print(df)
print("\nDataFrame setelah penambahan kolom dan filter:")
print(result_filtered)
print("\nDataFrame setelah ditulis ke CSV dan dibaca kembali:")
print(df_from_csv)
```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8b81da07-987a-4642-bcc3-6e4a3a818a96)
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Data-Manipulation"></a>
# 6. Data Manipulation:

- `df.drop()`: Easily remove unwanted columns or rows.
- `df.rename()`: Personalize your DataFrame by changing column or index names.
- `df.set_index()`: Give your DataFrame the index that suits you.
- `df.reset_index()`: Reset the index and reorganize your DataFrame to its original state.
- `df.sort_values()`: Use sort_values() to arrange data as you desire.
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Aggregation-and-Grouping"></a>
# 7. Aggregation and Grouping:

- **df.groupby()**: Create groups based on specific columns to perform aggregation operations.
- **df.agg()**: Let Pandas extract the information you need from grouped data.
- **df.pivot()**: Present your data in a beautiful pivot format.
- **df.melt()**: Transform data into a long format and discover the pattern.
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Merging and Joining)"></a>
# 8. Merging and Joining:

- **df.merge()**: Intuitively combine DataFrames with ease.
- **df.join()**: Merge with another DataFrame to intelligently combine information.
- **pd.concat()**: Powerfully combine multiple DataFrames into one.

Dalam Pandas, terdapat beberapa metode untuk menggabungkan atau menggabungkan dua DataFrames. Berikut adalah perbedaan antara tiga metode utama: `merge`, `concat`, dan `join`.

### 1. **`merge`:**
   - `merge` digunakan ketika kita ingin menggabungkan DataFrames berdasarkan nilai-nilai tertentu dalam kolom-kolom tertentu (seperti bergabung berdasarkan kolom kunci).
   - Secara default, `merge` menggunakan tipe gabungan "inner join" (gabungan dalam) di mana hanya nilai-nilai yang cocok di kedua DataFrames yang akan disertakan.
   - Contoh:

    ```python
    import pandas as pd

    df1 = pd.DataFrame({'key': ['A', 'B', 'C'], 'value': [1, 2, 3]})
    df2 = pd.DataFrame({'key': ['A', 'B', 'D'], 'value': [4, 5, 6]})

    merged_df = pd.merge(df1, df2, on='key', how='inner')
    print(merged_df)
    ```

    Outputnya:

    ```
      key  value_x  value_y
    0   A        1        4
    1   B        2        5
    ```

### 2. **`concat`:**
   - `concat` digunakan untuk menggabungkan DataFrames secara vertikal (menambahkan baris) atau secara horizontal (menambahkan kolom).
   - Secara default, `concat` melakukan penggabungan secara vertikal (axis=0).
   - Contoh:

    ```python
    import pandas as pd

    df1 = pd.DataFrame({'A': [1, 2], 'B': [3, 4]})
    df2 = pd.DataFrame({'A': [5, 6], 'B': [7, 8]})

    concatenated_df = pd.concat([df1, df2], axis=0)
    print(concatenated_df)
    ```

    Outputnya:

    ```
       A  B
    0  1  3
    1  2  4
    0  5  7
    1  6  8
    ```

### 3. **`join`:**
   - `join` digunakan untuk menggabungkan DataFrames berdasarkan indeks mereka.
   - Secara default, `join` menggunakan tipe gabungan "left join" (gabungan kiri), yang akan menggabungkan semua indeks dari DataFrame pertama dan nilai-nilai yang cocok dari DataFrame kedua.
   - Contoh:

    ```python
    import pandas as pd

    df1 = pd.DataFrame({'A': [1, 2], 'B': [3, 4]}, index=['X', 'Y'])
    df2 = pd.DataFrame({'C': [5, 6], 'D': [7, 8]}, index=['X', 'Z'])

    joined_df = df1.join(df2, how='left')
    print(joined_df)
    ```

    Outputnya:

    ```
       A  B    C    D
    X  1  3  5.0  7.0
    Y  2  4  NaN  NaN
    ```

#### **_Ringkasan_**:
`merge` digunakan untuk menggabungkan berdasarkan kolom, `concat` untuk menggabungkan secara vertikal atau horizontal, dan `join` untuk menggabungkan berdasarkan indeks. Pilihan metode tergantung pada kebutuhan spesifik analisis Anda.
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Data-Filling-and-Replacement"></a>
# 9. Data Filling and Replacement:
- `df.fillna()`: Fill missing values with policies you define.
- `df.replace(to_replace, value)`: Replace values with new ones as per your requirements.

<a name="String-Operations)"></a>
# 10. String Operations:

- **df['column'].`str.upper()`**: Elevate all letters to uppercase!
- **df['column'].`str.contains()`**: Unearth patterns in text with df['column'].str.contains().
- **df['column'].`str.title()`**: Capitalize the first letter of each word in the string.
- **df['column'].`str.capitalize()`**: Capitalize the first letter of the string.
- **df['column'].str.`swapcase()`**: Swap the case of each character (e.g., "aBc" becomes "AbC").
- **df['column'].str.`strip()`**: Remove leading and trailing whitespace.
- **df['column'].str.`lstrip()`**: Remove leading whitespace.
- **df['column'].str.`rstrip()`**: Remove trailing whitespace.
- **df['column'].str.`strip('char')`**: Remove specific characters from the start and end.
- **df['column'].str.`lstrip('char')`**: Remove specific characters from the start.
- **df['column'].str.`rstrip('char')`**: Remove specific characters from the end.
- **df['column'].str.`len()`**: Calculate the length (number of characters) of each string.
- **df['column'].str.`slice(start, stop)`**: Extract a substring based on the specified start and stop positions.
- **df['column'].str.`replace(old, new)`**: Replace a substring with a new value.
- **df['column'].str.`replace(r'pattern', new)`**: Replace substrings based on a regular expression pattern.
- **df['column'].str.`contains('substring')`**: Check if a string contains a specific substring and returns a boolean.
- **df['column'].str.`startswith('prefix')`**: Check if a string starts with a specific prefix and returns a boolean.
- **df['column'].str.`endswith('suffix')`**: Check if a string ends with a specific suffix and returns a boolean.
- **df['column'].str.`split('delimiter')`**: Split a string into a list of substrings based on a delimiter.
- **df['column'].str.`join('separator')`**: Join a list of strings with a specified separator.
- **df['column'].str.`cat(sep='separator')`**: Concatenate strings within a column, separated by a specified separator.
  
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Datetime-Operations"></a>
# 11. Datetime Operations:
- **df['column'].dt.`year`**: Peek at the year effortlessly from a datetime column.
- **df['column'].dt.`month`**: Dip your fingers to unearth the month from datetime data.
- **df['column'].dt.`day`**: Extracts the day component from the datetime column.
- **df['column'].dt.`hour`**: Extracts the hour component from the datetime column.
- **df['column'].dt.`minute`**: Extracts the minute component from the datetime column.
- **df['column'].dt.`second`**: Extracts the second component from the datetime column.
- **df['column'].dt.`microsecond`**: Extracts the microsecond component from the datetime column.
- **df['column'].dt.`date`**: Extracts the date component (without the time) from the datetime column.
- **df['column'].dt.`time`**: Extracts the time component (without the date) from the datetime column.
- **df['column'].dt.`dayofweek`**: Returns the day of the week as an integer, where Monday is 0 and Sunday is 6.
- **df['column'].dt.`day_name()`**: Returns the day of the week as a string (e.g., 'Monday', 'Tuesday').
- **df['column'].dt.`is_month_start`**: Returns a Boolean indicating if the date is the start of the month.
- **df['column'].dt.`is_month_end`**: Returns a Boolean indicating if the date is the end of the month.
- **df['column'].dt.`is_year_start`**: Returns a Boolean indicating if the date is the start of the year.
- **df['column'].dt.`is_year_end`**: Returns a Boolean indicating if the date is the end of the year.
- **df['column'].dt.`dayofyear`**: Returns the day of the year as an integer.
- **df['column'].dt.`week**: Returns the week number of the year.
- **df['column'].dt.`weekday`**: Returns the day of the week as an integer, where Monday is 0 and Sunday is 6.
- **df['column'].dt.`quarter`**: Returns the quarter of the year as an integer (1-4).
- **df['column'].dt.`to_period('M')`**: Converts the datetime to a period with a specified frequency (e.g., 'M' for monthly).
- **df['column'].dt.`to_period('D')`**: Converts the datetime to a period with a daily frequency.
- **df['column'].dt.`strftime('format_string')`**: Allows you to format the datetime as a string using a custom format.

### Example 1:

```python
import pandas as pd

# Sample DataFrame with datetime data
data = {
    'date_column': ['2023-01-01', '2023-02-15', '2023-03-20', '2023-04-10'],
    'value': [100, 150, 200, 250]
}
df = pd.DataFrame(data)

# Example 1: Date Parsing and Conversion
df['date_column'] = pd.to_datetime(df['date_column'])

# Example 2: Date Extraction
df['year'] = df['date_column'].dt.year
df['month'] = df['date_column'].dt.month
df['day'] = df['date_column'].dt.day

# Example 3: Resampling (Monthly Sum)
monthly_data = df.set_index('date_column').resample('M').sum()

# Example 4: Time Difference Calculation
df['days_since_event'] = (df['date_column'] - pd.to_datetime('2023-01-01')).dt.days

# Example 5: Date Range Generation
date_range = pd.date_range(start='2023-01-01', end='2023-12-31', freq='D')

# Example 6: Offset by 10 days
df['date_column_offset_10_days'] = df['date_column'] + pd.DateOffset(days=10)

# Example 7: Offset by 2 months
df['date_column_offset_2_months'] = df['date_column'] + pd.DateOffset(months=2)

```
### Example 2
```python
import pandas as pd

# Sample DataFrame with datetime data
data = {
    'date_column': ['2023-01-01', '2023-02-15', '2023-03-20', '2023-04-10'],
}
df = pd.DataFrame(data)
df['date_column'] = pd.to_datetime(df['date_column'])

# Extract the day of the week (0 = Monday, 6 = Sunday)
df['day_of_week'] = df['date_column'].dt.dayofweek

# Filter for weekdays (Monday to Friday, day_of_week 0 to 4)
weekdays_df = df[df['day_of_week'].isin([0, 1, 2, 3, 4])]

# Filter for weekends (Saturday and Sunday, day_of_week 5 and 6)
weekends_df = df[df['day_of_week'].isin([5, 6])]

# Print the results
print("Weekdays:")
print(weekdays_df)
print("\nWeekends:")
print(weekends_df)

```
#### output:
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/a499499c-33a0-4751-ae5c-ab85061a3cd5)

<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Data-Type-Conversion"></a>
# 12. Data Type Conversion

- `df['column_name'] = df['column_name'].astype('int64')`
- `df['date_column'] = pd.to_datetime(df['date_column'])`
  
### Example 1:
```python
import pandas as pd

# Create a DataFrame
data = {'Nama': ['Alice', 'Bob', 'Charlie', 'David'],
        'Usia': [25, 30, 35, 28],
        'Kota': ['Jakarta', 'Surabaya', 'Bandung', 'Medan'],
        'Pekerjaan': ['Guru', 'Dokter', 'Insinyur', 'Desainer'],
        'Gaji': [50000, 80000, 70000, 60000],
        'Tanggal_Absen': ['2022-01-01', '2022-02-15', '2022-03-20', '2022-04-10']}

df = pd.DataFrame(data)

# Convert the 'Tanggal_Absen' column to datetime
df['Tanggal_Absen'] = pd.to_datetime(df['Tanggal_Absen'])

# Extract day name and select rows with weekend dates
df['Hari'] = df['Tanggal_Absen'].dt.day_name()
weekend_df = df[df['Tanggal_Absen'].dt.dayofweek.isin([5, 6])]

# Select rows with weekday dates
weekday_df = df[df['Tanggal_Absen'].dt.dayofweek.isin([0, 1, 2, 3, 4])]

# Display the DataFrame with weekend and weekday dates
print("DataFrame with Weekend Dates:")
print(weekend_df[['Nama', 'Hari', 'Tanggal_Absen']])

print("\nDataFrame with Weekday Dates:")
print(weekday_df[['Nama', 'Hari', 'Tanggal_Absen']])
```

_Output:_
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/42f857f5-709a-43a1-9886-22abc1aa8d3b)

---
### Example 2:
```phyton
import pandas as pd

# Create a DataFrame with birthdates
data = {'Nama': ['Alice', 'Bob', 'Charlie', 'David'],
        'Tanggal_Lahir': ['1992-02-29', '1996-03-15', '1988-02-29', '1995-04-10']}

df = pd.DataFrame(data)

# Convert the 'Tanggal_Lahir' column to datetime
df['Tanggal_Lahir'] = pd.to_datetime(df['Tanggal_Lahir'])

# Extract year and check for leap year
df['Tahun_Kabisat'] = df['Tanggal_Lahir'].dt.year
df['Is_Kabisat'] = df['Tahun_Kabisat'].apply(lambda year: year % 4 == 0 and (year % 100 != 0 or year % 400 == 0))

# Select rows where the birthdate is on a leap year
leap_year_df = df[df['Is_Kabisat']]

# Display the DataFrame with leap year birthdays
print("DataFrame with Birthdays on Leap Years:")
print(leap_year_df[['Nama', 'Tanggal_Lahir', 'Tahun_Kabisat']])
```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/3302e1f5-a7f3-4099-a54b-5e79efe88e22)

- `df['category_column'] = df['category_column'].astype('category')`
- `df['numeric_column'] = pd.to_numeric(df['numeric_column'], errors='coerce')`
- `df['boolean_column'] = df['boolean_column'].astype(bool)`
- `df['string_column'] = df['string_column'].astype(str)`

<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Format-Method"></a>
# 13. Format Method

### Example 1:


```python
import pandas as pd

# Assuming you have a DataFrame df with a 'Category' column
data = {'Category': ['A', 'B', 'A', 'C', 'B', 'D', 'A', 'C']}
df = pd.DataFrame(data)

# Calculate the number of unique values in 'Category' column
num_unique_values = df['Category'].nunique()

# Additional variables
total_entries = len(df)
percentage_unique = (num_unique_values / total_entries) * 100

# Using f-string for formatting with additional variables and formatting options
print(f"""
Summary of 'Category' Column:
- Total entries: {total_entries}
- Number of unique values: {num_unique_values}
- Percentage of unique values: {percentage_unique:.2f}%
""")

# Using .format() method for formatting
print("""
Summary of 'Category' Column:
- Total entries: {}
- Number of unique values: {}
- Percentage of unique values: {:.2f}%
""".format(total_entries, num_unique_values, percentage_unique))

# Using % operator for formatting (old-style formatting)
print("""
Summary of 'Category' Column:
- Total entries: %d
- Number of unique values: %d
- Percentage of unique values: %.2f%%
""" % (total_entries, num_unique_values, percentage_unique))
```

#### Output:
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/d1020dde-4b36-4433-8f97-f16a4faf971e)


### Example 2:

Apologies for any confusion. It seems there was a mistake in the previous response. Here's the corrected output for the more complex example:

```python
import pandas as pd

# Assuming you have a DataFrame df with a 'Category' column
data = {'Category': ['A', 'B', 'A', 'C', 'B', 'D', 'A', 'C']}
df = pd.DataFrame(data)

# Calculate the number of unique values in 'Category' column
num_unique_values = df['Category'].nunique()

# Additional variables
total_entries = len(df)
percentage_unique = (num_unique_values / total_entries) * 100

# Using f-string for formatting with additional variables and formatting options
print(f"""
Summary of 'Category' Column:
- Total entries: {total_entries}
- Number of unique values: {num_unique_values}
- Percentage of unique values: {percentage_unique:.2f}%
""")

# Using .format() method for formatting
print("""
Summary of 'Category' Column:
- Total entries: {}
- Number of unique values: {}
- Percentage of unique values: {:.2f}%
""".format(total_entries, num_unique_values, percentage_unique))

# Using % operator for formatting (old-style formatting)
print("""
Summary of 'Category' Column:
- Total entries: %d
- Number of unique values: %d
- Percentage of unique values: %.2f%%
""" % (total_entries, num_unique_values, percentage_unique))
```

#### Output:
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/874c7013-22d2-4b00-8e44-f98a73d31d1a)

<p align="right">(<a href="#top">back to top</a>)</p>
<h3>
<p align="center">
    :copyright: 2023 | A-Rahmawati </p>
</h3>
