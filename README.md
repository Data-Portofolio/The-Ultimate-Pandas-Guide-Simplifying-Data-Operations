
<h1 align="center">
<p align="center">  The Ultimate Pandas Guide:Simplifying Data Operations
   
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

Welcome to My repository! This comprehensive guide serves as your key to mastering the powerful 🐼 `Pandas library`, simplifying `data operations` 🖥️, and unleashing the full potential of your 📊 `data analysis tasks`.

**✨ About This Guide:**

Pandas 🐼 is a go-to library for data manipulation, analysis, and transformation🚀. However, its rich set of functions can be intimidating for beginners. This guide is designed to make your journey with Pandas both accessible and enjoyable🥂. It offers a hands-on approach, packed with practical tips, tricks, and real-world examples to help you become proficient in using Pandas for 🎯 a wide range of tasks.

# 📚 Table of Contents

   
1. [Make DataFrame ](#Make-DataFrame)
2. [Read and Write Data](#Read-and-Write-Data)
3. [Info and Statistics](#Info-and-Statistics)
4. [Categorical Data Info](#Categorical-Data-Info)
5. [Data Selection](#Data-Selection)
<details>
   <summary>📌 More...</summary>
<br>
   
6. [Data Manipulation](#Data-Manipulation)
7. [Aggregation and Grouping](#Aggregation-and-Grouping)
8. [Merging and Joining](#Merging-and-Joining)
9. [Data Filling and Replacement](#Data-Filling-and-Replacement)
10. [String Operations](#String-Operations)
11. [Datetime Operations](#Datetime-Operations)
12. [Data Type Conversion](#Data-Type-Conversion)
13. [Format Method](#Format-Method)
14. [Apply & Lambda](#Apply-&-Lambda)
</details>

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

<details><summary>pd.set_option()</summary>
   <br>
Anda telah memberikan contoh kode yang baik untuk menambahkan opsi pengaturan lainnya menggunakan `pd.set_option()` dalam pandas. Dengan menambahkan opsi-opsi ini, Anda dapat mengontrol tampilan dan perilaku output pandas sesuai dengan preferensi Anda.

```python
# Menambah jumlah maksimum baris yang ditampilkan
pd.set_option('display.max_rows', 1000)

# Menambah jumlah maksimum kolom yang ditampilkan
pd.set_option('display.max_columns', 100)

# 1. Presisi angka desimal
pd.set_option('display.precision', 2)

# 2. Lebar kolom
pd.set_option('display.max_colwidth', 50)

# 3. Presisi datetime
pd.set_option('display.date_format', '%Y-%m-%d')

# 4. Floating-point formatting
pd.set_option('display.float_format', '{:.2f}'.format)

# 5. Menyembunyikan index
pd.set_option('display.show_index', False)
```

Dengan menyesuaikan pengaturan sesuai dengan kebutuhan Anda, Anda dapat meningkatkan pengalaman bekerja dengan DataFrame pandas. Terima kasih telah memberikan contoh lengkap!                                    
</details>

<a name="Read-and-Write-Data"></a>
# 2. Read and Write Data 👀

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
<details>
<summary align="left">🎀 More Explanation:</summary>
<br>

>`sep=';'`: Menggunakan titik koma (`;`) sebagai delimiter dalam file CSV.
>`skiprows=2`: Mengabaikan dua baris pertama dalam file CSV.
>`parse_dates=['Tanggal']`: Mengonversi kolom 'Tanggal' menjadi tipe data datetime.
>`na_values='Not Available'`: Menggantikan nilai 'Not Available' dengan nilai NaN untuk menangani nilai yang hilang.
>`usecols=['Tanggal', 'Column1', 'Column2']`: Membatasi pembacaan hanya pada kolom-kolom yang disebutkan dalam daftar tersebut.
</details>

- **pd.read_excel()**: Bring the world of spreadsheets into your DataFrame with pd.read_excel().
- **df.to_csv()**: Save your analysis results back to a shareable CSV format.
- **df.to_excel()**: Showcase your hard work in a neatly formatted Excel file.
- **df.to_sql()**: Let Pandas assist you in saving your DataFrame to your SQL database.
  
<a name="Info-and-Statistics"></a>
# 3. Info and Statistics 📈

- **df.info()**: Hand over control to Pandas to provide a comprehensive summary of your DataFrame's structure.
- **df.head()**: Take a sneak peek at your initial data to gain a quick understanding.
- **df.tail()**: Scroll through the tail end of your data to inspect the outcomes.
- **df.describe()**: Display statistical prowess with pd.describe() and uncover all the details.
- **df.shape**: Observe your DataFrame's dimensions, how many rows and columns it has.
- **df.columns**: Create a list of column names in the blink of an eye.
- **df.dtypes**: Use dtypes to reveal the secrets of column data types.
- **df.isnull()**: Let Pandas unveil the places where your data is missing.

<a name="Categorical-Data-Info"></a>
# 4. Categorical Data Info

### 💡 `df.unique()`
Metode ini digunakan untuk mendapatkan nilai unik dari suatu Series (kolom dalam DataFrame). Ini memberikan daftar nilai yang berbeda dari kolom tersebut.

<details>
    <summary align="center">🔥 Example</summary>
   
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
<details> 
    <summary align="right">
       🥇 More Details about `df.iteritems()` & `enumerate`! 
    </summary>
   
### 🌊 df.iteritems()

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

### 🌊 enumerate

`enumerate` adalah fungsi Python yang memberikan indeks dan nilai saat mengiterasi melalui suatu iterable. Berguna untuk mendapatkan kedua informasi tersebut selama iterasi.

Dalam contoh ini:

```python
for indeks, nilai in enumerate(nilai_unik):
    print(f"  Indeks {indeks}: {nilai}")
```

Loop ini mengiterasi melalui nilai-nilai unik dari suatu kolom (dengan `unique()`), mencetak indeks dan nilai untuk setiap elemen. `nilai_unik` berisi nilai-nilai unik tersebut.

Secara keseluruhan, `df.iteritems()` digunakan untuk iterasi kolom-kolom, dan `enumerate` digunakan di dalam loop untuk mendapatkan indeks dan nilai dari setiap nilai unik dalam suatu kolom. Ini memberikan ringkasan lebih detail dari DataFrame, termasuk nilai unik dan indeks mereka untuk setiap kolom.

</details>

**Output:**

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

</details>

### 💡 `df.nunique()`
Metode ini mengembalikan jumlah nilai unik dalam suatu Series. Ini memberikan informasi tentang seberapa bervariasinya data dalam kolom.

#### Example:

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
    
### 💡 `df.value_counts()`
Metode ini menghitung frekuensi masing-masing nilai dalam suatu Series. Ini memberikan wawasan tentang seberapa sering masing-masing nilai muncul dalam data.

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/7d3a1c3d-91f1-4f8f-b6c0-72e405219da8)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c790d96a-e99e-4c36-9f7c-872ba6f5986b)


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
  
 ### Simple Subset
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/72930bf9-b61e-4b6a-812a-347afa4e1c81)
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/093be7f9-8138-4832-a433-31b4922ab249)
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/34b6619c-eae1-4140-ade4-6254672e536c)

### Subset with Logical
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/76bc501d-c311-4a0c-b4e2-d549f5411482)
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/03bc113c-4091-43db-b7e3-a423988aa382)
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/9f9695b9-700f-4210-9127-11733e8f1b6d)
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/5727a4da-ba3b-4b4f-af37-68a4554507c8)

### Subset Multiple Condition
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8e905ab9-217f-449b-b9f3-450d8ab638dd)

### Subset with .isin()
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/20e81ff6-2211-46f0-84c1-a8fb50349420)







<details>
<summary align="center">🔥 Example</summary>

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
</details>

- `df.loc[]`: Perform selection based on row and column labels.
- `df.iloc[]`: Execute selection based on row and column indices.


<details>
<summary align="center">🔥 Example 1</summary>

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
</details>

<details>
<summary align="center" >🔥 Example 2</summary>
   
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
</details>

<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Data-Manipulation"></a>
# 6. Data Manipulation:

- `df.drop()`: Easily remove unwanted columns or rows.
- `df.drop_duplcates()`
   ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/5f8b723e-88da-4f11-abbe-98fc2d9b3bc5)

  
- `df.rename()`: Personalize your DataFrame by changing column or index names.
- `df.set_index()`: Give your DataFrame the index that suits you.
- `df.reset_index()`: Reset the index and reorganize your DataFrame to its original state.
- `df.sort_values()`: Use sort_values() to arrange data as you desire.

```python
# Sort homelessness by region, then descending family members
homelessness_reg_fam = homelessness.sort_values(["region", "family_members"], ascending=[True, False])

# Print the top few rows
print(homelessness_reg_fam.head())
```

<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Aggregation-and-Grouping"></a>
# 7. Aggregation and Grouping:

- **df.groupby()**: Create groups based on specific columns to perform aggregation operations.
- **df.agg()**: Let Pandas extract the information you need from grouped data.
- **df.pivot()**: Present your data in a beautiful pivot format.
- **df.melt()**: Transform data into a long format and discover the pattern.
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Merging and Joining)"></a>
# 8. Merging and Joining 🎎

Dalam Pandas, terdapat beberapa metode untuk menggabungkan atau menggabungkan dua DataFrames. Berikut adalah perbedaan antara tiga metode utama: `merge`, `concat`, dan `join`.

### 🎎 **`merge`:**
   - `merge` digunakan ketika kita ingin menggabungkan DataFrames berdasarkan nilai-nilai tertentu dalam kolom-kolom tertentu (seperti bergabung berdasarkan kolom kunci).
   - Secara default, `merge` menggunakan tipe gabungan "inner join" (gabungan dalam) di mana hanya nilai-nilai yang cocok di kedua DataFrames yang akan disertakan.
<details>
<summary align="center" >🔥 Example </summary>

```python
import pandas as pd

df1 = pd.DataFrame({'key': ['A', 'B', 'C'], 'value': [1, 2, 3]})
df2 = pd.DataFrame({'key': ['A', 'B', 'D'], 'value': [4, 5, 6]})

merged_df = pd.merge(df1, df2, on='key', how='inner')
print(merged_df)
```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/bdd2d055-2e50-4090-94ea-74bf460c4d06)
</details>

