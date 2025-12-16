# DataFrame Operations

Bu dokümanda **Pandas DataFrame** ile yapılan temel işlemler,
**kodlar ve örnek çıktılarla** birlikte gösterilmektedir.

---

## İçerik
- DataFrame Oluşturma
- Sütun ve Satır İşlemleri
- Veri Filtreleme
- Veri Okuma Yöntemleri
- Veri Yazma Yöntemleri

---

## Pandas Kütüphanesini Import Edelim

```python
import pandas as pd
```

---

## Boş DataFrame Oluşturma

```python
df_empty = pd.DataFrame()
df_empty
```

**Çıktı:**

|   |   |
|---|---|

---

## Dictionary nesnesi ile DataFrame oluşturma

```python
d = {
    "Model": ["m1", "m2", "m3"],
    "Seri": ["s1", "s2", "s3"],
    "Yil": [2001, 2002, 2003],
    "Fiyat": [1000.0, 2000.0, 3000.0]
}

df = pd.DataFrame(d)
df
```

**Çıktı:**

|   | Model | Seri | Yil | Fiyat |
|---|-------|------|-----|-------|
| 0 | m1 | s1 | 2001 | 1000.0 |
| 1 | m2 | s2 | 2002 | 2000.0 |
| 2 | m3 | s3 | 2003 | 3000.0 |

---
# DataFrame Veri Filtreleme

## Tek Bir Sütun Seçme

> [!TIP]
> Alan ismi tek kelime ise doğrudan yazılabilir, değilse df["Model"] şeklinde yazılmalıdır.

```python
df.Model
```

**Çıktı:**

| index | Model |
|------|-------|
| 0 | m1 |
| 1 | m2 |
| 2 | m3 |

---

```python
df["Seri"]
```

**Çıktı:**

| index | Seri |
|------|------|
| 0 | s1 |
| 1 | s2 |
| 2 | s3 |

---

## Birden Fazla Sütun Seçme

> [!TIP]
> Birden fazla sütun seçerken çift parantez `[[ ]]` kullanılması gerektiğini unutmayın.

```python
df[["Yil", "Fiyat"]]
```

**Çıktı:**

|   | Yil | Fiyat |
|---|-----|-------|
| 0 | 2001 | 1000.0 |
| 1 | 2002 | 2000.0 |
| 2 | 2003 | 3000.0 |

---

## Veri Filtreleme

### 2002 ve Üzeri Yıllar

```python
df[df["Yil"] >= 2002]
```

**Çıktı:**

|   | Model | Seri | Yil | Fiyat |
|---|-------|------|-----|-------|
| 1 | m2 | s2 | 2002 | 2000.0 |
| 2 | m3 | s3 | 2003 | 3000.0 |

---
## Veri Filtreleme İşlemleri
> [!TIP]
> Fiyat alanı boş olan satırlar

```python
df[df["Fiyat"].isnull()]
```
**Çıktı:**
| | Model | Seri | Yil | Fiyat |
|---|---|---|---|---|


## Fiyat alanı dolu olan satırlar

> [!TIP]
> Fiyat alanı dolu olan satırlar

```python
df[df["Fiyat"].notnull()]
```
**Çıktı:**
| | Model | Seri | Yil | Fiyat |
|---|---|---|---|---|
| 0 | m1 | s1 | 2001 | 1000.0 |
| 1 | m2 | s2 | 2002 | 2000.0 |
| 2 | m3 | s3 | 2003 | 3000.0 |

## iloc ile Satır Seçme

> [!TIP]
> 0. satırı ver

```python
df.iloc[0]
```

**Çıktı:**

| Alan | Değer |
|-----|------|
| Model | m1 |
| Seri | s1 |
| Yil | 2001 |
| Fiyat | 1000.0 |

---

> [!TIP]
>iloc[m:n] m. satırdan başlayarak n. satıra kadar olanları ver (n dahil değil) 


```python
df.iloc[1:3]
```

**Çıktı:**

|   | Model | Seri | Yil | Fiyat |
|---|-------|------|-----|-------|
| 1 | m2 | s2 | 2002 | 2000.0 |
| 2 | m3 | s3 | 2003 | 3000.0 |

---
# DataFrame'den Alan Silme

## Tek bir alan silme

```python
del df["Model"]
df
```

**Çıktı:**

|   | Seri | Yil | Fiyat |
|---|------|-----|-------|
| 0 | s1 | 2001 | 1000.0 |
| 1 | s2 | 2002 | 2000.0 |
| 2 | s3 | 2003 | 3000.0 |

---
## Birden fazla alan silme
```python
df.drop(["Yil", "Fiyat"], axis=1, inplace=True)
df
```

**Çıktı:**

|   | Seri |
|---|------|
| 0 | s1 |
| 1 | s2 |
| 2 | s3 |

---
# Veri Okuma Yöntemleri

