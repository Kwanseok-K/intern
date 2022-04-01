## R-AI Modeler

### 배경

- 데이터 및 AI 지식이 없는 사람도 데이터 분석을 수행할 수 있는 툴을 제작하고자 함.

- 여러 종류의 머신러닝 모델, AI가 만든 AI 모델, 유명 논문의 모델을 손쉽게 사용해 데이터 분석을 할 수 있게 함.

### Data

- 사용 가능 데이터: 현재, Table data에 대한 분석만 가능하도록 만들어졌으며, 추후 다양한 데이터에 대해 적용이 가능하도록 업데이트 할 예정

  			- 데이터는 크게 회귀를 위한 것과 분류를 위한 것으로 나뉨. 

  			- 분류 과제에서는 scikit-learn의 iris data를 활용한 예시 제시

  <img src="/img/irisdata.png" alt="image" style="zoom:50%;" />

     - 회귀 과제에서는 scikit-learn의 boston data를 활용한 예시 제시

  <img src="/img/boston.png" alt="image" style="zoom:50%;" />

### Preprocessing

- 분류 혹은 회귀 과제 판별

  - 우리가 맞추고자 하는 Target의 개수가 전체 데이터 개수의 1/10 미만인 경우 분류, 1/10 이상인 경우 회귀로 판별.

- 전처리

  - 자동으로 전처리 진행 후 데이터 크기, 전처리에 사용한 방법을 보여줌

    <img src="/img/preprocess.png" alt="image" style="zoom: 50%;" />

    <img src="/img/datasize.png" alt="image" style="zoom:50%;" />

### Model Training

- Pycaret

  - Pycaret을 활용해 여러 머신러닝 모델들을 학습시켜 가장 성능이 좋은 모델 제시

  <img src="/img/pycaret.png" alt="image" style="zoom:50%;" />

- Autokeras

  - Autokreas를 이용해 신경망 기반의 모델 학습
  - AI가 모델 구조를 직접 결정하여 모델을 구성해 학습을 진행하는 "AI가 만든 AI 모델" 활용 가능

  <img src="/img/akmodelsummary.png" alt="image" style="zoom: 33%;" />

  <img src="/img/autokeras.png" alt="image" style="zoom: 33%;" />

- TabNet

  - Table 데이터 분석에 좋은 성능을 보이는 것으로 알려진 TabNet 모델 학습

  <figure>
    <img src="/img/tabnet.png" alt="image" style="zoom:50%">
    <figcaption align="center" size=6>TabNet: Attentive Interpretable Tabular Learning, Secan O. Arik, Tomas Pfister, 2020 Dec
    </figcaption>
  </figure>

### Model Interpretation

- Pycaret

  - Decision Tree 모델을 기반으로 각 변수별 중요도를 산출

  <img src="/img/pycaret2.png" alt="image" style="zoom:50%;" />

- Autokeras

  - Explainable AI, 설명 가능한 AI를 활용하기 위해 LIME을 활용해 변수별 중요도 산출

  <img src="/img/lime.png" alt="image" style="zoom: 50%;" />

- TabNet

  - TabNet 모델 구조를 활용한 변수 중요도 산출

  <img src="/img/tabnet2.png" alt="image" style="zoom: 33%;" />

  - 해당 변수 중요도를 통해 현재 진행하는 분석 과제 중 예측하고자 하는 변수 설명에 가장 중요한 변수를 찾아 모델을 이해하고, 해석 결과를 의사결정에 활용할 수 있음.

### 기능 추가 및 개선

- Jupyter Notebook에 작성한 코드를 웹서비스로 배포하는 최적의 방안을 찾고 이를 구현

- Table 데이터를 활용한 분류 및 회귀 뿐만 아니라 다른 데이터를 받아 분석을 진행할 수 있으며 다른 종류의 과제 또한 진행할 수 있도록 기능 추가
- 예시
  - 이미지 데이터
    - 예시 : 이미지 데이터를 받아 분류할 수 있는 모델
  - 자연어 데이터
    - 예시 : 특정 주제의 글을 입력 받아 해당 글의 주제를 출력하는 모델
  - 클러스터링
    - 예시 : 특정 데이터를 입력받아 비슷한 것들끼리 묶어주는 모델

- 사용자가 입력한 데이터를 통해 생성한 모델을 저장 및 새로운 데이터에 대해 활용할 수 있도록 제시

- 사용자가 입력한 데이터에 대한 다양한 시각화 제시

