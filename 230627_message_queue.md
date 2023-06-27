# Message Queue

#
# 1. intro
메시지 큐는 서버리스, 마이크로 서비스 아키텍쳐에 사용되는 비동기적 service-to-service 의사 소통이다.

#
# 2. key concept

1. Producer & consumer
메시지 큐에서 시스템의 한 파트(Producer)가 메시지를 생성하고, 이를 큐에 넣는다. 다른 파트 (Consumer)가 이 메시지를 읽어 처리한다.

2. Messages
메시지는 어떤 종류의 정보는 포함할 수 있다. 예를 Consumer가 처리할 작업이나 필요한 데이터를 전달할 수 있다.

3. Asynchronous Processing
메시지 큐는 비동기 처리를 가능하게 한다. producer는 메시지를 큐에 넣고 consumer가 이를 받아 수행하는 작업이 끝나길 기다리지 않고 계속 작업을 이어할 수 있다.

4. Scalability and Balancing
여러 consumer가 동일 메시지 큐를 읽을 수 있고, load balancing도 가능하다. 그냥 consumer를 추가하면 되므로 확장성이 뛰어나다.

5. Reliability
메시지 큐는 메시지가 길을 잃지 않도록 보장한다. Consumer쪽에 문제가 있더라고 메시지는 큐에 머무르며 다른 consumer의 처리를 기다릴 수 있다.

6. Dead Letter queues
종종 메시지는 여러 이유에 의해 처리되지 못하기도 하는데, 이 경우 메시지는 `Dead Letter Queue`에 들어가면 나중에 처리 실패 원인을 분석한다.

#
# 3. Common msg Queue systems
1. RabbitMQ 
가장 많이 쓰이는 오픈 소스 메시지 큐 소프트웨어로 신뢰성과 확장성이 뛰어나다. multiple messaging protocol을 지원한다.

2. Apache Kafka
실시간 데이터 파이프라인과 스트리밍 애플리케이션을 구축하는 데 사용되는 분산 이벤트 스트리밍 플랫폼. 로그 집계, 스트림 처리, 이벤트 소싱에 자주 사용된다.

3. Amazon SQS
AWS에서 제공하는 관리된 메시지 큐잉 서비스. 이를 이용해 마이크로서비스 분산 시스템, 서버리스 어플리케이션을 디커플/확장할 수 있다.

4. Microsoft Azure Service Bus
완전 관리형 엔터프라이즈 통합 메시지 브로커. Service Bus는 애플리케이션과 서비스를 분리할 수 있다.

#
# 4. Use case
1. Task offloading: 만약 작업이 실행되기에 시간이 너무 오래 걸린다면 메시지 큐를 통해 다른 작업자에게 offload 될 수 있다. 이렇게 하면 메인 어플리케이션이 다른 작업을 계속 수행할 수 있음.

2. Decoupling Service
마이크로 서비스 아키텍쳐에서 메시지 큐는 서비스들을 디커플링하고, 이들 간의 상호작용애 scalable하고 탄력적으로 할 수 있음.

3. Batch Processing
일정 기간 동안 데이터를 모아 실시간이 아닌 병렬로 처리할 수 있음.

4. Application Scaling
큐에 있는 메시지의 수를 어플리케이션 컴포넌트를 확장할지 결정하는 근거로 사용할 수 있음

5. Data streaming and Evt processing
실시간 데이터, 이벤트를 감지, 처리, 분석 가능


#
# 5. etc

서버리스, 마이크로서비스 아키텍쳐, 카프카

## 1. Serverless Architecture
서버리스 아키텍처는 클라우드 공급자가 서버 할당 및 프로비저닝을 동적으로 관리하는 클라우드 컴퓨팅 실행 모델이다. 서버리스 아키텍처에서 개발자는 코드 작성에만 집중할 수 있으며 기본 인프라는 추상화된다.

### 1. key concept
1. Function as a Service (FaaS)
서버리스 아키텍쳐의 핵심 개념. 개별 함수를 작성하고, 이를 이벤트 (e.g. HTTP req, db operatrions)에 대한 응답으로 실행되게끔 함. 예시로는 AWS Lambda, Azure functions, Google Cloud Function등이 있음.

2. Event-Driven
서버리스 함수들은 일반적으로 event-driven이며, 이벤트나 트리거에 대한 응답으로서만 실행된다는 것을 의미한다. 일시적이며 지속적으로 실행되지 않는다.

3. Scaling and Pricing
서버리스 함수는 요청의 숫자와 함께 자동적으로 확장된다. 시간이 아닌 함수의 실행 횟수로 인해 소모된 리소스의 양만큼만 비용을 지불하면 된다.

4. Statelessness
함수는 stateless해, local state에 의존하지 않는다. 매번 다른 서버에서 실행될 수도 있으며, state가 있다면 db나 다른 외부 저장소에 저장되어야 한다.

### 2. Use Cases
- Data processing (e.g. image, video processing)
    **&& how?

- Automation of cloud infrastructure tasks
- Building APIs or microservice
- Handling asynchronous backend tasks

### 3. Pros
- 서버 관리가 필요 없다.
- 가격, 비용 측면에서 유리
- 확장성이 좋다.

### 4. Cons
- cold starts (**&& why?)
    오랜만에 쓰는 함수는 딜레이가 걸림

- 지연이 길어질 수 있음
- 오래 지속되는 함수의 실행에는 제한이 있을 수 있음 (e.g. AWS lambda는 한 함수를 최대 15분 동안 실행할 수 있음)

##
## 2. MicroServices Architecture
마이크로서비스 아키텍쳐는 작고 독립적인 서로 네트워크 너머로 의사 소통하는(일반적으로 http/rest, messaging queue) 서비스들의 집합으로 어플리케이션을 설계한다. 각 서비스는 각각의 기능에 대한 책임이 있으며 개별적으로 확장, 배포, 개발이 가능하다.

### 1. Key Concept
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

### 2. Use case
1. 큰 스케일의 웹 어플리케이션

2. 높은 확장성과 기능이 필요한 어플리케이션

3. 다른 장소나 스택을 사용하는 개발팀들간의 협업

### 3. Pros
- 확장, 배포가 쉽다.
- 개발이 빨라지고 책임 소재가 명확해진다.
- 다양한 기술을 사용할 수 있다.

### 4. Cons
- 서비스 관리가 복잡하다.
- 데이터의 일관성을 유지하기 어렵다.
- 네트워크의 지연, 상호작용이 까다롭다.
- 다수의 서비스에 걸쳐있는 트랜잭션을 처리하기가 힘들다.

##
## 3. Summary
1. Serverless는 server layer를 추상화하고 코드 실행에 이벤트의 응답으로서 집중하는 것이고,

2. MicroService는 어플리케이션을 느슨하게 결합된 서비스들의 집합으로 디자인하는 아키텍쳐 스타일이다.

MicroService로 만들고 각 서비스들을 Serverless로 만드는 등 두 개념을 함께 도입할 수도 있음.