## CSV Dosyasından Veri Okuma


> [!TIP]
> Dosyadaki ilk satır başlık içermiyorsa header=None kullanılır


```python
data = pd.read_csv("test_pandas.csv", header=None)
data
```

**Çıktı (örnek):**

| 0 | 1 | 2 | 3 |
|---|---|---|---|
| 0 | 1 | cat | 1.1 |
| 1 | 2 | dog | 2.2 |
| 2 | 3 | bird | 3.3 |

---

## Excel Dosyasından Veri Okuma

```python
data = pd.read_excel("test_pandas.xlsx")
data
```

**Çıktı:**

| Unnamed: 0 | Column A | Column B | Column C |
|-----------|----------|----------|----------|
| 0 | 1 | cat | 1.1 |
| 1 | 2 | dog | 2.2 |
| 2 | 3 | bird | 3.3 |

---

## Index Ayarlama


> [!TIP]
> Yukarıda Unnamed: 0 alanı Excel dosyasında index alanı olduğu için bu sütun index olarak kullanılabilir


```python
data.set_index("Unnamed: 0", inplace=True)
data
```

**Çıktı:**

| Unnamed: 0 | Column A | Column B | Column C |
|-----------|----------|----------|----------|
| 0 | 1 | cat | 1.1 |
| 1 | 2 | dog | 2.2 |
| 2 | 3 | bird | 3.3 |

---
> [!TIP]
> <font color="red">inplace=True</font> parametresi ile yapılan değişiklik orjinal DataFrame üzerinde güncellenir 

## HTML Üzerinden Tablo Okuma

```python
df = pd.read_html(
"https://en.wikipedia.org/wiki/List_of_countries_by_GDP_(nominal)"
)[2]

df.iloc[:5]
```

**Çıktı (ilk 5 satır):**

| index | Country / Territory | IMF Forecast | IMF Year | World Bank Estimate | WB Year | United Nations Estimate | UN Year |
|------:|---------------------|-------------:|---------:|--------------------:|--------:|------------------------:|--------:|
| 0 | World | 109,529,216 | 2024 | 105,435,540 | 2023 | 100,834,796 | 2022 |
| 1 | United States | 28,781,083 | 2024 | 27,360,935 | 2023 | 25,744,100 | 2022 |
| 2 | China | 18,532,633 | 2024 | 17,794,782 | 2023 | 17,963,170 | 2022 |
| 3 | Germany | 4,591,100 | 2024 | 4,456,081 | 2023 | 4,076,923 | 2022 |
| 4 | Japan | 4,110,452 | 2024 | 4,212,945 | 2023 | 4,232,173 | 2022 |


## Veritabanından Veri Okuma (SQLite)

> [!TIP]
> Veri tabanına bağlan, yoksa oluştur


> [!TIP]
> SQL Kodu detayları için SQL komutları konusunu araştırın!


```python
import sqlite3

conn = sqlite3.connect("test_pandas.db")
sql = "SELECT * FROM test"
data = pd.read_sql(sql, conn)
data
```

**Çıktı (örnek):**

| index | id | city           | mascot     |
|-------|----|----------------|------------|
| 0     | 1  | San Francisco  | 49ers      |
| 1     | 2  | Oakland        | Raiders    |
| 2     | 3  | Seattle        | Seahawks   |
| 3     | 4  | Chicago        | Bears      |
| 4     | 5  | NYC            | Jets       |
| ...   | ...| ...            | ...        |
| 83    | 7  | ANA            | Chargers   |
| 84    | 6  | LA             | Rams       |
| 85    | 7  | ANA            | Chargers   |
| 86    | 6  | LA             | Rams       |
| 87    | 7  | ANA            | Chargers   |


> [!NOTE]
> Diğer veri okuma yöntemleri:
> - `pd.read_json()` : JSON dosyasından veri oku
> - `pd.read_xml()`  : XML dosyasından veri oku
> - `pd.read_pickle()` : Pickle dosyasından veri oku
> 
> Örnekleri çoğaltmak mümkün.


### Veritabanına Yazma

> [!TIP]
> Test tablosuna yaz, bu tablo yoksa oluştur, varsa üzerine ekle


```python
data.to_sql("test", conn, if_exists="append", index=False)
```

### CSV’ye Yazma

> [!TIP]
>index=False kodu ile yazarken indeksleri yazma

```python
data.to_csv("yeni_dosya.csv", index=False)
```

### Excel’e Yazma

```python
data.to_excel("yeni_dosya.xlsx", index=False)
```

---

## Sonuç

Bu çalışmada Pandas ile:

- DataFrame oluşturma
- Satır ve sütun işlemleri
- Farklı kaynaklardan veri okuma
- Verileri CSV, Excel ve veritabanına yazma

işlemleri **örnekler ve tablolarla** gösterilmiştir.
