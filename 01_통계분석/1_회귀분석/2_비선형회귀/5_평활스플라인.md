# 4_회귀모형진단

## 6. 모델 진단

### 6-1. 모형의 선형성

- 진단: 잔차 산점도가 선형인지 확인

- 처방: 비선형회귀모형을 설정하거나 변수변환을 하여 선형이 되도록 하기

<br>

### 6-2. 잔차 진단

잔차(residuals): 남아있는 오차, 추정 회귀식이 반응변수 관찰치를 설명하지 못하는 부분

- 잔차 산점도 (Residual Plot)를 그렸을 때 평평한 띠 모양

- 오차항에 대한 가정 검토: 독립성, 정규성, 등분산성

**1. 오차의 등분산성**

- 진단: 잔차 산점도에서 띠 모양이 나오는지 확인

- 처방: 등분산이 되도록 모형을 조정하거나 이분산을 고려한 모형으로 바꾸기

**2. 오차의 정규성**

- 진단: 잔차의 히스토그램, 줄기잎그림을 그려 정규 분포 모양인지 확인
  - Shapiro-Wilk W 통계량
  - `Normal Q-Q plot`
- 처방: 변수변환을 하기

**3. 오차의 독립성**

- 진단: Durbin-watson 통계량

<br>

### 6-3. 이상치

- 입력 실수인지 확인
- 이상치를 그대로 포함할지, 제거한 후 선형 모형을 적용할지 확인

<br>

### 6-4. 영향관찰치

- 입력 실수인지 확인

- 영향력을 판단하기 위해 제거한 후 모형을 추정하고 추정치 값들과 R2가 얼마나 차이나는

<br>

```r
plot(m)
```

`Residuals vs Fitted plot`

- X축 - 선형 회귀로 예측된 Y값, Y축 - 잔차

- 0에서 멀리 떨어진 값: 이상치 가능

![image-20210706175309436](C:/Users/USER/Desktop/chenni0531/Data Analysis/study-TIL/00_통계분석/1_회귀분석/1_선형회귀/1_단순선형회귀.assets/image-20210706175309436.png)

`Normal Q-Q plot`

![image-20210706175328632](C:/Users/USER/Desktop/chenni0531/Data Analysis/study-TIL/00_통계분석/1_회귀분석/1_선형회귀/1_단순선형회귀.assets/image-20210706175328632.png)

`Scale-Location plot`

- X축 - 선형 회귀로 예측된 Y값, Y축 - 표준화 잔차
- 0에서 멀리 떨어진 값: 이상치 가능

![image-20210706175340869](C:/Users/USER/Desktop/chenni0531/Data Analysis/study-TIL/00_통계분석/1_회귀분석/1_선형회귀/1_단순선형회귀.assets/image-20210706175340869.png)

`Residuals vs Leverage plot`

- X축 - 레버리지, Y축 - 표준화 잔차

- 레버리지: 설명변수가 얼마나 극단에 치우쳐 있는지
- 쿡의 거리 (Cook's Distance): 회귀 직선의 모양에 크게 영향을 끼치는 점들을 찾는 방법으로, 레버리지와 잔차에 비례 (우측 상단, 우측 하단)

![image-20210706175223296](C:/Users/USER/Desktop/chenni0531/Data Analysis/study-TIL/00_통계분석/1_회귀분석/1_선형회귀/1_단순선형회귀.assets/image-20210706175223296.png)

<br>

```r
plot(m, which=c(4, 6))
```

`Cook's distance`

![image-20210706235812906](C:/Users/USER/Desktop/chenni0531/Data Analysis/study-TIL/00_통계분석/1_회귀분석/1_선형회귀/1_단순선형회귀.assets/image-20210706235812906.png)

`Cook's dist vs Leverage`

![image-20210706235823326](C:/Users/USER/Desktop/chenni0531/Data Analysis/study-TIL/00_통계분석/1_회귀분석/1_선형회귀/1_단순선형회귀.assets/image-20210706235823326.png)