### 🎎 **`concat`:**
   - `concat` digunakan untuk menggabungkan DataFrames secara vertikal (menambahkan baris) atau secara horizontal (menambahkan kolom).
   - Secara default, `concat` melakukan penggabungan secara vertikal/bawah **(axis=0)** dan secara horizontal/samping **(axis=1)**.
<details>
<summary align="center" >🔥 Example</summary>

```python
import pandas as pd

df1 = pd.DataFrame({'A': [1, 2], 'B': [3, 4]})
df2 = pd.DataFrame({'A': [5, 6], 'B': [7, 8]})

# Use ignore_index to reset the index after concatenation
concatenated_df = pd.concat([df1, df2], axis=0, ignore_index=True)
print(concatenated_df)
```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ac227f09-6cfc-4aa8-b847-adb1369a893a)

By setting `ignore_index=True`, it resets the index to a default integer index after concatenation. This can be helpful if you want a clean, continuous index for the resulting DataFrame.
</details>

### 🎎 **`join`:**
   - `join` digunakan untuk menggabungkan DataFrames berdasarkan indeks mereka.
   - Secara default, `join` menggunakan tipe gabungan "left join" (gabungan kiri), yang akan menggabungkan semua indeks dari DataFrame pertama dan nilai-nilai yang cocok dari DataFrame kedua.
