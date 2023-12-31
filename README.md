# 시계열 데이터 ARIMA모형에 적용
Kaggle의 'Weather Conditions in World War Two' 데이터셋 이용해서 적용

### Stack
<img src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"> <img src="https://img.shields.io/badge/numpy-00A3E0?style=for-the-badge&logo=numpy&logoColor=white"> <img src="https://img.shields.io/badge/scikitlearn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white">

## 시계열 데이터 분석
- 과거 데이터의 패턴을 분석해서 미래의 값을 예측하는 방법
- 과거의 패턴이 미래에도 지속된다는 데이터의 안정성이 기본적인 가정으로 필요

## 시계열 분해법(추세/순환/계절/불규칙)
- 추세 : 데이터가 장기적으로 증가하거나 감소하는 것
- 순환 : 사회적 요인에 의한 변화로 일정주기가 없으며 장기적인 변화 현상
- 계절 : 주, 월, 분기 단위 등 특정 시간의 주기로 나타나는 패턴
- 불규칙 : 예측 불가능한 임이의 변동

### 덧셈분해와 곱셈분해
- 덧셈분해는 Trend와 Seasonal이 별개
- 곱셈분해는 Trend와 seasonal이 변화

## AR(Autoregression)모형
- 자귀 회귀 모형, 자기상관성을 시계열 모형으로 구성
- 예측하고자 하는 특정 변수의 과거 관측값의 선형 결합으로 해당 변수의 미래값 예측
- 이전 자신의 관측값이 이후 자신의 관측값에 영향을 준다는 아이디어에 기반

## MR(Moving Average)모형
예측 오차를 이용하여 미래를 예측하는 모형

## ARIMA(Autoregressive Integrated Moving Average)모형
- d차 차분한 데이터에 AR모형과 MA모형을 합친 모형
- 시계열 데이터의 정상성을 가정

### 정상성(Stationary)
- 평균, 분산이 시간에 따라 일정한 성질(즉, 데이터의 특성이 시간의 흐름에 따라 변하지 않음)
- 정상성이 나타나지 않는 데이터는 복잡한 패턴 모델링이 어렵기 때문에 정상성을 갖도록 로그변환, 차분 등 전처리 후 분석
- 변동폭이 일정하지 않는 경우 -> 로그변환
- 추세, 계절성이 존재하는 경우 -> 차분(1차 차분으로 안되면 차분 반복)

### ACF(자기상관함수)
- 시차에 따른 일련의 자기상관으로 시차가 커질수록 ACF는 0에 가까워짐
-  정상 시계열은 상대적으로 빠르게 0에 수렴하고, 비정상 시계열은 천천히 감소

### PACF(편자기상관함수)
- 시차에 따른 일련의 편자기상관으로 시차가 다른 두 시계열 데이터 간의 순수한 상호 연관성
