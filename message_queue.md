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
