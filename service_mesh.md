# Service mesh

#
# 1. Keywords
- Service mesh
- Service Discovery
- Traffic management
- Fault Injection
- Security


#
# 2. Overview
서비스 간 통신을 처리하기 위한 전용 인프라 계층.
모던, 클라우드 네이티브 appl을 구성하는 복잡한 서비스 토폴로지를 통해 요청을 안정적으로 전송한다.
마이크로 서비스들간의 상호작용의 관리가 어려워서 나온 아키텍쳐.
기존에는 서비스들이 서로를 직접 호출하는 방식이었다면 Service mesh에서는 Service와 함께 돌아가는 proxy가 다른 서비스의 proxy를 호출하는 방식

* Topology (망구성방식)
컴퓨터 네트워크의 요소들 (link, node)를 물리적으로 연결해 놓은 것 or 그 연결 방식 (e.g. LAN)


#
# 3. Key Concept
1. Service Discovery : 서비스들이 서로를 발견하도록 해주고, 로드 밸런싱을 관리

2. Traffic management : 동적 라우트 config를 사용하면 서비스 간 트래픽 및 api 호출의 흐름을 제어할 수 있다.

3. Fault Injection : 오류와 지연을 주입해 appl의 복원력을 test 가능
   
4. Security : 내장된 ID 및 Credential 관리를 통해 서비스 전반의 안전한 통신을 관리할 수 있다.


#
# 4. use cases
1. MicroServices Architecture
다수의 마이크로 서비스를 운용할때 서비스 메시는 매우 유용하다.
service discovery, failure handling, load balacning, location transparency 등을 전부 지원하기 때문.

2. Cloud native Applications
cloud native 생태계에서는 servie mesh를 사용해 네트워킹의 복잡성을 추상화하므로 개발자는 비지니스 로직에 집중할 수 있다.


#
# 5. Pros
1. 회복력 (resilience) : 네트워크 장애, 서비스 retry, 타임아웃을 처리해 시스템을 안정적으로 만들 수 있음.

2. 관측성 (Observability) : 서비스 통신이 appl 성능에 미치는 영향에 대한 정보를 얻을 수 있다.

3. 보안 (security) : 개별 서비스가 각각 보안을 갖추는 대신 네트워크 레벨에서 보안 정책을 강화할 수 있다.

#
# 6. ref
- https://www.redhat.com/en/topics/microservices/what-is-a-service-mesh
- https://velog.io/@beryl/Istio-%EC%86%8C%EA%B0%9C