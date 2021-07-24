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

- 데이터 전처리: 노이즈 제거 , 중복값 제거 , 결측값 보정 , 데이터 연계/통합 , 데이터 구조 변경(차원 변경)

- 데이터 탐색: EDA(Exploratory Data Analysis), 상관 관계 , 분포 확인 , 인과 관계

<br>

## 4. 데이터 모델링 단계

원하는 결과를 도출하기 위해서 모델 적합을 진행하는 단계

<br>

## 5. 시각화 및 해석 단계

문제에 대한 해결 방안을 모색하는 단계

- 시각화: 이해하기 쉬운 이미지로 데이터 안에 숨겨진 유의미한 인사이트를 발견
- 기술 통계: 수집한 데이터를 요약, 묘사, 설명하는 통계 기법

<br>

------

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