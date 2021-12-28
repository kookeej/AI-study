🧠AI 공부 레포지토리📁
===

***
# Concepts
### [Machine Learning](#Machine-Learning)
> * [Ensemble](#Ensemble)
> * [LGBM](#LGBM)

### [Deep Learning](#Deep-Learning)
> * [Backbone Network](#Backbone-Network)

***

# 🦾Machine Learning
## Ensemble
reference
> http://www.dinnopartners.com/__trashed-4/    
> https://velog.io/@guns/%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-%EC%8A%A4%ED%84%B0%EB%94%94-%EC%95%99%EC%83%81%EB%B8%94-Ensemble-Voting

* `앙상블`이란, 여러 개의 모델을 활용하여 더 나은 결과를 도출해 내는 것
* 강력한 하나의 모델을 사용하는 대신, 보다 약한 모델 여러 개를 조합하여 더 정확한 예측에 도움을 주는 방식
* 집단 지성을 이용하여 문제를 해결

### 앙상블 학습 유형
#### 1. Voting
* 여러 개의 분류기가 투표를 통해 최종 예측 결과 결정
* 서로 다른 알고리즘을 여러 개 결합하여 사용
* Voting 방식으로는 `하드보팅`과 `소프트보팅`이 있음
  * **하드 보팅**: 다수의 분류기가 예측한 결과값을 최종 결과로 선정
  * **소프트 보팅**: 모든 분류기가 예측한 레이블 값의 결정 확률 평균을 구한 뒤 가장 확률이 높은 레이블 값을 최종 결과로 선정

![image](https://user-images.githubusercontent.com/74829786/147535022-17e50d91-c8de-4fb0-9090-6e4e9ef49859.png)

#### 2. Bagging
* 데이터 샘플링을 통해 모델을 학습시키고, 그 결과를 집계하는 방식
* 모두 같은 유형의 알고리즘 기반의 분류기 사용
* 데이터 분할 시 중복 허용
* `Categorical Data`: 다수결 투표 방식으로 결과 집계
* `Continuous Data`: 평균값 집계
* 오버피팅 방지에 효과적
* ex) Random Forest    
![](http://www.dinnopartners.com/wp-content/uploads/2020/01/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7-2020-01-31-09.26.43.png)

#### 3. Boosting
* 여러 개의 분류기가 순차적으로 학습 수행
* 이전 분류기가 **예측이 틀린 데이터에 대해 올바르게 예측할 수 있도록** 다음 분류기에 가중치를 부여하면서 학습과 예측 진행
* 예측 성능이 뛰어남
* 속도가 느리고 오버피팅 발생할 가능성 존재
* ex) XGBoost, LightGBM

## LGBM
reference
> https://greatjoy.tistory.com/72
* `LGBM`은 `Light GBM`의 준말로 트리 기반의 학습 알고리즘인 `gradient boosting` 방식의 프레임 워크이다.
* 트리를 수평으로 확장하는 다른 알고리즘에 반해, `LGBM`은 수직으로 확장한다.
  * 기존 알고리즘은 수평으로 확장하여 포화 트리를 만듦.
* `leaf-wise tree growth`
  * `leaf-wise`알고리즘은 다른 `level-wise`알고리즘보다 낮은 loss를 달성하는 경향이 있다.
  * 데이터의 크기가 작은 경우 `leaf-wise`는 오버피팅되기 쉬우므로 `max_depth`를 줄여야 한다.
    * 오버피팅에 민감하기 때문에 데이터의 크기가 작을 경우, 기존의 머신러닝 알고리즘이 더 좋을 수 있다.
    * 데이터의 개수가 1만개 이상일 때 추천 

### LGBM의 장점
* 속도가 빠르다.
* 메모리를 적게 차지한다.
* 결과의 정확도가 높다.
* GPU를 활용할 수 있다.


## 
***

# 🧠Deep Learning
## Backbone Network
reference
> https://blog.naver.com/keeping816/221681396990    
> https://velog.io/@garam/Fine-tuning-vs-Transfer-learning-vs-Backbone
* `Backbone`은 "등뼈"라는 뜻인데, 뇌와 몸의 각 부위에 신경을 이어주는 역할을 한다.
* 여러가지 `task`가 몸의 각 부분이라고 생각하면 `ResNet`과 같은 `classification model`은 입력을 받아서 각 task에 맞는 모듈로 전달해주는 역할이다.
*  `classification`용으로 만든 모델(ResNet 등)을 Fully-connected layer 부분을 바꿔 다른 용도인 Detection, Segmentation, Pose Estimation 등으로 사용하는 것을 말한다.
*  입력을 받아 backbone network model을 이용하여 `feature extraction`을 진행한 뒤, 용도에 맞는 모듈로 전달해 처리한다.

![](https://postfiles.pstatic.net/MjAxOTEwMThfODUg/MDAxNTcxMzY3NDU3MzAw.sHLUrsWhN1l7zJbaEAYDRa-6fkr6o3LYtrscL--xeRMg.TJauNv_nzB9iYmirESBxPPZmROu9HALk2NvoeqYVIy8g.PNG.keeping816/SE-e127b3c5-7c89-40c8-aedc-a8031a829cfa.png?type=w966)

