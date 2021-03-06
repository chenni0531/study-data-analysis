# TIL-DATA

> 데이터 분석 정리 노트

<br>

```
study: 개념 공부 및 정리
practice: 실습
docs: 문서 및 폴더 관리
```

<br>

## 00_데이터분석

[📖 데이터 분석 프로세스](./00_데이터분석)

| No.  | Section                                       | Practice | Check |
| ---- | --------------------------------------------- | -------- | ----- |
| 1    | 문제 정의                                     |          | ✔     |
| 2    | 데이터 준비/수집                              |          | ✔     |
| 3    | [데이터 전처리](./00_데이터분석/데이터전처리) |          |       |
| 4    | [데이터 탐색](./00_데이터분석/데이터탐색)     |          |       |
| 5    | 모델 생성                                     |          |       |
| 6    | 학습/예측                                     |          |       |
| 7    | 평가                                          |          |       |

<br>

## 01_통계분석

| No.  | Section                                      | Practice | Check |
| ---- | -------------------------------------------- | -------- | ----- |
| 1    | [기초 통계](./01_통계분석/기초통계)          |          | ✔     |
| 2    | [상관 분석](./01_통계분석/상관분석)          |          | ✔     |
| 3    | [검정](./01_통계분석/검정)                   |          | ✔     |
| 4    | [최적 모델 선택](./01_통계분석/최적모델선택) |          |       |

<br>

## 02_머신러닝

[📖 머신러닝](./02_머신러닝)

| No.  | Section1                                                     | Section2                                                     | Practice                                                     | Check |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ----- |
| 1    | [**지도 학습 - 분류**](./02_머신러닝/지도학습/분류)          | 0️⃣ [모델 성능 평가](./02_머신러닝/지도학습/분류/모델성능평가) | -                                                            | ✔     |
|      |                                                              | 1️⃣ [의사결정나무](./02_머신러닝/지도학습/분류/분류알고리즘/의사결정나무) | [[Python] iris 데이터 분류](./02_머신러닝/지도학습/분류/분류알고리즘/의사결정나무/의사결정나무_Python.ipynb)<br>[[R] iris 데이터 분류](./02_머신러닝/지도학습/분류/분류알고리즘/의사결정나무/의사결정나무_R.ipynb) | ✔     |
|      |                                                              | 2️⃣ [나이브베이즈](./02_머신러닝/지도학습/분류/분류알고리즘/나이브베이즈) | [[Python] 아마존 리뷰의 긍정 부정 분류](./02_머신러닝/지도학습/분류/분류알고리즘/나이브베이즈/나이브베이즈_Python.ipynb) | ✔     |
|      |                                                              | 3️⃣ [로지스틱회귀](./02_머신러닝/지도학습/분류/분류알고리즘/로지스틱회귀) | [[Python] 가계 대출 여부 분류](./02_머신러닝/지도학습/분류/분류알고리즘/로지스틱회귀/로지스틱회귀_Python.ipynb) | ✔     |
|      |                                                              | 4️⃣ [KNN](./02_머신러닝/지도학습/분류/분류알고리즘/KNN)        | [[Python] 분류 - 유방암 분류](./02_머신러닝/지도학습/분류/분류알고리즘/KNN/KNN_classification_Python.ipynb)<br>[[Python] 회귀 - IMDb 영화 평점 예측](./02_머신러닝/지도학습/분류/분류알고리즘/KNN/KNN_regression_Python.ipynb) | ✔     |
|      |                                                              | 5️⃣ [SVM](./02_머신러닝/지도학습/분류/분류알고리즘/서포트벡터머신) | [[Python] 분류 - iris 데이터 분류 ](./02_머신러닝/지도학습/분류/분류알고리즘/서포트벡터머신/서포트벡터머신_Python.ipynb) | ✔     |
|      |                                                              | 6️⃣ [신경망](./02_머신러닝/지도학습/분류/분류알고리즘/신경망)  |                                                              | ➖     |
| 2    | **[지도 학습 - 회귀](./02_머신러닝/지도학습/회귀)**          | 0️⃣ [모델 성능 평가](./02_머신러닝/지도학습/회귀/모델성능평가) | [[Python] 모델 성능 평가](./02_머신러닝/지도학습/회귀/모델성능평가/모델성능평가_Python.ipynb)<br>[[R] 모델 성능 평가](./02_머신러닝/지도학습/회귀/모델성능평가/모델성능평가_R.ipynb) | ✔     |
|      |                                                              | 1️⃣ [선형회귀](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀)<br>회귀진단, 질적설명변수, 과적합, 변수변환, 상호작용 등 | [[Python] 아파트 경매 가격 예측](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/선형회귀_Python.ipynb) | ✔     |
|      |                                                              | 2️⃣ [단순선형회귀](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/단순선형회귀) | [[Python] 단순선형회귀](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/단순선형회귀/단순선형회귀_Python.ipynb)<br>[[R] 단순선형회귀](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/단순선형회귀/단순선형회귀_R.ipynb) | ✔     |
|      |                                                              | 3️⃣ [다중선형회귀](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/다중선형회귀) | [[Python] 다중선형회귀](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/다중선형회귀/다중선형회귀_Python.ipynb)<br>[[R] 다중선형회귀](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/다중선형회귀/다중선형회귀_R.ipynb) | ✔     |
|      |                                                              | 3️⃣ [다중선형회귀 - Regularization](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/Regularization)<br>Ridge, Lasso | [[Python] Boston 주택 가격 예측](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/Regularization/Regularization_Python.ipynb) | ✔     |
|      |                                                              | 4️⃣ [다중선형회귀 - Feature Extraction](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/Feature-Extraction)<br>PCA, PLS | [[Python] 습관과 체형 데이터 PCA 차원축소](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/Feature-Extraction/FeatureExtractionPCA_Python.ipynb) | ✔     |
|      |                                                              | 5️⃣ [다중선형회귀 - Feature Selection](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/Feature-Selection) | [[Python] Toyota Corolla 모델의 가격 예측 변수선택](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/Feature-Selection/FeatureSelection_Python.ipynb) | ✔     |
|      |                                                              | 5️⃣ [다중선형회귀 - GAM](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/다중선형회귀/GAM) |                                                              |       |
|      |                                                              | 5️⃣ [다중선형회귀 - GLM](./02_머신러닝/지도학습/회귀/회귀분석/선형회귀/다중선형회귀/GLM) |                                                              |       |
|      |                                                              | 6️⃣ [비선형회귀](./02_머신러닝/지도학습/회귀/회귀분석/비선형회귀) |                                                              | ➖     |
| 3    | **[비지도 학습 - 연관규칙분석](./02_머신러닝/비지도학습/연관규칙분석)** | 1️⃣ [연관규칙분석](./02_머신러닝/비지도학습/연관규칙분석)      | [[Python] 식료품 연관 규칙 분석](./02_머신러닝/비지도학습/연관규칙분석/연관규칙분석_Python.ipynb)<br>[[R] 식료품 연관 규칙 분석](./02_머신러닝/비지도학습/연관규칙분석/연관규칙분석_R.ipynb) | ✔     |
|      | **[비지도 학습 - 클러스터링](./02_머신러닝/비지도학습/클러스터링)** | 1️⃣ [K-평균 군집화](./02_머신러닝/비지도학습/클러스터링/K-평균군집화) | [[Python] 슈퍼마켓 고객 군집화](./02_머신러닝/비지도학습/클러스터링/K-평균군집화/K-평균군집화_Python.ipynb) | ✔     |
|      |                                                              | [2️⃣ 계층적 군집화](./02_머신러닝/비지도학습/클러스터링/계층적군집화) |                                                              |       |
|      |                                                              | [3️⃣ DBSCAN](./02_머신러닝/비지도학습/클러스터링/DBSCAN)       |                                                              |       |