<details>
<summary align="center" >🔥 Example</summary>

```python
import pandas as pd

df1 = pd.DataFrame({'A': [1, 2], 'B': [3, 4]}, index=['X', 'Y'])
df2 = pd.DataFrame({'C': [5, 6], 'D': [7, 8]}, index=['X', 'Z'])

# Explicitly specify the column to join on
joined_df = df1.join(df2[['C', 'D']], how='left')
print(joined_df)
```

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/d051ae97-ce5f-468a-8b9a-3ad1e4ed88b9)


In this version, `df2[['C', 'D']]` is used to select only the 'C' and 'D' columns from `df2` before performing the join.
</details>
   
<details>
<summary>🎀 Ringkasan</summary>
   
- `merge` digunakan untuk menggabungkan berdasarkan kolom, 
- `concat` untuk menggabungkan secara vertikal atau horizontal,
- `join` untuk menggabungkan berdasarkan indeks. Pilihan metode tergantung pada kebutuhan spesifik analisis Anda.
 </details> 
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Data-Filling-and-Replacement"></a>
# 9. Data Filling and Replacement:
- `df.fillna()`: Fill missing values with policies you define.
- `df.replace(to_replace, value)`: Replace values with new ones as per your requirements.
  
<details><summary>Example:</summary>

```python
   short_movies['genre'] = short_movies['genre'].replace(['Uncategorized',
    'Comedies',
    'Dramas',
    'International Movies',
    'Action',
    'Music',
    'Classic Movies',
    'Anime Features',
    'Horror Movies'], "other")
   short_movies.sample(10)
```
**Output:**

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/17cab2dc-76c8-4f6b-832d-379214ed5028)

</details>
<a name="String-Operations)"></a>

# 10. String Operations

- **df['column'].`str.upper()`**: Elevate all letters to uppercase!
- **df['column'].`str.contains()`**: Unearth patterns in text with df['column'].str.contains().
- **df['column'].`str.title()`**: Capitalize the first letter of each word in the string.
- **df['column'].`str.capitalize()`**: Capitalize the first letter of the string.
- **df['column'].str.`swapcase()`**: Swap the case of each character (e.g., "aBc" becomes "AbC").
- **df['column'].str.`strip()`**: Remove leading and trailing whitespace.
- **df['column'].str.`lstrip()`**: Remove leading whitespace.
- **df['column'].str.`rstrip()`**: Remove trailing whitespace.
<details>
   <summary align="left">🌟 More Function! 🌟</summary>
<br>

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
</details>
  
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Datetime-Operations"></a>
# 11. Datetime Operations 📅
- **df['column'].dt.`year`**: Peek at the year effortlessly from a datetime column.
- **df['column'].dt.`month`**: Dip your fingers to unearth the month from datetime data.
- **df['column'].dt.`day`**: Extracts the day component from the datetime column.
- **df['column'].dt.`hour`**: Extracts the hour component from the datetime column.
- **df['column'].dt.`minute`**: Extracts the minute component from the datetime column.
- **df['column'].dt.`second`**: Extracts the second component from the datetime column.
  
<details>
   <summary align="left">🌟 More Function! 🌟</summary>
<br>
   
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
- **df['column'].dt.`week`**: Returns the week number of the year.
- **df['column'].dt.`weekday`**: Returns the day of the week as an integer, where Monday is 0 and Sunday is 6.
- **df['column'].dt.`quarter`**: Returns the quarter of the year as an integer (1-4).
- **df['column'].dt.`to_period('M')`**: Converts the datetime to a period with a specified frequency (e.g., 'M' for monthly).
- **df['column'].dt.`to_period('D')`**: Converts the datetime to a period with a daily frequency.
- **df['column'].dt.`strftime('format_string')`**: Allows you to format the datetime as a string using a custom format.
</details>

<details>
<summary align="center">🔥 Example 1</summary>

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
</details>

<details>
<summary align="center">🔥 Example 2</summary>
   
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
</details>
<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Data-Type-Conversion"></a>
# 12. Data Type Conversion

- df['column_name'] = df['column_name'].`astype('int64')`
- df['date_column'] = pd.`to_datetime(df['date_column'])`
  
<details>
   <summary align="center" >🔥 Example 1</summary>
   
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
</details>


<details>
   <summary align="center" >🔥 Example 2</summary>
   
