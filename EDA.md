# Event-Deiven Architecture (EDA)


#
# 1. Keywords
- event
- publisher
- subscriber
- event bus
- event-driven programming
- event streaming
- real-time processing


#
# 2. Overview
EDA, 이벤트 중심 아키텍쳐는 상태의 중요한 변화인 이벤트의 생성, 감지, 소비 및 이에 대한 대응을 촉진하는 소프트웨어 아키텍쳐 패턴이다.


#
# 3. Key Concepts
1. Event : 상태의 변화 (e.g. 사용자가 버튼을 클릭한 것도 이벤트로 간주될 수 있음)

2. Event Creators : 이벤트를 생성하는 개체. 작업을 수행하는 사용자 or 데이터를 생성하는 IoT 일 수도 있음

3. Evt Consumers : evt를 수신, 처리하는 개체

4. evt channels : evt 생성자에서 소비자에게 이벤트를 전달하는 채널


#
# 4. Use cases
1. 실시간 데이터 처리 : EDA를 사용하면 실시간 데이터를 통해 evt를 트리거해 즉시 처리할 수 있다.

2. Microservice acrhitecture : 각 마이크로 서비스가 evt를 방출하고, evt를 listen할 수 있어, 상호간의 강한 커플링 없이도 협업할 수 있다.

3. IoT systems : IoT 시스템에서 센서는 계속해서 데이터를 생성하고, evt로 처리된다.


#
# 5. Pros
1. Loose coupling : 컴포넌트들이 이벤트를 통해 상호작용하므로, 특정 컴포넌트 수정시 다른 컴포넌트에 영향을 주지 않음.

2. 확장성 : 이미 존재하는 evt consumer에 영향을 주지 않고 새로운 evt consumer를 추가할 수 있음

3. 실시간 처리 : EDA는 실시간 이벤트를 처리하도록 설계되었기 때문에 빠른 응답이 필요한 사용 사례에 적합


#
# 6. Cons
1. debugging complexity : 이벤트가 여러 소스에서 비동기적으로 오므로 디버깅이 어려워질 수 있음

2. evt-chain complexity : 긴 체인의 이벤트 처리를 관리하는게 복잡하다.

#
# 7. ref
1. https://aws.amazon.com/ko/event-driven-architecture/
2. https://www.ibm.com/topics/event-driven-architecture