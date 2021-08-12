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

Stationarity는 ADF test(Augmented Dickey-Fuller test)를 통해서 검정할 수 있습니다. ADF Test 검증 모형은 아래와 같습니다.



![img](https://blog.kakaocdn.net/dn/cmB3bp/btqPZIW8nkx/G7w0qnxG3OsPoGONcxkhi1/img.png)https://en.wikipedia.org/wiki/Augmented_Dickey%E2%80%93Fuller_test



 해당 Test의 귀무가설(H0H0)과 대립가설(H1H1)은 다음과 같습니다.

귀무가설(H0H0): 데이터는 비정상성이다.[단위근이 존재한다.](Non-stationary)

대립가설(H1H1): 데이터는 정상성을 만족한다.[단위근이 존재하지 않는다.](Stationary)



![img](https://blog.kakaocdn.net/dn/bDcmfQ/btqP9rs5BuC/ahhU4EOVj520bjOWYAv6N1/img.gif)



만약 δδ가 1이라면 이는 Unit root를 가지게 되는 것이고, 시간이 지남에 따라 시계열 데이터는 분산이 무한대로 커지게 됩니다. 따라서 위에 정리한 ADF test 검증모형에서 γγ는 0이 되면 시계열 데이터가 비정상성을 가진다고 볼 수 있습니다.

Python에서 statsmodels 패키지를 활용하여 쉽게 ADF Test를 수행할 수 있습니다.

```
import statsmodels.tsa.stattools as sts 

sts.adfuller(df["Close"])
'''
(1.059624647407287,
 0.9948568682915807,
 6,
 6774,
 {'1%': -3.43131571888621,
  '5%': -2.8619667679228646,
  '10%': -2.5669971648470256},
 55484.34577265247)
 '''

sts.adfuller(df["wn"])
'''
(-82.61985810790189,
 0.0,
 0,
 6780,
 {'1%': -3.4313148639438347,
  '5%': -2.861966390170326,
  '10%': -2.5669969637620627},
 105778.09936636973)
 '''
```

위의 결과에서 2번째 줄이 P-value를 나타내며, 일반적으로 P-value가 0.05미만일 때 해당 데이터는 정상성을 가진다고 볼 수 있습니다. White noise같은 경우는 정상성을 가지고 있으며, S&P500 index의 경우에는 비정상성을 띄고 있습니다.