```python
import pandas as pd

# Create a DataFrame with birthdates
data = {'Nama': ['Alice', 'Bob', 'Charlie', 'David'],
        'Tanggal_Lahir': ['1992-02-29', '1996-03-15', '1988-02-29', '1995-04-10']}

df = pd.DataFrame(data)

# Convert the 'Tanggal_Lahir' column to datetime
df['Tanggal_Lahir'] = pd.to_datetime(df['Tanggal_Lahir'])

# Extract year and check for leap year
df['Tahun_Kabisat'] = df['Tanggal_Lahir'].dt.year
df['Is_Kabisat'] = df['Tahun_Kabisat'].apply(lambda year: (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0))

# Select rows where the birthdate is on a leap year
leap_year_df = df[df['Is_Kabisat']]

# Display the DataFrame with leap year birthdays
print("DataFrame with Birthdays on Leap Years:")
print(leap_year_df[['Nama', 'Tanggal_Lahir', 'Tahun_Kabisat']])
```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/3302e1f5-a7f3-4099-a54b-5e79efe88e22)

</details>

- df['category_column'] = df['category_column'].`astype('category')`
- df['numeric_column'] = pd.`to_numeric(df['numeric_column'], errors='coerce')`
- df['boolean_column'] = df['boolean_column'].`astype(bool)`
- df['string_column'] = df['string_column'].`astype(str)`

<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Format-Method"></a>
# 13. Format Method

Metode `.format()` digunakan dalam Python untuk memformat string. Ini memberikan cara yang lebih fleksibel dan kuat daripada metode lama menggunakan `%` operator. Beberapa elemen kunci dalam metode `.format()` termasuk:

### 1. Placeholder Curly Braces `{}`
   - Curly braces digunakan sebagai tempat penampung atau placeholder untuk nilai yang akan dimasukkan ke dalam string.

     Contoh:
     ```python
     print("Hello, {}!".format("World"))
     ```

### 2. Urutan Argumen
   - Urutan argumen yang diberikan dalam metode `.format()` sesuai dengan urutan tempat penampung dalam string.

     Contoh:
     ```python
     print("Nama: {}, Usia: {}".format("John", 25))
     ```

### 3. **Penomoran Tempat Penampung:**
   - Anda dapat memberikan nomor pada tempat penampung untuk mengontrol urutan argumen.

     Contoh:
     ```python
     print("Nama: {0}, Usia: {1}".format("John", 25))
     ```

### 4. **Pemformatan Numerik:**
   - Anda dapat menggunakan format numerik khusus, seperti `{:.2f}`, untuk mengontrol jumlah angka desimal pada bilangan floating-point.

     Contoh:
     ```python
     value = 3.14159
     print("Nilai Pi: {:.2f}".format(value))
     ```

   - Pada contoh di atas, `:.2f` berarti dua digit di belakang koma untuk nilai desimal.

### 5. **F-Strings (Formatted String Literals):**
   - Dengan Python 3.6 ke atas, Anda dapat menggunakan f-strings sebagai alternatif yang lebih mudah dibaca dan menulis.

     Contoh:
     ```python
     name = "John"
     age = 25
     print(f"Nama: {name}, Usia: {age}")
     ```

   - Dalam f-strings, Anda dapat langsung menulis variabel di dalam string dengan menggunakan `{}`.

Jadi, singkatnya, metode `.format()` adalah cara untuk memasukkan nilai ke dalam string dengan lebih fleksibel, dan format numerik seperti `.2f` digunakan untuk mengatur tampilan angka desimal. F-strings adalah alternatif modern dan lebih ringkas untuk melakukan hal yang sama, terutama pada versi Python yang lebih baru.

<details>
<summary align="center">🔥 Example 1</summary>

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
</details>

<details>
<summary align="center">🔥 Example 2</summary>

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
</details>

<p align="right">(<a href="#top">back to top</a>)</p>

<a name="Apply-&-Lambda"></a>
# 14. Apply & Lambda

### 1. Lambda Functions
 - Improved the lambda function to explicitly mention the operation being performed.
 - Updated the print statements for clearer output.

   ```python
   multiply = lambda a, b: a * b
   print("Result of multiplication:", multiply(5, 6))

   check_even_odd = lambda x: 'Even' if x % 2 == 0 else 'Odd'
   print("Number is:", check_even_odd(8))
   ```
  

### 2. Apply with NumPy

  - Renamed variables for better readability.
   - Added comments to clarify the purpose of each line.

   ```python
   # Aggregating sum for each column and row
   sum_by_column = df_apply.apply(np.sum, axis=0)  # Sum for each column
   sum_by_row = df_apply.apply(np.sum, axis=1)  # Sum for each row
   ```
 

### 3. Apply with Custom Function

   - Simplified the segment function by directly working with the 'total_order' column.
   - Removed unnecessary lambda expression and variable assignments.
     
 <details>
  <summary align="center">🔥 Example</summary>

   ```python
  import pandas as pd

# Sample DataFrame
data = {'Name': ['Alice', 'Bob', 'Charlie', 'David'],
        'Age': [25, 30, 22, 35],
        'Salary': [50000, 60000, 45000, 70000]}

df = pd.DataFrame(data)

# Define a custom function with a conditional statement
def categorize_salary(salary):
    if salary >= 60000:
        return 'High'
    elif 50000 <= salary < 60000:
        return 'Medium'
    else:
        return 'Low'

# Apply the custom function to create a new column
df['Salary_Category'] = df['Salary'].apply(categorize_salary)

# Display the DataFrame with the new column
print(df)
   ```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/5e523023-203f-46f0-9e83-72e5e538563e)

