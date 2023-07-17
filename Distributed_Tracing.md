# Distributed Tracing (분산 추적)

#
# 1. Keywords
- 분산 추적
- Traces
- span
- Context propagation

#
# 2.Overview
distribute tracing은 (distribute request tracing 이라고도 불림) appl, 특히 마이크로서비스 아키텍쳐를 사용해 구축된 appl을 프로파일링하고 모니터링하는데 사용되는 방법이다. 성능 병목 현상을 식별하고, 복잡한 시스템 문제를 해결하는데 도움이 된다.

#
# 3. Key Concept
1. Traces : 시스템을 통해 이동하는 tx 혹은 요청 이동의 기록

2. Spans : 마이크로서비스에 대한 요청이나 db 쿼리와 같은 추적 내의 개별 작업을 나타낸다.

3. Context propagation : 상위 span에서 하위 span으로, 그리고 서로 다른 서비스 간 context를 전달하는 작업

#
# 4. use cases
1. 성능 최적화 : 분산 추적은 시스템에서 느린 마이크로서비스를 찾을 수 있고, 이를 최적화할 수 있게 해준다.

2. Err detection : 시스템 어딘가에서 에러가 발생한다면, 분산 추적이 에러가 발생한 부분을 찾아낼 수 있음.

3. 의존성 이해 : trace를 시각화함으로써, 시스템 상의 서로 다른 서비스 간의 의존성을 이해하고, 이를 통해 디자인, 아키텍쳐 결정에 도움을 받을 수 있음.

#
# 5. Pros
1. Debugging
문제가 있는 서비스를 정확히 알려줘 디버깅이 편하다.

2. Monitoring
시스템의 성능을 모니터링하고 병목이 일어나는 곳을 확인할 수 있다.

이에 따라 확장성도 개선됨.

#
# 6. ref
1. https://velog.io/@adam2/%EB%A7%88%EC%9D%B4%ED%81%AC%EB%A1%9C%EC%84%9C%EB%B9%84%EC%8A%A4-%EB%B6%84%EC%82%B0-%EC%8B%9C%EC%8A%A4%ED%85%9C-%EC%B6%94%EC%A0%81-c3k3cwuzgv
