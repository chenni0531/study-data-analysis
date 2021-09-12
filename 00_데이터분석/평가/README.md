# 평가

[TOC]

https://brunch.co.kr/@mnc/9

## 1. 분류

손실 함수



### 1-1. 혼동 행렬

> Confusion Matrix

### 1-1. Accuracy 정확도

전체 예측에서 옳은 예측의 비율 (모델이 얼마나 정확하게 분류를 하는지)

### 1-2. Precision 정밀도 

Positive로 분류된 경우 중 실제 Positive의 비율

### 1-3. Recall 재현율

> Sensity, TP Rate, Hit Rage

실제 Positive 중 Postivie로 분류된 비율 (모델이 얼마나 정확하게 Positive 값을 찾는지)

### 1-4. Specificity

Negative로 분류된 경우 중 실제 Negative의 비율

### 1-5. FP Rate

> False Alarm Rate

실제 Negative 중 Postivie로 잘못 분류된 비율

### 1-6. F1 score

불균형한 데이터의 경우 Recall과 Precision의 조화 평균인 F1 score를 사용 



### 1-7. Kappa

두 평가자의 평가가 얼마나 일치하는지 평가하는 값 (0~1)



## 2. ROC 커브

> Receiver Operating Characteristics

가로축을 FP Rate(1-Specificity), 세로축을 TP Rate (Recall)로 하여 시각화한 그래프

임계값을 변경하면서 혼동행렬을 구하고 FPR, TPR을 계산해 그림으로 표현한 것

<br>

ROC AUC

> ROC Area Under Curve

ROC 그래프의 면적, 최대값은 1

<br>

## 2. 예측

- **편차 (bias)**: 관측치가 평균으로부터 떨어져있는 정도, 평균과의 차이

- **오차 (Error)**: 모집단에서 얻은 회귀식으로 예측을 수행했을 때 실제 값과 예측 값의 차이

- **잔차 (Residual)**: 모집단에서 추출한 표본 집단에서 얻은 회귀식으로 예측을 수행했을 때 실제 값 (표본집단의 값)과 예측 값의 차이

  ▶ 추정된 값이 설명할 수 없어서 아직 남아있는 편차

손실 함수

### 1-1. MAE

> Mean Absolute Error: 평균 절대 오차

실제 값과 예측 값의 차이를 절대값으로 변환해 평균한 것

### 1-2. MSE

> Mean Squared Error: 평균 제곱 오차

실제 값과 예측 값의 차이를 제곱해 평균한 것

### 1-3. RMSE

> Root Mean Squared Error: 평균 제곱근 오차

MSE에 루트를 씌운 값

### 4. RMSLE

> Root Mean Squared Log Error

RMSE에 로그를 적용한 값

### 1-5. RSE

> Residual Standard Error: 잔차표준오차 

 실제 값이 추정한 회귀선으로부터 얼마나 벗어날지에 대한 평균값

## R Square (R2)

> Coefficient of Determination, 결정계수

예측한 모델이 얼마나 실제 데이터를 설명하는지

- 모델의 적합성 (goodness of fit) 판단 기준

https://hoon427.tistory.com/53



## 3. 오버피팅 언더피팅



## 4. 교차 검증

> Cross Validation

훈련 데이터와 테스트 데이터를 분리하여 모델을 만드는 방법 중 가장 자주 사용하는 기법으로, 데이터를 다수의 조각으로 나누어 훈련과 테스트를 반복하는 기법

<br>

### 3-1. 과적합

> Overfitting

주어진 데이터로부터 보장되는 것 이상으로 모델을 만들 때 발생, 즉 학습 데이터를 과하게 학습하는 것

학습 데이터에 대해서는 오차가 감소하지만 실제 데이터에 대해서는 오차가 증가할 수 있다

<br>

### 3-2. 테스트 데이터

> Test Data 

데이터가 새로운 데이터에 얼마나 잘 동작할 것인지를 판단하는 방법

```
1. 데이터를 훈련 데이터와 테스트 데이터로 분리한다
2. 훈련 데이터로부터 모델을 만든다
3. 만들어진 모델을 테스트 데이터에 적용해 성능 평가한다
4. 전체 데이터로부터 모델을 만들고 최종 모델로 결정한다
```

<br>

### 3-3. 교차 검증

> K-fold Cross Validation

데이터를 훈련 데이터와 검증 데이터로 나누어 모델링 및 평가하는 작업을 K회 반복하는 것

```
1. 데이터를 10등분 하여 D1, D2, ..., D10으로 분할한다
2. K값을 1로 초기화한다
3. Dk를 검증 데이터, 그 외의 데이터를 훈련 데이터로 하여 모델을 생성한다
4. 검증 데이터 DK를 사용하여 모델의 성능을 평가한다 (평가된 성능은 Pk)
5. K <= 9이면 K += 1을 하고 3단계로 이동, K == 10이면 종료
```

교차 검증 후 테스트: 검증 데이터를 반복 사용한다는 문제 -> 테스트 데이터 단계 추가

```
1. 데이터를 훈련 데이터와 테스트 데이터로 분리한다
2. 훈련 데이터에 대해 K 교차 검증을 수행하여 어떤 모델링 기법이 가장 우수한지를 결정한다
3. 해당 모델링 기법으로 훈련 데이터 전체를 사용해 최종 모델을 만든다
4. 테슽 데이터에 최종 모델을 적용해 성능을 평가한다
```

