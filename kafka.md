# Apache Kafka
분산 이벤트 스트리밍 플랫폼
> 이를 개발한 링크드인은 카프카를 적용함으로써 모든 이벤트, 데이터 흐름을 중앙에서 관리할 수 있게 되었고 이로 인해 서비스 아키텍쳐가 훨씬 단순해짐.

#
# 1. intro
실시간 데이터 파이프라인과 스트리밍 어플리케이션을 위해 디자인 되었다. 수평적 확장이 편하고, 처리량이 높고, 이벤트 or 레코드 스트림을 처리하도록 디자인되었다.

#
# 2. Key Concept
1. Producers and Consumers
> Producer가 evt/msg를 생성하고 consumer가 읽을 수 있다.

2. Topics
> evt는 topic에 조직되고 저장된다. Topic은 카테고리나 피드 등으로 간주할 수 있음.

3. Partitions
> 각 토픽은 파티션으로 쪼개질 수 있고, 데이터가 여러 브로커, consumer에 걸쳐 분산될 수 있도록 한다. (Key of Kafka's scalability)

4. Brokers
> Kafka Cluster는 하나 이상의 서버 (Kafka broker)로 구성되어 있으며 record를 토픽에 저장한다.

5. ZooKeeper
> ZooKeeper를 사용해 클러스터의 메타 데이터, leader election, config 관리 등 중요한 조정 작업을 관리한다.

6. Offsets
> 파티션 내의 각 레코드에는 `offset`이라는 고유 식별자가 있으며, 이는 파티션 내에서 레코드의 위치를 나타낸다.

7. Kafka Streams
> 어플리케이션과 마이크로서비스를 구축하기 위한 client lib로, 입력 및 출력 데이터가 Kafka 클러스터에 저장됩니다.

8. Kafka Connect
> Kafka와 다른 데이터 시스템 (msg queue, db 등)과의 (확장력, 신뢰성이 있는) 데이터 스트리밍을 위한 tool

#
# 3. Use cases
1. Evt Sourcing
- appl의 상태의 변경을 이벤트 로그로 캡쳐

2. Log Aggregation
- 서버의 물리적 로그 파일을 수집, central place에 넣어 처리

3. Stream Processing
- 스트리밍 데이터의 실시간 분석, 모니터링, 처리

4. Data Integration
- 실시간으로 서로 다른 데이터 소스들과 appl 통합

5. Msg Queue

- 성능좋은 메시지 큐로 사용할 수 있음

#
# 4. Pros ans Cons

##
## 1. Pros
- 높은 처리량, 짧은 지연 시간
- 파티셔닝을 통한 확장성
- log 압축을 통한 durable storage
- 스트림 처리 능력
- 커뮤니티가 크다

##
## 2. Cons
- config, tuning이 복잡
- ZooKeeper를 관리해야 함.
- 간단한 메시징에 사용하기엔 너무 크다.

#
# 5. ref
https://kafka.apache.org/downloads
https://kafka.apache.org/quickstart

https://velog.io/@jaehyeong/Apache-Kafka%EC%95%84%ED%8C%8C%EC%B9%98-%EC%B9%B4%ED%94%84%EC%B9%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80