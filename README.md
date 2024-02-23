# 2022-Production_Quality_Prediction / [국방 AI 부문 MINI 경진대회] 공정 프로세스 최종 품질값 예측

일정: 2022.12.24 ~ 2022.12.27

## 대회 설명

![image](https://github.com/aerojohn1223/2022-Production_Quality_Prediction/assets/82106824/666c9c7f-e004-4ff4-9cab-515317d8f60c)

이번 경진대회의 목표는 일정 시간별로 제품이 생산되는 공정에서 생산된 제품이 어떤 측정치를 가질지를 회귀 모델을 통해 예측하는 것이다. 본 프로젝트에서 사용한 데이터셋은 여러대의 기계를 통해 제품을 생산하는 공정에서 각 기계의 각 시간별 상태와 해당 상태에서 생산된 제품의 측정치로 구성되어 있다.

이를 이용하여 임의의 시간에서 임의의 기계 상태가 주어졌을 때 생산된 제품의 측정치는 어떻게 나올 것인지를 예측하는 모델을 총 2개 만들어야 했다.

생산 공정 과정은 아래와 같다.

1.  Machine 1, 2, 3에 해당하는 3개의 기계가 병렬적으로 동작하여 각 기계의 출력물을 Combiner으로 전달

2.  Combiner의 첫 산출물 생산, 15개의 위치에서 산출물의 특정 값이 측정 (무슨 측정값인지는 구체적으로 알려지지는 않았다)

3.  2번에서 측정된 15개의 값이 첫번째 Stage(Stage1)의 출력값

4.  첫번째 Stage를 통과한 산출물이 Machine 4와 Machine 5를 차례로 (즉 직렬적으로) 통과

5.  Machine 5를 통해 생산된 산출물이 최종 산출물이 되며, 앞서 첫번째 Stage와 같이 여기서도 15개의 위치에서 특정 값 측정

6.  5번에서 측정된 15개의 값이 두번째 Stage(Stage2) 의 출력값

이 과정에서 각 기계의 센서 값과 각 Stage의 Output이 시간별로 기록된 것이 전체 데이터셋이 된다. 이를 Stage 1과 Stage2로 나누어 각 Stage의 회귀 모델을 구현하는 것이 이번 경진대회의 목표이다.

각 Stage 별로 모델을 하나씩 구현해서 총 2개의 모델을 구현해야 하며, 두개의 예측 결과값을 따로 제출해야 한다. 채점은 이 둘의 R2 Score를 계산하여 이것의 평균을 통해 이루어진다.

## 대회 결과

최종 3등 (우수상)

![image](https://github.com/aerojohn1223/2022-Production_Quality_Prediction/assets/82106824/72294940-80e2-4ee7-a7ac-59cfe92270b0)

![image](https://github.com/aerojohn1223/2022-Production_Quality_Prediction/assets/82106824/ef7a986e-613c-4675-acff-2f5d347eb2a7)

