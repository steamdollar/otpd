# Container Orchestration with Kubernetes

#
# 1. keywords
- containers
- Orchestration
- Kubernetes
- Pods
- Nodes
- Clusters
- Services
- ConfigMaps
- Deployments

#
# 2. Intro
K8s로도 종종 불리는 쿠버네티스는 컨테이너화된 어플리케이션의 배포, 확장, 관리를 자동화해줄 수 있는 오픈 소스 컨테이너 오케스트레이션 툴이다.
(구글이 처음 디자인헀고, 지금은 다른 재단에서 관리되고 있음)
현재 컨테이너 오케스트레이션(대응하는 한글 없는 듯)의 사실상 표준이며 다양한 production 환경에서 사용되고 있다.

#
# 3. Key Concepts
1. Orchestration
복잡한 시스템과 서비스에 대한 자동화된 configuration과 coordination

2. Pods
쿠버네티스에서 `pods`는 쿠버네티스 객체 모델에서 가장 작고 단순한 단위이다. `pod`는클러스터에서 돌아가는 프로세스의 하나의 인스턴스이며, 하나 이상의 컨테이너를 포함한다.

3. nodes
node는 쿠버네티스의 worker machine이다. 클러스터에 따라 가상 or 물리적 머신이 될 수 있고, 각 노트는 `master`가 관리한다.

4. Clusters
쿠버네티스 클러스터는 `node`라 불리는 여러 개의  worker machine으로 구성되어 있다. 클러스터는 worker node들을 컨트롤하는 master node를 포함한다.

5. Services
쿠버네티스 서비스는 `pod`의 집합과 `pod`에 대한 access policy을 정의하는 abstraction이다. (가끔 마이크로 서비스라고도 불림)

6. ConfigMaps & Secrets
Configmaps는 이미지 컨텐츠에서 config artifact를 디커플해 컨테이너화된 어플리케이션을 portable하게 유지해준다.

Secret도 비슷하지만 민감한 정보에 대해 더 강력 서큐리티를 제공함.

7. Deployments
`Deployment`는 `pod`와 `ReplicaSets`에 대한 선언전 업데이트를 제공한다. 사용자가 `deployment`에서 원하는 state를 설명함녀 deployment controller가 실제 상태를 변경함.

#
# 4. Use Cases
- 여러 host에 걸쳐 컨테이너화된 어플리케이션들을 관리할 때
- 필요에 따라 어플리케이션의 스케일 조정 (키우기, 줄이기 모두)
- 어플리케이션의 버전을 교체할 때 (다운 그레이드, 업그레이드 모두)
- 로드 밸런싱, 어플리케이션의 트래픽 분산

#
# 5. Pros and Cons
확장성, 로드 밸런싱, 버전 관리, 보안 등의 향상,
하지만 config가 복잡하고 러닝 커브가 크다. 작은 어플엔 필요 없음.

6. ref
- official : https://kubernetes.io/docs/home/
- https://kubernetes.io/docs/tutorials/kubernetes-basics/

7. comment
다음부터는 유스케이스에 좀 더 구체적인 예시를 제시해달라고 피드백 함.
한국어 레퍼런스는 제외해달라고 함. 대부분 링크가 죽었음. 직접 벨로그 같은데서 찾자.