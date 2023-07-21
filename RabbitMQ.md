# RabbitMQ


#
# 1. Overview
RabbitMQ는 오픈소스 msg broker 소프트웨어로, (msg 지향 미들웨어라고도 함) 원래는
고급 msg 큐 프로토콜(AMQP)을 구현한 것이다.
Erlanf으로 작성되었으며, 높은 처리량, 유연한 구성으로 인해 실시간 시스템을 구현하는데 자주 사용된다.


#
# 2. Key concept
1. Producer/Consumer model
RabbitMQ에서 생산자는 대기열에 메시지를 보내고 소비자는 이를 수신한다. 이렇게 하면 시스템의 각 부분이 분리되어 독립적으로 작동할 수 있다.

2. Exchanges and Queue
메시지는 대기열에 직접 게시되지 않고, producer는 하나 이상의 queue로 이동할 수 있는 exchange에 메시지를 보냅니다. routing은 binding이라는 규칙에 의해 처리됩니다.

3. Durability and Reliability
장애 발생 시, msg가 손상되지 않고 적어도 한 번은 전달되도록 보장하는 기능이 있다.


#
# 3. use cases
여러 서비스가 서로 비동기적으로 통신해야 하는 (각 파트의 분리가 필요한)마이크로서비스 아키텍쳐에서 자주 사용된다. 또, 장기 실행 작업이 작업자에게 offload 되는 작업 대기열 시스템에서도 사용된다.


#
# 4. ref
1. https://www.rabbitmq.com/getstarted.html
2. https://velog.io/@lololtoday/RabbitMQ
3. https://velog.io/@y005/%EB%A9%94%EC%84%B8%EC%A7%80%ED%81%90