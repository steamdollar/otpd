#
# 1. MicroServices Architecture
마이크로서비스 아키텍쳐는 작고 독립적인 서로 네트워크 너머로 의사 소통하는(일반적으로 http/rest, messaging queue) 서비스들의 집합으로 어플리케이션을 설계한다. 각 서비스는 각각의 기능에 대한 책임이 있으며 개별적으로 확장, 배포, 개발이 가능하다.

# 2. Key Concept
1. Decoupling
각 마이크로 서비느는 독립적이다.

2. domain driven design
비지니스 도메인을 중심으로 설계되는 경우가 많으며 각 서비스는 특정 비지니스 기능에 해당한다.

3. Communication
서비스들은 api를 이용해 상호작용하며, 동기, 비동기적 모두 가능하다.
(sync : hrrp/rest, async : messaging queue)

4. DB and Data management
종종 각 마이크로 서비스는 각자의 db를 가지며, 이는 서비스들간의 느슨한 커플링을 보증한다.

5. Centralized Configuration and Service Discovery
마이크로서비스의 configuration은 중앙적으로 이루어지며 서로를 발견, 상호작용할 방법이 필요하다.

# 3. Use case
1. 큰 스케일의 웹 어플리케이션

2. 높은 확장성과 기능이 필요한 어플리케이션

3. 다른 장소나 스택을 사용하는 개발팀들간의 협업

# 4. Pros
- 확장, 배포가 쉽다.
- 개발이 빨라지고 책임 소재가 명확해진다.
- 다양한 기술을 사용할 수 있다.

# 5. Cons
- 서비스 관리가 복잡하다.
- 데이터의 일관성을 유지하기 어렵다.
- 네트워크의 지연, 상호작용이 까다롭다.
- 다수의 서비스에 걸쳐있는 트랜잭션을 처리하기가 힘들다.

#
# 6. Summary
1. Serverless는 server layer를 추상화하고 코드 실행에 이벤트의 응답으로서 집중하는 것이고,

2. MicroService는 어플리케이션을 느슨하게 결합된 서비스들의 집합으로 디자인하는 아키텍쳐 스타일이다.

MicroService로 만들고 각 서비스들을 Serverless로 만드는 등 두 개념을 함께 도입할 수도 있음.