</details>
   
### 4. Apply with Two Arguments
   - Kept the function as is since it is already concise and clear.

   ```python
   def segment_new(province, total_order):
       return 'Potential' if (province == 'DKI Jakarta') and (total_order >= 75) else 'Not Potential'

   df['segment_apply'] = df.apply(lambda x: segment_new(x['province'], x['total_order']), axis=1)
   ```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/f7f1859e-5dad-4165-8fce-5bf84b45bf1b)

   
### 5. Apply with Boolean Expression

   - Renamed the column to 'is_jakpus' for clarity.

   ```python
   df['is_jakpus'] = df['city'].apply(lambda x: x == 'Jakarta Pusat')
   df.head()
   ```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/cfb13a0c-6f5b-4eee-89d2-9336a2550d44)

### 6. Apply with String Slicing

- Maintained the string slicing for simplicity.

   ```python
   df['year'] = df['order_month'].apply(lambda x: x[:4])
   df.head()
   ```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ea2539ee-4cb9-457f-be4c-3329fe32fcaa)

     
### 7. Apply with One Line Conditional 

```python
import pandas as pd

# Sample DataFrame
data = {'Name': ['Alice', 'Bob', 'Charlie', 'David'],
        'Age': [25, 30, 22, 35],
        'Salary': [50000, 60000, 45000, 70000]}

df = pd.DataFrame(data)

# Apply a one-liner with a lambda function and conditional statement
df['Salary_Category'] = df['Salary'].apply(lambda x: 'High' if x >= 60000 else 'Medium' if 50000 <= x < 60000 else 'Low')

# Display the DataFrame
print(df)
```
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/54b1a582-8624-4de5-9ca8-ced798c2aa09)

### 8. Iterrows

Metode .iterrows() adalah metode yang digunakan dalam pandas untuk melakukan iterasi melalui baris-baris DataFrame. Ini menghasilkan generator yang menghasilkan indeks baris bersama dengan data baris sebagai Series.

```python
import matplotlib.pyplot as plt

colors = []
labels = []

for _, row in netflix_movies.iterrows():
    if row['genre'] == 'Children':
        colors.append('red')
        labels.append('Children')
    elif row['genre'] == 'Documentaries':
        colors.append('blue')
        labels.append('Documentaries')
    elif row['genre'] == 'Stand-Up':
        colors.append('green')
        labels.append('Stand-Up')
    else:
        colors.append('black')
        labels.append('Other')

fig = plt.figure(figsize=(12, 8))
plt.scatter(netflix_movies['release_year'], netflix_movies['duration'], c=colors, label=labels)

plt.xlabel("Release Year")
plt.ylabel('Duration')
plt.legend()  # Added legend to show color labels
plt.show()
```

Dengan menambahkan label, sekarang plot akan menampilkan legenda yang menjelaskan warna-warna yang digunakan untuk mewakili setiap genre.

## CASE STUDY

<details><summary>Case Study 1: Netflix Movie Data Camp</summary>

```python
# Print the head of the homelessness data
print(homelessness.head())

# Print information about homelessness
print(homelessness.info())

# Print the shape of homelessness
print(homelessness.shape)

# Print a description of homelessness
print(homelessness.describe())

```

```python
# Import pandas using the alias pd
import pandas as pd

# Print the values of homelessness
print(homelessness.values)

# Print the column index of homelessness
print(homelessness.columns)

# Print the row index of homelessness
print(homelessness.index)
```


```python

# Importing pandas and matplotlib
import pandas as pd
import matplotlib.pyplot as plt

# Read in the Netflix CSV as a DataFrame
netflix_df = pd.read_csv("netflix_data.csv")

# Subset the DataFrame for type "Movie"
netflix_subset = netflix_df[netflix_df["type"] == "Movie"]

# Select only the columns of interest
netflix_movies = netflix_subset[["title", "country", "genre", "release_year", "duration"]]

# Filter for durations shorter than 60 minutes
short_movies = netflix_movies[netflix_movies.duration < 60]

# Define an empty list
colors = []

# Iterate over rows of netflix_movies
for label, row in netflix_movies.iterrows() :
    if row["genre"] == "Children" :
        colors.append("red")
    elif row["genre"] == "Documentaries" :
        colors.append("blue")
    elif row["genre"] == "Stand-Up":
        colors.append("green")
    else:
        colors.append("black")
        
# Inspect the first 10 values in your list        
colors[:10]

# Set the figure style and initalize a new figure
fig = plt.figure(figsize=(12,8))

# Create a scatter plot of duration versus release_year
plt.scatter(netflix_movies.release_year, netflix_movies.duration, c=colors)

# Create a title and axis labels
plt.title("Movie Duration by Year of Release")
plt.xlabel("Release year")
plt.ylabel("Duration (min)")

# Show the plot
plt.show()

# Are we certain that movies are getting shorter?
answer = "no"
```

## Output:
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/f593a618-36c5-48cd-81e6-16aed8695c27)

</details>

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/688aafb1-3c6d-4e88-84be-ae1fc93267f3)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/e7bdb241-6e73-4e5b-a752-5c004ff2acaa)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c13fd896-3de4-4c66-a95d-6ae3af1e4e2e)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/76762fcd-051e-4528-b97a-22c434591464)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/1d828dfc-01c2-4a49-a07f-270642fc8e4d)