<br>

## 03_딥러닝

| No.  | Section | Practice | Check |
| ---- | ------- | -------- | ----- |

<br>

## 04_시계열

[📖 시계열 예측 분석](./04_시계열)

[[Python] 서울시 자전거 수요 분석](./04_시계열/시계열분석_Python.ipynb)

| No.  | Section1                                                     | Section2                                                     | Practice                                                     | Check |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ----- |
| 1    | **[시계열 데이터](./04_시계열/시계열데이터)**                | 1️⃣ [정상성](./04_시계열/시계열데이터/정상성)                  | [[Python] 서울 자전거 수요 데이터의 정상성 확인 및 변환](./04_시계열/시계열데이터/정상성/정상성변환_Python.ipynb)<br>[[R] 비행기 승객수 데이터의 정상성 확인 및 변환](./04_시계열/시계열데이터/정상성/정상성변환_R.ipynb) | ✔     |
|      |                                                              | 2️⃣ [진단](./04_시계열/시계열데이터/진단)                      | [[Python] White Noise와 Random Walk 구현](./04_시계열/시계열데이터/시계열데이터_Python.ipynb) | ✔     |
| 2    | **[시계열 분석 - 시계열분해법](./04_시계열/시계열분석/시계열분해법)** | -                                                            | -                                                            | ✔     |
| 3    | **[시계열 분석 - 평활법](./04_시계열/시계열분석/평활법)**    | 1️⃣ [이동평균법](./04_시계열/시계열분석/평활법/이동평균법)     | -                                                            | ✔     |
|      |                                                              | 2️⃣ [지수평활법](./04_시계열/시계열분석/평활법/지수평활법)     | -                                                            | ✔     |
| 4    | **[시계열 분석 - BOX JENKINS방법](./04_시계열/시계열분석/BOX-JENKINS방법)** | 1️⃣ [AR모형](./04_시계열/시계열분석/BOX-JENKINS방법/AR모형)    | -                                                            | ✔     |
|      |                                                              | 2️⃣ [MA모형](./04_시계열/시계열분석/BOX-JENKINS방법/MA모형)    | -                                                            | ✔     |
|      |                                                              | 2️⃣ [ARMA모형](./04_시계열/시계열분석/BOX-JENKINS방법/ARMA모형) | -                                                            | ✔     |
| 5    | **[시계열 분석 - 변동성추정](./04_시계열/시계열분석/변동성추정)** | 1️⃣ [ARCH모형](./04_시계열/시계열분석/평활법)                  | -                                                            | ✔     |
|      |                                                              | 2️⃣ [GARCH모형](./04_시계열/시계열분석/평활법)                 | -                                                            | ✔     |

