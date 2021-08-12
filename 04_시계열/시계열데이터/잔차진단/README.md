# 잔차진단



백색 잡음



ACF, PACF

동일한 변수를 시점을 달리하여 관측했을 때 시점에 따라 데이터 사이의 상호 연관관계가 나타나는지





# 정상성 검정

> 



## ADF 검정

>  Augmented Dickey Fuller Test

H0: 데이터에 단위근이 존재한다 vs H1: 시계열 데이터가 정상성을 만족한다

- 검정 통계량 ADF Statistics가 Critical Value보다 작으면 정상성 시계열 데이터

- P-value가 신뢰수준 값보다 작으면 정상적 시계열 데이터 

- ARIMA 모형의 적분 차수 판단에 사용된다