## Exampple
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/12522376-f5ff-4ef5-a414-de61b0e88d90)

### OUTPUT:
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c2405109-c525-417e-bac8-ccd519bf5497)

## Example
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/a4dfc12e-ffed-4060-bb42-a8bacecfb3fe)

### OUTPUT:
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/68aee280-b0f1-4a8c-b23c-2af30bd090ab)

## Example
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/77cb2c7e-17a2-4132-a470-af1f2e842cbe)

# Grouped AGG

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/49ea320d-4cd8-4490-bed7-a4c3f7bea416)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ab54f1f5-f8a8-44b6-acd2-071298f8461a)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/1d97f59d-e4af-49b0-a47a-0d4f098a74d8)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/050b9a6d-1159-4059-933d-6628b2f7fff8)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ac640600-cee3-4de2-98f6-e5b719263f57)

# Pivot Table
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/b3a3292d-6294-442a-96f0-3e47dd1ff0f9)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c17d006e-fa00-42be-b6f5-f9db5dafaf5c)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/9e3f9c44-854b-408b-a13a-0a4605b24987)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/a86cefa3-67ae-4186-b892-c236bf863843)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/4cfefdba-bbaa-41c5-a4eb-3d9c75071ac2)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/acb96915-2aeb-4688-a0c1-6d14ec08afd3)

# Indexing
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/701ac0d5-5b2a-4842-9bbe-7f8a3f3073f0)
  
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/6c502a66-b164-4d70-8617-bbc37ae6e7e6)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8fd0ffab-f9c4-4ef7-a7c6-80beb4d02ab4)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/6dba6035-38c1-4e6c-8a16-02f11ba536e4)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/7ade9f92-30a5-4673-8668-8058e93bcafb)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/7e001212-49cc-45f8-8f2a-639246ece2ad)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/69d894af-544d-4fc0-a976-57cb54ccbcb9)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/2ac8a517-d96d-424e-a91f-93f7636ec5c6)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/afc7bb38-dd77-4dce-bbdc-0c3e12a238da)

## EXAMPLE

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/4333d28d-eee5-44a0-9bd9-fdcc69e9d5d9)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/44065e85-b1c1-465b-adee-626d54ed10c0)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/69238c5f-443d-4421-8e22-4fd8230b9dc1)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ab53803b-3bfa-4deb-86a2-d0dae981c352)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/03299012-b9f0-48a3-a9a8-fdde4a22e045)
  
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/fe0594f0-7f7a-4de0-9a9a-9748b338ee83)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/b0ff6bc9-736d-400d-bf7e-0d638e05c02c)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8de63981-c6a6-4aa7-b824-bf8b5744ab43)

# SLICING .loc()  

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/43c3ac30-a585-4e0c-bf8a-1339f7d530a7)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/4e1a15df-33ae-4a31-9730-deabb9ea8218)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/e9bc1975-5a73-4ffd-9d37-b5a7aafd0228)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/cc7f8a28-1372-4938-a54a-784506202850)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/cba1a517-a163-414c-9439-dde6696494c7)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/04fbf3d9-0d72-49e0-98a4-3b1341803c44)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/7e32ed62-eaf5-4b88-9504-9bce7c6e02c1)


# SLICING .iloc()
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/678839c5-7405-44bf-86cc-33a0f97e1103)


- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/da83902f-105c-40c0-9b2a-8099babd5e77)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/6465c5f0-fbd8-4557-91b2-284f076f0f74)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/3ac4c8ef-ac20-46c7-853f-a6c2f2ba8675)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c838acc6-1ba3-49da-86ea-822d48b840c7)


- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/912f6b46-9d70-41df-9e74-2536365c294a)

  ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/e213899c-0883-40b8-81e6-693e61241417)

# Working with PIVOT Table


- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/7f0f7074-ba8e-48d4-92f0-58e85002221d)


- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/eb7fab4c-04c5-4226-ab35-fbb9f74cbd21)


- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/b96fa151-435d-4d9a-9dee-c2b2e4776eae)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/69f16887-1089-4d6c-ae71-b8524f3223f6)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/cba6cd45-0873-4e3f-9e27-a22b4db43aa0)


- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/5e646879-337c-4a77-8017-b91228c89e0a)


![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/88361923-7535-4261-9166-0758f6afbf1c)


- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/a261e167-89f4-44cb-8065-530059f62615)


![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/1c6287c5-cd47-4509-9e6b-c1b8e28d43f3)

### Example:

 - ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/18ff388d-b1d1-49e5-a705-01b373f32c4a)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/79995f7d-8afa-439d-8f90-1f2b8c1edd6e)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/10430646-43d9-4c7d-b485-6a1174099499)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ecb24653-b84b-4262-9bb2-ea09cedb7488)

# Dataframes

## List Dicts by Row

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/7575ff4e-cb1f-4587-b028-b2eb514b81c0)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/e9140db3-f96a-4a5c-b67c-452ae43cdb61)

## List Dicts by Column

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/6cbcf597-382a-47c5-9230-15a091ed10df)

# Joining Data
## Inner Join
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/f0977207-ea9c-48a7-8676-b2d37ef2af3d)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/3e51057a-320a-4f5a-bce2-fbcff0d01fef)

