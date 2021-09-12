# 0_데이터 분석 프로세스

[TOC]

![img](https://media.vlpt.us/images/kimdukbae/post/4454910d-bd33-4312-ab67-cf4fcd59c76f/image.png)

<br>

## 1. 문제 정의 단계

분석 분야를 이해하고 해결해야 할 문제를 구체적으로 정의하는 단계

- 분석의 대상, 분석의 목적
- 정의된 문제를 해결하기 위한 구체적인 계획 수립

<br>

## 2. 데이터 수집 단계

분석에 필요한 데이터를 확보하는 단계

Open datasets

- 국내 : [AI hub](http://www.aihub.or.kr/) , [공공 데이터 포털](http://www.data.go.kr/)
- 국외 : [UCI Repository](https://archive.ics.uci.edu/ml/index.php) , [MNIST](http://yann.lecun.com/exdb/mnist/)
- 기타 : [Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist) , [Open Images Dataset](https://opensource.google/projects/open-images-dataset) , [Kaggle](https://www.kaggle.com/)

<br>

## 3. 데이터 탐색 및 전처리 단계

데이터의 특성을 파악하고 여러 관계를 찾는 단계

- [데이터 전처리](./데이터전처리): 노이즈 제거 , 중복값 제거 , 결측값 보정 , 데이터 연계/통합 , 데이터 구조 변경(차원 변경)

- [데이터 탐색](./데이터탐색): EDA(Exploratory Data Analysis), 상관 관계 , 분포 확인 , 인과 관계

<br>

## 4. 데이터 모델링 단계

원하는 결과를 도출하기 위해서 모델 적합을 진행하는 단계

<br>

## 5. 시각화 및 해석 단계

문제에 대한 해결 방안을 모색하는 단계

- 시각화: 이해하기 쉬운 이미지로 데이터 안에 숨겨진 유의미한 인사이트를 발견
- 기술 통계: 수집한 데이터를 요약, 묘사, 설명하는 통계 기법

<br>

![img](http://scimonitors.com/wp-content/uploads/2019/04/%EC%82%AC%EC%A7%841%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9D%B4%EC%96%B8%EC%8A%A4-%EC%A0%88%EC%B0%A8.png)





![img](https://research.aimultiple.com/wp-content/uploads/2018/02/ds_stack_tools.png)

------

https://m.blog.naver.com/yoonok415/221794664696

데이타 분석
먼저 머신러닝에 사용할 전체 데이타셋을 분석한다. 그래프도 그려보고 각 변수간의 연관 관계나 분포도를 분석하여, 학습에 사용할 변수를 정의하고 어떤 모델을 사용할지 판단한다.

모델 정의 
분석된 데이타를 기반으로 모델을 정의하고, 일부 데이타를 샘플링하여 모델을 돌려보고 유효한 모델인지를 체크한다. 모델이 유효하지 않다면 변수와 모델을 바꿔 가면서 최적의 모델을 찾는다.

데이타 추출 및 전처리
유효한 모델이 개발이 되면, 일부 데이타가 아니라 전체 데이타를 가지고 학습을 한다. 전체 데이타를 추출해서 모델에 넣어서 학습을 하려면 데이타의 크기가 크면 매번 매뉴얼로 하기가 어렵기 때문에 데이타 추출 및 전처리 부분을 자동화 한다.  

전체 데이타를 이용한 반복 학습 및 튜닝
모델 자체가 유효하다고 하더라도 전체 데이타를 가지고 학습 및 검증을 한것이 아니기 때문에 의외의 데이타가 나오거나 전처리에 의해서 필터링되지 않은 데이타가 있을 수 있기 때문에 지속적으로 데이타 추출 및 전처리 모듈을 수정해야 하고, 마찬가지로 모델 역시 정확도를 높이기 위해서 지속적으로 튜닝을 한다. 이 과정에서 전체 데이타를 다루기 때문에 모델 역시 성능을 위해서 분산형 구조로 개선되어야 한다. 

모델 배포
학습 모델이 완성되었으면 학습된 모델을 가지고 예측을 할 수 있는 시스템을 개발하고 이를 배포한다. 

파이프라인 연결 및 자동화
머신러닝의 모델은 위의 과정을 통해서 만들었지만, 데이타가 앞으로도 지속적으로 들어올 것이고 지속적인 개선이 필요하기 때문에 이 전과정을 자동화 한다. 이때 중요한것은 데이타 전처리, 학습, 튜닝, 배포등의 각 과정을 물 흐르듯이 연결하고 자동화를 해야 하는데 이렇게 데이타를 흐르는 길을 데이타 플로우라고 한다. (흔히 Luigi, Rundeck, Airflow와 같은 데이타플로우 오케스트레이션 툴을 이용한다) 

<br>

## 데이터 특징

Data size

- ~건, 용량(GB...)
- ~ of instances(row)
- ~ of attributes(column)
  -> 데이터를 표현할 때에는 위 처럼 표현해야 한다. (ex) 몇 건이 있나 , 몇 GB가 있나 , 몇 개의 행과 열로 이루어져 있나

Data schema(meta info.)

- 데이터베이스의 구조(뼈대)와 제약조건에 관해 전반적인 명세를 기술한 것
- 개체의 특성을 나타내는 속성(Attribute) + 속성들의 집합으로 이루어진 개체(Entity) + 개체들 사이의 관계(Relation) + 지켜야할 제약조건(Constraint) = Data schema
- 쉽게 설명하여, DB내 어떤 구조로 데이터가 어떻게 저장되는가를 나타내는 DB의 구조를 스키마라 한다.

Data types

![img](https://media.vlpt.us/images/kimdukbae/post/0abcdc96-6e67-47f2-ad1e-284a5d06f463/image.png)

**Categorical**

- 관측 결과가 몇 개의 범주 또는 항목의 형태로 나타나는 자료형
- 빈도수
- Mode : 빈도수가 가장 높은 Categorical data types

**Numerical**

- 관측된 값이 수치로 측정되는 자료형
- 평균, 중앙값, 표준편차(std), 최대/최소, 사분위수

[여기](https://leedakyeong.tistory.com/entry/수치형-자료numerical-data와-범주형-자료categorical-data)

<br>

## 데이터 종류

정형 데이터 (Structured data)

데이터베이스의 사전에 정의된 규칙에 맞게 들어간 데이터 중에 수치 만으로 의미 파악이 쉬운 데이터를 의미한다.

- 데이터 스키마 지원 (비정형 데이터는 없다.)
- 스키마 구조를 통해 탐색 가능 -> 스키마 정보를 관리하는 DBMS를 통해 탐색
- (ex) RDBMS의 Tables , 스프레드 시트

비정형 데이터 (Unstructed data)

비정형 데이터는 정형 데이터와 반대되는 단어이다. 비정형 데이터는 형태가 없고, 연산이 불가능한 데이터를 의미한다. 정해진 규칙이 없기 때문에 데이터의 의미를 쉽게 파악하기 힘들다.

- Data set이 아닌 하나의 데이터가 객체화 되어있다.
- 구조화 X -> 이해하기 힘듬
- 이진 파일 형태 데이터이면 종류별로 응용SW를 이용하여 탐색
- script 파일 형태 데이터이면 데이터를 parsing하여 처리
- (ex) 동영상(이진) , 이미지(이진) , 음성 , SNS 데이터의 text(script) , 시계열 데이터

반정형 데이터 (Semi-structed data)

반정형 데이터의 반은 Semi를 의미한다. 즉 완전한 정형이 아닌 약한 정형 데이터이다. 데이터베이스는 아니지만 스키마를 가지고 있는 형태이고, 연산이 불가능한 데이터이다.

- 스키마에 해당하는 메타 데이터가 데이터 내부에 존재
- 데이터 내부에 있는 규칙성을 파악하여 parsing 규칙 적용
- (ex) HTML, XML, JSON, 웹로그, IoT 센서 데이터

![img](https://media.vlpt.us/images/kimdukbae/post/6d69f6f3-79fc-4a2a-85a5-8f28baefc6d3/image.png)

일반적으로 데이터베이스는 데이터를 저장하는 장소와 스키마가 분리되어 있어 테이블을 생성, 데이터를 저장하게 된다. 하지만 반정형 데이터는 위 그림처럼 한 txt파일에 column과 value를 모두 출력하게 된다.



[참고자료](https://velog.io/@kimdukbae/%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%84%EC%B2%98%EB%A6%AC-%EC%9D%B4%EB%A1%A0-%EB%B0%8F-%EC%8B%A4%EC%8A%B51)