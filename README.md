<div align="center">
<h2>[2023] 서초구 교차로별 5분 누적 교통량 시계열 예측 프로젝트</h2>
창의적인 전처리 기법을 통해 모델의 Loss를 92% 감소시킨(RMSE 12.51 -> 1.01) 시계열 데이터 예측 프로젝트 🚀
</div><br/>

## 개요

- 프로젝트 이름: 서초구 주요 교차로 회전교통량 예측 :blue_car:
- 프로젝트 지속기간: 2023.10-2023.11
- 개발 언어 및 툴: Python & TensorFlow
- 작업 인원: 2명(정지영, 김윤미)<br/><br/>

## 프로젝트 설명

<center><img src="https://github.com/Jiyeong303/Time-Series-Traffic-Volume-Prediction-Project/assets/146100147/d4e0a6b1-faed-49e7-b4f7-e8668f5ac2b0" width="950" height="450"/></center>

이번 프로젝트는 인공지능을 활용하여 서초구 교차로의 실시간 회전교통량을 예측하고, 이 예측값을 교통 신호 제어에 활용하여 교통 체증을 줄이고자 시작하게 되었습니다.

- 기대 효과 :earth_asia:
	- 운전자의 시간적, 비용적 부담 감소
	- 연료 감소를 통한 탄소 배출 감소 및 에너지 효율성 향상<br/><br/>
- 세부 목표 :dart:
	- 분석 가능한 한 달치의 데이터를 최대한 활용하여 예측의 유효성을 입증하고, 이를 통해 추가적인 데이터를 확보하는 것<br/><br/>
- 진행과정 요약 :chart_with_upwards_trend:
	- 교차로별 csv 로드 후, 기본적인 전처리 및 EDA
	- 파생변수 생성(요일, 시, 휴일)
	- **모든 회전교통량 변수를 하나의 변수로 통합**하여 유사한 변수의 수를 줄이고 데이터 수는 182배 증폭시키는 효과를 얻음(**Loss 92% 감소**)
	- window size: 36 (3시간) / target size: 12 (1시간) / LSTM 모델 사용
	- RSME 1.01로 예측이 매우 정확한 수준으로 측정되었으며, 과소예측 및 추종 문제는 발견되지 않음<br/><br/>
- 모델 비교 :eyes:
	- 변수 통합 전 모델: Model A
	- 변수 통합 후 모델: Model B

<div  align="center">

|비교|Model A|Model B|
|:------:|:---:|:---:|
|예측 가능 범위|하나의 교통량|전체 교통량|
|알고리즘|GRU|LSTM|
|파라미터 수|1,114,641|298,124|
|MSE|156.55 (±1206.34)|1.02 (±30.61)|
|RMSE|12.51 (±12.50)|1.01 (±1.01)|
|MAE|5.81 (±11.08)|0.48 (±0.89)|

</div>
