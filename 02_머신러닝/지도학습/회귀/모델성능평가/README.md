# 회귀 모델 성능 평가

> 실제 값과 회귀 예측 값의 차이를 기반으로 평가

[TOC]

- **오차 (Error)**: 모집단을 대상으로 회귀분석으로 예측을 수행했을 때 실제 값과 예측 값의 차이
- **잔차 (Residual)**: 모집단에서 추출한 표본 집단을 대상으로 회귀분석 후 표본집단의 값과 예측 값의 차이

<br>

## 1. MAE

> Mean Absolute Error

실제 값과 예측 값의 차이를 절대값으로 변환해 평균한 것

- 아웃라이어에 Robust하다: 아웃라이어에 대한 저항도 가지고 있고 데이터 특성도 잘 나타낸다
- 절대값이므로 underperformance인지, overperformance인지 알 수 없다

<br>

## 2. MSE

> Mean Squared Error

실제 값과 예측 값의 차이를 제곱해 평균한 것

- 아웃라이어에  민감하다

<br>

## 3. RMSE

> Root Mean Squared Error

MSE는 오류의 제곱을 구하므로 실제 오류 평균보다 커지는 특성

MSE에 루트를 씌운 값

<br>

## 4. RMSLE

> Root Mean Squared Log Error

RMSE에 로그를 적용한 값

- 아웃라이어에 Robust하다: 아웃라이어가 있어도 변동폭이 크지 않다
- 상대적 Error 측정
- Under Estimation에 큰 패널티: 예측값이 실제값보다 작을 때 패널티

<br>

## 5. R Square

> Coefficient of Determination, 결정계수

예측한 모델이 얼마나 실제 데이터를 설명하는지

- scale에 관계 없는 상대적 성능

- 분산 기반으로 예측 성능 평가

- 1에 가까울수록 높은 예측 정확도