# 🐍 Python Library

[TOC]

pandas

numpy

seaborn

matplotlib.pyplot

from mlxtend.frequent_patterns import apriori
from mlxtend.frequent_patterns import association_rules
import mlxtend as ml





### missingno

- 함수 `matrix()` 결측 데이터를 시각화 
  - 결측된 데이터는 흰색으로, 그렇지 않은 데이터는 검은색으로
  - 스파크라인(spark line): 각 행의 데이터 완성도

- 함수 `bar` 각 열에 결측 데이터가 얼마나 존재하는지 시각화

<br>

### pandas

- 메서드 `dropna()` 결측 데이터가 존재하는 행이나 열 지우기
  - 인수 `axis=1` 결측 데이터가 있는 열을 제거
  - 인수 `thresh=7` 7개 이상의 비결측 데이터가 있는 행 또는 열만 남기기

<br>

### scikit-learn

- 클래스 `SimpleImputer` : 결측 데이터를 대체
  - 인수 `strategy` 대체값 설정 (= `"mean" `/ `"median"` / `"most_frequent"`)
  - 메서드 `fit_transform` 대체값이 채워신 데이터프레임을 생성

```python
from sklearn.impute import SimpleImputer

imputer = SimpleImputer(strategy="most_frequent")
df = pd.DataFrame(imputer.fit_transform(df), columns=df.columns)
```

**preprocessing 서브패키지**

- 클래스`StandardScaler` : 스케일링 및 변수변환
  - 메서드 `fit()` 평균값과 표준편차를 계산하여 객체내에 저장
  - 메서드 `transform()` 저장한 값을 토대로 새로운 평균값이 0, 새로운 표준편차가 1이 되도록 데이터를 변환하여 출력
  - 메서드 `fit_transform()` 위의 과정을 한꺼번에

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
scaler.fit_transform(X)
```

- 클래스 `RobustScaler` :중앙값이 0, IQR(interquartile range)이 1이 되도록 변환

```python
from sklearn.preprocessing import RobustScaler

scaler = RobustScaler()
scaler.fit_transform(X)
```

- 클래스 `FunctionTransformer` : 데이터 변환 - 사용자가 지정한 함수를 사용하여 입력값을 변환
- 클래스 `PolynomialFeatures` : 데이터 변환 - 입력데이터를 여러 개의 다항식으로 변환
  - 인수 `degree` 차수
  - 인수 `include_bias` 상수항 생성 여부

```python
from sklearn.preprocessing import PolynomialFeatures

poly = PolynomialFeatures(degree=2)
poly.fit_transform(X)
```



<br>

### sns

- 함수 `countplot` 데이터 분포 시각화

<br>

### patsy

데이터프레임에서 원하는 데이터만 선택하거나 새로운 데이터를 조합 생성

- 함수 `demo_data()` 

  - x로 시작하는 변수에 대해 임의의 실수 데이터를 생성
  - 데이터 프레임에 상수항을 추가하거나 원하는 데이터만 선택하거나 변형

  - 모형 정의 문자열 `formula`
    - 지정한 대로 변환된 데이터 출력
    - 선택하고자 하는 데이터 열 이름을 `+`로 연결: 해당 데이터만 뽑아준다

```python
df = pd.DataFrame(demo_data("x1", "x2", "x3", "x4", "x5"))

# 전체 데이터 중 x1만을 뽑기
dmatrix("x1 + 0", data=df)

# 전체 데이터 중 x1, x2, x3를 뽑기
dmatrix("x1 + x2 + x3 + 0", data=df)

# 1로 구성된 상수항을 넣지 않기
dmatrix("x1 + x2 + x3", data=df)
dmatrix("x1 + x2 + x3 - 1", data=df)

# 수학 변환
dmatrix("x1 + np.log(np.abs(x2))", df)

# 상호작용(interaction)
dmatrix("x1 + x2 + x1:x2 + 0", df)
dmatrix("x1 * x2 + 0", df)

# 상호작용을 제외한 경우에는연산과정을 명시
dmatrix("x1 + x2 + I(x1 + x2) + 0", df)
```

**스케일링(scaling)** 조건수의 영향을 줄이기 위해 평균을 0으로 표준편차를 1으로 만드는 작업

- 함수 `center()`평균을 0으로 스케일링
- 함수 `standardize()` / 함수 `scale()` 평균을 0으로하고 표준편차를 1로 스케일링

```python
dm = dmatrix("center(x1) + 0", df)

# 평균값 저장
dm.design_info.factor_infos
```

