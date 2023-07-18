# Machine Learning Operations (MLOps)


#
# 1. Keywords
- MLOps
- CI/CD
- automated machine learning (AutoML)
- Model Versioning
- Model Monitoring


#
# 2. Overview
MLOps는 머신 러닝 분야의 DevOps라고 볼 수 있다. 머신 러닝과 데이터 엔지니어링, DevOps의 업무를 수행한다.
MLOps의 목표는 모델 개발 및 학습부터 프로덕션 환경에서의 배포, 관리에 이르기까지의 머신 러닝 수명 주기를 간소화, 표준화 하는 것이다.


#
# 3. Key Concepts
1. CI/CD for ML
ML code를 계속해서 코드베이스에 통합하고, 테스트하고 업데이트하는 것을 의미

2. Automated Machine Learning (AutoML)
데이터 전처리, 기능 선택, 모델 선택, 하이퍼파라미터(**&&) 튜닝 등 머신러닝을 적용하는 프로세스를 자동화

* Hyper Parameter
하이퍼 파라미터는 학습 프로세스 자체를 지배하는 구성 변수이다. 메타 데이터 비슷한 거인듯.
학습 데이터로부터 오는게 아니라 학습 전에 어떻게 학습을 할지를 config 하는 것.
학습 속도, 서포트 벡터 머신의 C, sigma, 의사 결정 트리의 depth등을 설정할 수 있다.
모델에 대한 최적 하이퍼 파라미터는 특정 데이터 셋, 작업에 따라 달라질 수 있고, test, tune이 필요할 때가 많음.

3. Model Versioning
재현성, 책임성(문제 발생의 원인)을 위해 다양한 버전의 ML model과, 연관된 데이터, param을 추적한다.

4. Model Monitoring
프로덕션 환경에서 ML model의 성능을 추적하고, 필요한 경우 재학습 하는 작업


#
# 4. Use case
1. ML model Production
MLOps는 model의 배포를 간소화, 수명 주기 관리에 도움이 될 수 있다.

2. ML Workflow 자동화
MLOps가 있다면 데이터 전처리, 하이퍼 파라미터 튜닝등의 여러 ML process가 자동화될 수 있다.

#
# 5. Pros
1. 효율
ML model의 개발, 배포, 관리 프로세스를 자동화

2. 재현성
model, 데이터의 버전을 관리함으로써 결과를 재현, 업데이트를 롤백하기가 쉬워진다.

3. 책임성 (accountability)
MLOps는 모델 버전을 추적하고 성능을 모니터링하여 모델 책임성을 강화합니다.
