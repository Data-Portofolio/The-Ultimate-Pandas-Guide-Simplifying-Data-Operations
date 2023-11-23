
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

# Make DataFrame
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


**Read and Write Data:**
=========================

- **pd.read_csv()**: Explore the world of data with ease! Read data from a CSV file and convert it into a DataFrame.
```
import pandas as pd

# Contoh: Membaca file CSV dengan delimiter (pemisah) titik koma, membatasi kolom, dan menangani tanggal
file_path = 'path/to/your/another_file.csv'

# Membaca CSV dengan menggunakan titik koma sebagai delimiter, membatasi kolom, dan menangani tanggal
df = pd.read_csv(file_path, sep=';', skiprows=2, parse_dates=['Tanggal'], na_values='Not Available', usecols=['Tanggal', 'Column1', 'Column2'])

# Menampilkan lima baris pertama dari DataFrame
print(df.head())
```

**_Penjelasan:_**

`sep=';'`: Menggunakan titik koma (`;`) sebagai delimiter dalam file CSV.
`skiprows=2`: Mengabaikan dua baris pertama dalam file CSV.
`parse_dates=['Tanggal']`: Mengonversi kolom 'Tanggal' menjadi tipe data datetime.
`na_values='Not Available'`: Menggantikan nilai 'Not Available' dengan nilai NaN untuk menangani nilai yang hilang.
`usecols=['Tanggal', 'Column1', 'Column2']`: Membatasi pembacaan hanya pada kolom-kolom yang disebutkan dalam daftar tersebut.

- **pd.read_excel()**: Bring the world of spreadsheets into your DataFrame with pd.read_excel().
- **df.to_csv()**: Save your analysis results back to a shareable CSV format.
- **df.to_excel()**: Showcase your hard work in a neatly formatted Excel file.
- **df.to_sql()**: Let Pandas assist you in saving your DataFrame to your SQL database.

**Info and Statistics:**
=========================

6. **df.info()**: Hand over control to Pandas to provide a comprehensive summary of your DataFrame's structure.
7. **df.head()**: Take a sneak peek at your initial data to gain a quick understanding.
8. **df.tail()**: Scroll through the tail end of your data to inspect the outcomes.
9. **df.describe()**: Display statistical prowess with pd.describe() and uncover all the details.
10. **df.shape**: Observe your DataFrame's dimensions, how many rows and columns it has.
11. **df.columns**: Create a list of column names in the blink of an eye.
12. **df.dtypes**: Use dtypes to reveal the secrets of column data types.
13. **df.isnull()**: Let Pandas unveil the places where your data is missing.

**Categorical Data Info:**
=========================

14. **`df.unique()`**: Metode ini digunakan untuk mendapatkan nilai unik dari suatu Series (kolom dalam DataFrame). Ini memberikan daftar nilai yang berbeda dari kolom tersebut.

    Contoh:

    ```python
    unique_values = df['Category'].unique()
    print("Unique values in 'Category' column:", unique_values)
    ```

    Outputnya:

    ```
    Unique values in 'Category' column: ['A' 'B' 'C']
    ```

15. **`df.nunique()`**: Metode ini mengembalikan jumlah nilai unik dalam suatu Series. Ini memberikan informasi tentang seberapa bervariasinya data dalam kolom.

    Contoh:

    ```python
    num_unique_values = df['Category'].nunique()
    print("Number of unique values in 'Category' column:", num_unique_values)
    ```

    Outputnya:

    ```
    Number of unique values in 'Category' column: 3
    ```

16. **`df.value_counts()`**: Metode ini menghitung frekuensi masing-masing nilai dalam suatu Series. Ini memberikan wawasan tentang seberapa sering masing-masing nilai muncul dalam data.

    Contoh:

    ```python
    value_counts = df['Category'].value_counts()
    print("Value counts for each unique value in 'Category' column:")
    print(value_counts)
    ```

    Outputnya:

    ```
    Value counts for each unique value in 'Category' column:
    A    3
    B    2
    C    1
    Name: Category, dtype: int64
    ```

**Data Selection:**
=========================
17. **df['column']**: Pick and extract the necessary column from the DataFrame.
18. **df[['column1', 'column2']]**: Bundle your data by selecting multiple columns at once.
   ```
   import pandas as pd

# Create a DataFrame
data = {'Nama': ['Alice', 'Bob', 'Charlie', 'David'],
        'Usia': [25, 30, 35, 28],
        'Kota': ['Jakarta', 'Surabaya', 'Bandung', 'Medan']}

df = pd.DataFrame(data)

# Display specific columns using .head()
result = df[['Nama', 'Usia']].head()

# Print the result
print(result)
   ```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/11c7a992-8eeb-4f98-9eee-16016bf344fb)

19. **df.loc[]**: Perform selection based on row and column labels.
20. **df.iloc[]**: Execute selection based on row and column indices.

**Data Manipulation:**
=========================
21. **df.drop()**: Easily remove unwanted columns or rows.
22. **df.rename()**: Personalize your DataFrame by changing column or index names.
23. **df.set_index()**: Give your DataFrame the index that suits you.
24. **df.reset_index()**: Reset the index and reorganize your DataFrame to its original state.
25. **df.sort_values()**: Use sort_values() to arrange data as you desire.

**Aggregation and Grouping:**
=========================
26. **df.groupby()**: Create groups based on specific columns to perform aggregation operations.
27. **df.agg()**: Let Pandas extract the information you need from grouped data.
28. **df.pivot()**: Present your data in a beautiful pivot format.
29. **df.melt()**: Transform data into a long format and discover the pattern.