## Merge
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/500ddef5-19ff-4f13-94d5-75244deb8735)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/7dfc26d7-30db-44d9-bf57-52716dd6275e)

  ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/13722353-73c5-48d4-847e-56ee469bc340)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/6f41d52a-dbb6-4f83-b1e1-acad41b8a0e7)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/844b6bdd-2357-4478-9f3f-476f311b7f07)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8355d10b-b6ec-45d6-aa28-7d40f51ce852)


- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/281af68f-a8a3-4776-86da-26ee3c1eb0b1)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/f2a3f2a7-6e3b-462b-89bf-6981d1b6ee11)

-![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/cde3f356-7ef0-44e0-aa39-d45ace0b9a07)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/357eea1b-56f3-4657-951f-dc34e8f28090)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/197fa0d2-7360-44e9-a535-5da822e04d5b)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/d7bdf33d-3de4-4804-b076-a3ad0db752ea)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8018c4d5-b4d0-48a0-8909-cc4656687c6e)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/27dabe2b-e66f-44ba-a23b-68d08acdc7ae)


# Index
-![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/1a01891c-b33d-4d52-a1a6-678f2cb7f551)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/2e8a2726-8f3b-4d14-a7c9-22fadb01fdfe)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/83072fa4-44ec-45eb-a298-50b70cce62cb)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/0d250053-5d1b-493e-946b-9610c9ac0b12)

# Concat Dataframe

## Basic
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/64427d65-8173-4e1e-af7e-a6f4451bcc42)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/a620311b-bc4b-4b54-8a89-a992c2cb4da4)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/26687aff-2bbb-4838-8046-047b5c11461a)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/751ea302-b913-4c53-8cc3-cf849f6cab23)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ed0bdd19-a56b-4354-b219-1a26776c5d4a)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/fab734df-fd09-48ef-a571-c565a15eb59e)

## Merge Validating
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/4bc56f6a-05e9-4f54-a399-e0874ea0362a)

## Check Duplicate
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/cc786bb4-7d7f-48be-b59b-eca636730bc4)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/bacbc020-b27d-48fb-a3d6-2e40e779fbc4)

## .merge_ordered
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/28b7c4f4-d9c5-4869-bc9a-2f6790bd2351)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/395a47d4-7073-4bce-afa3-034facc968c8)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/118e50dc-1c6a-45fd-88f8-673cc4384da5)

# .query()

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/628a7c45-33b6-4fe3-8ed1-afa53988d0bb)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/5984a5cd-54ef-4860-b67a-962a13770f6b)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/24688693-15b3-4638-902a-551d5b86b526)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/1ac6a381-ae53-4587-97f4-200deccb1edb)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c81735d2-f9cc-4cb1-aea3-0ac3a5ba6e10)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/17ef2b3b-1eea-4cf0-8226-80f3a6b52ccc)

# .melt() / Unpivot DataFrame

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/f3a85ee1-3229-41b7-8dd3-64e5dc6f859d)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/aa4692c2-a5a3-493d-bf0c-84515cbc32d3)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/dcf8c44a-dccd-4032-b423-a3cbbe9a6dd9)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/66d9b6cd-ce43-45f1-b66e-05d64d08edae)

### Example:
-![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/91776069-e5d8-4494-924c-d39824fe3775)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/603bb618-e629-4027-97aa-f35a5830555b)

# STATISTIC

## Type of stat
-![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8f155545-198f-41ea-8473-3db4bbaba838)

## Type of Data

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/eb5832cf-c4a7-4ab4-a34d-5702eedd8386)
-![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ac4b6160-fbd9-4482-b009-49d5bb758595)

## Measure of center
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8d39100b-293c-4ea0-9239-4caeec574025)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/294498fa-c546-4e83-a23b-aeaea945efe5)

## Measure of Spead

### Variance
  ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/3375be11-9296-41df-ac0a-13470486dffb)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/3606c854-a839-4bd7-9659-ae2896ce6ee1)

### STD
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/19bc0c66-6b20-436a-98b3-8ff77988a4e4)

### Quantiles
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/112bf2c8-b13c-4a7e-b9e2-f16c97dcdbd9)

- Boxplot
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8ef3e4ee-7508-48b1-b617-3af0c2657287)

### IQR
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/30e704a9-8841-4f8a-973e-0c31e834e40f)

### Outliers

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ea664705-8498-42a2-8ffe-e835efe56656)

# Correlation 

- Berhubungan dengan liniaritas 2 variabel -> `tidak menunjukkan causality`
  
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/8460fe82-683e-4fdd-9990-40288eb58ab7)

# Data Vuz - Pyplot

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/172db3d0-b801-4daf-8427-9d84b89bdc6c)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/d9e91d3f-a784-4718-a61f-5fbfbb7cc35b)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/f9a9fc23-6ed2-479b-b863-6e7912587f51)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/89c83b1d-470a-471b-a2d0-9cf2812cd9a8)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/f7704126-1fe8-4208-8828-8b70a79cd6ef)

## SubPlot

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ef10157e-6183-4801-897f-ccf65663e773)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/eb55a237-af72-488b-8fc6-740911efef8d)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/faa24b85-8e8a-439c-a8a2-5bda62cc209f)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/72873d6b-bfcc-442a-967a-7b50e8818f77)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/fea9f1e2-37f6-415f-a09d-b60d581f9a50)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/a58610a4-1a99-4403-b3e9-f27c6d210005)

### Plot Zooming Time Series

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/678e597e-5040-43df-9bb2-32ac89e6acec)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/6ef677a0-2854-4691-a25a-24cc2965264d)

