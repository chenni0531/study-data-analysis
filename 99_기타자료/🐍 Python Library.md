# π Python Library

[TOC]

pandas

numpy

seaborn

matplotlib.pyplot

from mlxtend.frequent_patterns import apriori
from mlxtend.frequent_patterns import association_rules
import mlxtend as ml





### missingno

- ν¨μ `matrix()` κ²°μΈ‘ λ°μ΄ν°λ₯Ό μκ°ν 
  - κ²°μΈ‘λ λ°μ΄ν°λ ν°μμΌλ‘, κ·Έλ μ§ μμ λ°μ΄ν°λ κ²μμμΌλ‘
  - μ€νν¬λΌμΈ(spark line): κ° νμ λ°μ΄ν° μμ±λ

- ν¨μ `bar` κ° μ΄μ κ²°μΈ‘ λ°μ΄ν°κ° μΌλ§λ μ‘΄μ¬νλμ§ μκ°ν

<br>

### pandas

- λ©μλ `dropna()` κ²°μΈ‘ λ°μ΄ν°κ° μ‘΄μ¬νλ νμ΄λ μ΄ μ§μ°κΈ°
  - μΈμ `axis=1` κ²°μΈ‘ λ°μ΄ν°κ° μλ μ΄μ μ κ±°
  - μΈμ `thresh=7` 7κ° μ΄μμ λΉκ²°μΈ‘ λ°μ΄ν°κ° μλ ν λλ μ΄λ§ λ¨κΈ°κΈ°

<br>

### scikit-learn

- ν΄λμ€ `SimpleImputer` : κ²°μΈ‘ λ°μ΄ν°λ₯Ό λμ²΄
  - μΈμ `strategy` λμ²΄κ° μ€μ  (= `"mean" `/ `"median"` / `"most_frequent"`)
  - λ©μλ `fit_transform` λμ²΄κ°μ΄ μ±μμ  λ°μ΄ν°νλ μμ μμ±

```python
from sklearn.impute import SimpleImputer

imputer = SimpleImputer(strategy="most_frequent")
df = pd.DataFrame(imputer.fit_transform(df), columns=df.columns)
```

**preprocessing μλΈν¨ν€μ§**

- ν΄λμ€`StandardScaler` : μ€μΌμΌλ§ λ° λ³μλ³ν
  - λ©μλ `fit()` νκ· κ°κ³Ό νμ€νΈμ°¨λ₯Ό κ³μ°νμ¬ κ°μ²΄λ΄μ μ μ₯
  - λ©μλ `transform()` μ μ₯ν κ°μ ν λλ‘ μλ‘μ΄ νκ· κ°μ΄ 0, μλ‘μ΄ νμ€νΈμ°¨κ° 1μ΄ λλλ‘ λ°μ΄ν°λ₯Ό λ³ννμ¬ μΆλ ₯
  - λ©μλ `fit_transform()` μμ κ³Όμ μ νκΊΌλ²μ

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
scaler.fit_transform(X)
```

- ν΄λμ€ `RobustScaler` :μ€μκ°μ΄ 0, IQR(interquartile range)μ΄ 1μ΄ λλλ‘ λ³ν

```python
from sklearn.preprocessing import RobustScaler

scaler = RobustScaler()
scaler.fit_transform(X)
```

- ν΄λμ€ `FunctionTransformer` : λ°μ΄ν° λ³ν - μ¬μ©μκ° μ§μ ν ν¨μλ₯Ό μ¬μ©νμ¬ μλ ₯κ°μ λ³ν
- ν΄λμ€ `PolynomialFeatures` : λ°μ΄ν° λ³ν - μλ ₯λ°μ΄ν°λ₯Ό μ¬λ¬ κ°μ λ€ν­μμΌλ‘ λ³ν
  - μΈμ `degree` μ°¨μ
  - μΈμ `include_bias` μμν­ μμ± μ¬λΆ

```python
from sklearn.preprocessing import PolynomialFeatures

poly = PolynomialFeatures(degree=2)
poly.fit_transform(X)
```



<br>

### sns

- ν¨μ `countplot` λ°μ΄ν° λΆν¬ μκ°ν

<br>

### patsy

λ°μ΄ν°νλ μμμ μνλ λ°μ΄ν°λ§ μ ννκ±°λ μλ‘μ΄ λ°μ΄ν°λ₯Ό μ‘°ν© μμ±

- ν¨μ `demo_data()` 

  - xλ‘ μμνλ λ³μμ λν΄ μμμ μ€μ λ°μ΄ν°λ₯Ό μμ±
  - λ°μ΄ν° νλ μμ μμν­μ μΆκ°νκ±°λ μνλ λ°μ΄ν°λ§ μ ννκ±°λ λ³ν

  - λͺ¨ν μ μ λ¬Έμμ΄ `formula`
    - μ§μ ν λλ‘ λ³νλ λ°μ΄ν° μΆλ ₯
    - μ ννκ³ μ νλ λ°μ΄ν° μ΄ μ΄λ¦μ `+`λ‘ μ°κ²°: ν΄λΉ λ°μ΄ν°λ§ λ½μμ€λ€

```python
df = pd.DataFrame(demo_data("x1", "x2", "x3", "x4", "x5"))

# μ μ²΄ λ°μ΄ν° μ€ x1λ§μ λ½κΈ°
dmatrix("x1 + 0", data=df)

# μ μ²΄ λ°μ΄ν° μ€ x1, x2, x3λ₯Ό λ½κΈ°
dmatrix("x1 + x2 + x3 + 0", data=df)

# 1λ‘ κ΅¬μ±λ μμν­μ λ£μ§ μκΈ°
dmatrix("x1 + x2 + x3", data=df)
dmatrix("x1 + x2 + x3 - 1", data=df)

# μν λ³ν
dmatrix("x1 + np.log(np.abs(x2))", df)

# μνΈμμ©(interaction)
dmatrix("x1 + x2 + x1:x2 + 0", df)
dmatrix("x1 * x2 + 0", df)

# μνΈμμ©μ μ μΈν κ²½μ°μλμ°μ°κ³Όμ μ λͺμ
dmatrix("x1 + x2 + I(x1 + x2) + 0", df)
```

**μ€μΌμΌλ§(scaling)** μ‘°κ±΄μμ μν₯μ μ€μ΄κΈ° μν΄ νκ· μ 0μΌλ‘ νμ€νΈμ°¨λ₯Ό 1μΌλ‘ λ§λλ μμ

- ν¨μ `center()`νκ· μ 0μΌλ‘ μ€μΌμΌλ§
- ν¨μ `standardize()` / ν¨μ `scale()` νκ· μ 0μΌλ‘νκ³  νμ€νΈμ°¨λ₯Ό 1λ‘ μ€μΌμΌλ§

```python
dm = dmatrix("center(x1) + 0", df)

# νκ· κ° μ μ₯
dm.design_info.factor_infos
```

