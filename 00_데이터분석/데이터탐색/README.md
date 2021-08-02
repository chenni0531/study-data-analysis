# 테이터탐색

> 데이터를 이해하는 단계

[TOC]

[💻 데이터탐색 with R](./데이터탐색_R)

<br>

## 탐색적 데이터 분석 (EDA)

> Exploratory Data Analysis: process of gaining relevant knowledge about a complex system

![img](https://www.insilicogen.com/blog/attach/1/1385257713.jpg)

- 데이터를 분석하기 전에 그래프나 통계적인 방법으로 자료를 직관적으로 바라보는 과정

- 데이터를 탐색하여 데이터의 특징과 구조로부터 얻은 정보를 바탕으로 통계 모형을 만드는 분석 방법
- 연구의 초기 혹은 데이터 정제(Clean Data) 이후 단계에 수행

```
- 가설 수립과 적절한 모델 및 기법의 선정 지원
- 데이터의 분포 및 값을 관찰하며 전체적인 양상과 현상 이해 (변수 간 트렌드, 패턴, 관계 등)
- 데이터 준비 단계에서 파악하지 못한 잠재적인 문제 발견
- 문제 정의 단계에서 발견하지 못한 다양한 패턴 발견
```

<br>

**도표(plot), 그래프(graph), 요약 통계(summary statistics)등을 사용**

1. 분석의 목적과 변수 확인
2. 데이터를 전체적으로 살펴보기
   - 데이터에 문제가 없는지 확인
   - head나 tail부분을 확인
   - 추가적으로 다양한 탐색(이상치, 결측치 등)
3. 데이터의 개별 속성값을 관찰
   - 각 속성 값이 예측한 범위와 분포를 갖는지 확인
   - 만약 그렇지 않다면, 이유가 무엇인지를 확인
4. 속성 간의 관계에서 패턴을 발견 (상관관계, 시각화 등)

| 데이터 분류                            | 종류            | 내용                                                         |
| -------------------------------------- | --------------- | ------------------------------------------------------------ |
| **Categorical Variable (Qualitative)** | Nominal Data    | 숫자로 표시할 수 없으나 숫자화한 데이터 (순위의 개념 없음) ex) 남자-0, 여자-1 |
|                                        | Ordinal Data    | 숫자로 표시할 수 없으나 숫자화한 데이터 (순위의 개념이 있음) ex) 소득분위 10분위 > 9 분위 > 8 분위 |
| **Numeric Variable (Quantitative)**    | Continuous Data | 셀 수 있는 연속량 데이터 ex) 키 - 166.1cm                    |
|                                        | Discrete Data   | 셀 수 있는 비연속량 데이터 ex) 자식 수 5명                   |

| 데이터 조합               | 요약 통계          | 시각화                                                       |
| ------------------------- | ------------------ | ------------------------------------------------------------ |
| Categorical               | 빈도표             | 막대그래프, 파이차트                                         |
| Numeric                   | 기초 통계량        | 이산형 : bar<br>연속형 : q-q plot, 확률밀도그래프, 히스토그램, 박스 플롯 |
| Categorical - Categorical | 교차 테이블        | 모자이크 플롯                                                |
| Numeric - Categorical     | 카테고리별 통계 값 | 박스 플롯                                                    |
| Numeric - Numeric         | 상관계수           | 산점도                                                       |

<small>[참고자료](https://eda-ai-lab.tistory.com/13)</small>

<br>

---

<br>

## 기술 통계

**수치적인 요약 (기술통계)**

평균(Mean), 중앙값(Median), 최빈값(Mode), 표준편차(Standard Deviation), 분산(Variance), 사분위수범위(Interquartile Range), 첨도(Kurtosis), 왜도(Skewness)

<br>

---

<br>

## 데이터 시각화

> Data visualization = process of telling what you learned and what you want to communicate

**그래프에 의한 요약 (Graphical methods)**

Histogram, Density estimation, Quantile-quantile plot, Box plots, Scatter plots

- 데이터를 한 눈에 이해할 수 있도록 도표나 차트 등으로 정리하는 것

- 설득과 사실 확인 목적
- 분석 결과를 커뮤니케이션 하기 위해 마지막 단계인 의사결정 전 단계(Decision making)에 수행

![img](https://miro.medium.com/max/875/1*qtWoRMUSYfwKh87CLLAWCg.png)

```
Exploratory Data Analysis

- Main Point
	- Data Analysis
  	- Inlier/Outlier
  	- Feature Engineering
    	- Feature Selection
    	- Dimension Reduction
    	- Feature Generation
    	
- Libraries
  	- Visualization
    	- matplotlib
    	- bokeh:
    	- seaborn (as sns)
      		- heatmap: variable/feature 간의 correlation matrix
      		- pointplot, boxplot, lmplot(=scatterplot)
     	- plotly
     		- dots, lines, bars, pie, ...
```

| Statistics          | R function                       |
| ------------------- | -------------------------------- |
| Mean                | `mean()`                         |
| Median              | `median()`                       |
| Mode                | `sort(x, decreasting = TRUE)[1]` |
| Standard Deviation  | `sd()`                           |
| Variance            | `var()`                          |
| Correlation         | `cor(), cov()`                   |
| Quantiles           | `quantile()`                     |
| Range               | `range()`                        |
| Interquartile range | `IQR()`                          |
| 첨도(Kurtosis)      | `e1071::kurtosis()`              |
| 왜도(Skewness)      | `e1071::skewness()`              |
| Frequencies         | `table(), addmargins(table())`   |
| Group summary       | `aggregate()`                    |

<small>[참고자료](http://bigdata.dongguk.ac.kr/lectures/EDA/_book/section-14.html)</small>