#### Example:

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/013fb96e-2c16-4e6e-9a97-f4913d43969c)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/010266bf-6aa7-461e-8e35-d32bf3667d72)

### Plot Twin Axes

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/d96c2b4e-294d-4b83-a439-0fef3b06266c)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/cee7bfd8-bcb0-4209-8c05-fd627ecacef9)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/00c3b0b5-51a0-4f75-a439-46807dc4058b)

### Funtion Plot Data Time Series

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/95781b72-50ca-4b06-8405-e4de5ca5fc9e)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c3471240-73f8-4d9f-8893-08df0d166a23)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/6f77fdeb-bb9d-4cf3-8cf7-e0369e480235)

# Quantitative Comparison
## Bar charts
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/a7cf0bc3-9f95-4966-97e3-7c965ea1ebd1)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/9341ad6e-c1ea-4a46-8bd8-d6d07da86574)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/0270615a-aff3-4de2-af51-1d5507f2f44b)

- Stacked Bar
 ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/4953003c-1779-4617-ba93-1bbb3faabca8)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/1cf1fd36-aafa-4fa7-a46e-68e19e40bd99)

## Histogram

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ca69929c-832c-4d9e-8132-840d4f0ae855)

## Boxplot
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/543244e4-a0ab-46e5-95af-f5b30026652f)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/dda251c3-1acf-4247-bfa8-0a1d6b2ba1c4)

## Scatter Plot
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/d732fbc6-c809-437a-83c3-4b3baab92b41)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/41d20a07-0774-4d55-8cb6-25d87b7528ca)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/0ba69f72-b26e-4f04-86b0-976c34f255fc)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/5bf6045e-46e3-4bae-a26a-4bbd51d31479)

## Savefig

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/94cf239c-ac5d-4934-8822-cadaf2b64a7f)

# SEABORN (pandas + matplotlib) --> https://seaborn.pydata.org/

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/b4e864c7-f9d2-4559-b6a1-123a7183505e)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/1789830e-438a-4e3b-bbe0-87d24293680c)

## Countplot
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/4ba8d441-5d14-4985-8e82-86f2ee1e0f7c)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/33bacba1-0e00-47e2-a50b-c9cbb2312d6d)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/d6e34d43-ce99-4926-b798-03268c262f84)

## Relplot
### scattter Plot
-![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ad5ad892-897b-42c2-b28c-3cda48311536)

-![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/6c69acfd-45b4-414a-87cc-bef1fa4e98f5)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c3b64ca1-9792-4a02-a546-320113b01cb3)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/9ac95721-78de-4f01-9cce-bd8f269c0104)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/25e6251c-a7fb-4cb2-a0c3-4ed2be40be3b)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/e6fd4131-f95b-4235-ab0d-0533fc6fa118)

#### Customize scatter
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/f018a20b-75c1-4004-a1c4-42a5579a8eaf)
  
#### Quantitative 
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/5d090dda-a867-45a1-8d54-cd2d0870f25f)
-  ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/b993fa67-8951-4696-b000-ad354a38f3c7)
 
#### Categorize
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/f874ae44-8381-4d47-bb99-f1e994bff0d8)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/9393e17c-641e-4556-b46f-0b5ce4f21128)
  
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/04bf2f67-e310-4a91-aa1b-f730b0d036c1)

### Line PLot
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/52666d5f-9824-4974-a5d6-4255afc01d0a)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/017c7639-bfc6-4e4b-a4f7-7711316fd918)

## Catplot

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/b23460af-1095-4f22-b277-41f21fac9cc5)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/0e1a3827-6576-4ca9-9b77-d4ac0fd1ae47)
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/5b967ccc-ba91-4b7d-9a48-f4d68bc01249)
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/33126525-5357-4e2e-8f9e-cde0f6c49b16)

![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/36f9d5ce-4686-4ab2-a64c-5e94ff7a1929)

## Boxplot
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c7168f11-d2f5-41f8-b67f-bb61f07c4d51)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/0e23d7a9-2437-40ab-984d-ec0962f1280a)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/d49d995f-1137-4995-8e07-21cf247c97f6)

# Color Pallete
## Color
![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/fac5ed37-0200-486d-9a95-95dc863588fc)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/ae7d3b05-f00b-447d-8d76-c2179798670e)

## Sequential
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/6cef0bf2-9b88-4baa-be10-f210d6d88d57)
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/e436d83d-6152-46f5-8ad5-86daa2f69f32)

## set scale
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/2d6dad15-e3e1-4cf8-a629-119c0ff1c4a5)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/78773c98-6878-45d2-beb9-190e10107fdb)



# 
##  FacetGrid vs. AxesSubplot objects
- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c13db333-4838-492c-92c0-37cd823d8975)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/c8b62085-6e3f-4faa-8214-c97aa29bb65a)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/52aea95f-89c1-4f3b-9255-66ae05100228)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/a6d89983-2bf6-4dd5-9647-55f6fea7124a)

- ![image](https://github.com/Data-Portofolio/The-Ultimate-Pandas-Guide-Simplifying-Data-Operations/assets/133883292/a6e1ad03-29d4-4fe1-99e6-1745e35ea443)


<p align="right">(<a href="#top">back to top</a>)</p>

<p align="center">
    :copyright: 2023 | A-Rahmawati </p>
</h3>