**Merging and Joining:**
=========================
30. **df.merge()**: Intuitively combine DataFrames with ease.
31. **df.join()**: Merge with another DataFrame to intelligently combine information.
32. **pd.concat()**: Powerfully combine multiple DataFrames into one.

Dalam Pandas, terdapat beberapa metode untuk menggabungkan atau menggabungkan dua DataFrames. Berikut adalah perbedaan antara tiga metode utama: `merge`, `concat`, dan `join`.

A. **`merge`:**
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

B. **`concat`:**
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

C. **`join`:**
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

**_Ringkasan_**: `merge` digunakan untuk menggabungkan berdasarkan kolom, `concat` untuk menggabungkan secara vertikal atau horizontal, dan `join` untuk menggabungkan berdasarkan indeks. Pilihan metode tergantung pada kebutuhan spesifik analisis Anda.

**Data Filling and Replacement:**
=========================
33. **df.fillna()**: Fill missing values with policies you define.
34. **df.replace(to_replace, value)**: Replace values with new ones as per your requirements.

**String Operations (on string-type columns):**
=========================
35. **df['column'].str.upper()**: Elevate all letters to uppercase!
36. **df['column'].str.contains()**: Unearth patterns in text with df['column'].str.contains().
37. **df['column'].str.title()**: Capitalize the first letter of each word in the string.
38. **df['column'].str.capitalize()**: Capitalize the first letter of the string.
39. **df['column'].str.swapcase()**: Swap the case of each character (e.g., "aBc" becomes "AbC").
40. **df['column'].str.strip()**: Remove leading and trailing whitespace.
41. **df['column'].str.lstrip()**: Remove leading whitespace.
42. **df['column'].str.rstrip()**: Remove trailing whitespace.
43. **df['column'].str.strip('char')**: Remove specific characters from the start and end.
44. **df['column'].str.lstrip('char')**: Remove specific characters from the start.
45. **df['column'].str.rstrip('char')**: Remove specific characters from the end.
46. **df['column'].str.len()**: Calculate the length (number of characters) of each string.
47. **df['column'].str.slice(start, stop)**: Extract a substring based on the specified start and stop positions.
48. **df['column'].str.replace(old, new)**: Replace a substring with a new value.
49. **df['column'].str.replace(r'pattern', new)**: Replace substrings based on a regular expression pattern.
50. **df['column'].str.contains('substring')**: Check if a string contains a specific substring and returns a boolean.
51. **df['column'].str.startswith('prefix')**: Check if a string starts with a specific prefix and returns a boolean.
52. **df['column'].str.endswith('suffix')**: Check if a string ends with a specific suffix and returns a boolean.
53. **df['column'].str.split('delimiter')**: Split a string into a list of substrings based on a delimiter.
54. **df['column'].str.join('separator')**: Join a list of strings with a specified separator.
55. **df['column'].str.cat(sep='separator')**: Concatenate strings within a column, separated by a specified separator.

**Datetime Operations (on datetime-type columns):**
=========================
- **df['column'].dt.year**: Peek at the year effortlessly from a datetime column.
- **df['column'].dt.month**: Dip your fingers to unearth the month from datetime data.
- **df['column'].dt.day**: Extracts the day component from the datetime column.
- **df['column'].dt.hour**: Extracts the hour component from the datetime column.
- **df['column'].dt.minute**: Extracts the minute component from the datetime column.
- **df['column'].dt.second**: Extracts the second component from the datetime column.
- **df['column'].dt.microsecond**: Extracts the microsecond component from the datetime column.
- **df['column'].dt.date**: Extracts the date component (without the time) from the datetime column.
- **df['column'].dt.time**: Extracts the time component (without the date) from the datetime column.
- **df['column'].dt.dayofweek**: Returns the day of the week as an integer, where Monday is 0 and Sunday is 6.
- **df['column'].dt.day_name()**: Returns the day of the week as a string (e.g., 'Monday', 'Tuesday').
- **df['column'].dt.is_month_start**: Returns a Boolean indicating if the date is the start of the month.
- **df['column'].dt.is_month_end**: Returns a Boolean indicating if the date is the end of the month.
- **df['column'].dt.is_year_start**: Returns a Boolean indicating if the date is the start of the year.
- **df['column'].dt.is_year_end**: Returns a Boolean indicating if the date is the end of the year.
- **df['column'].dt.dayofyear**: Returns the day of the year as an integer.
- **df['column'].dt.week**: Returns the week number of the year.
- **df['column'].dt.weekday**: Returns the day of the week as an integer, where Monday is 0 and Sunday is 6.
- **df['column'].dt.quarter**: Returns the quarter of the year as an integer (1-4).
- **df['column'].dt.to_period('M')**: Converts the datetime to a period with a specified frequency (e.g., 'M' for monthly).
- **df['column'].dt.to_period('D')**: Converts the datetime to a period with a daily frequency.
- **df['column'].dt.strftime('format_string')**: Allows you to format the datetime as a string using a custom format.

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


**Converting Column Data Types in Pandas**
===========================
- `df['column_name'] = df['column_name'].astype('int64')`
- `df['date_column'] = pd.to_datetime(df['date_column'])`
- `df['category_column'] = df['category_column'].astype('category')`
- `df['numeric_column'] = pd.to_numeric(df['numeric_column'], errors='coerce')`
- `df['boolean_column'] = df['boolean_column'].astype(bool)`
- `df['string_column'] = df['string_column'].astype(str)`
