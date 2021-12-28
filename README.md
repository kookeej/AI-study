🧠AI 공부 레포지토리📁
===

***
# Concepts
### [Machine Learning](#Machine-Learning)


### [Deep Learning](#Deep-Learning)
> * [Backbone Network](#Backbone-Network)

***
# 🦾Machine Learning

***

# 🧠Deep Learning
## Backbone Network
reference
> https://blog.naver.com/keeping816/221681396990    
> https://velog.io/@garam/Fine-tuning-vs-Transfer-learning-vs-Backbone

### Backbone이란?
* `Backbone`은 "등뼈"라는 뜻인데, 뇌와 몸의 각 부위에 신경을 이어주는 역할을 한다.
* 여러가지 `task`가 몸의 각 부분이라고 생각하면 `ResNet`과 같은 `classification model`은 입력을 받아서 각 task에 맞는 모듈로 전달해주는 역할이다.
*  `classification`용으로 만든 모델(ResNet 등)을 Fully-connected layer 부분을 바꿔 다른 용도인 Detection, Segmentation, Pose Estimation 등으로 사용하는 것을 말한다.
*  입력을 받아 backbone network model을 이용하여 `feature extraction`을 진행한 뒤, 용도에 맞는 모듈로 전달해 처리한다.

![](https://postfiles.pstatic.net/MjAxOTEwMThfODUg/MDAxNTcxMzY3NDU3MzAw.sHLUrsWhN1l7zJbaEAYDRa-6fkr6o3LYtrscL--xeRMg.TJauNv_nzB9iYmirESBxPPZmROu9HALk2NvoeqYVIy8g.PNG.keeping816/SE-e127b3c5-7c89-40c8-aedc-a8031a829cfa.png?type=w966)

