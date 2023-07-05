# WebSockets

#
# 1. Keywords
- full-duplex
- Real-time
- Communication Protocol
- Websocket API
- TCP
- Connection upgrade

#
# 2. intro
웹소켓은 단일 TCP 연결을 통해 full-duplex(전이중) 통신 채널을 제공하는 통신 프로토콜입니다. 채팅 애플리케이션, 온라인 게임, 실시간 금융 데이터 추적 등 실시간 데이터 교환이 필수적인 웹 애플리케이션에 사용된다.

* 전이중 통신(full-duplex) : 두 대의 단말기가 data를 송 수신하기 위해 동시에
  각각 독립된 회성을 사용하는 통신 방식

#
# 3. How it works
기존 http 통신은 client가 req를 보내면 server가 res를 보내는 방식으로 이루어진다.
이는 실시간 통신이 필요한 경우 비효율적이며, 이를 위해 ws가 도입되었다.

1. Establishing Connections
client가 http req를 보낸다. (이 과정을 ws handshake req라고 부름)
서버는 이 req를 승인하고 ws 연결이 설정된다.

2. Data Transfer
연결이 설정되면 client, server 간 data를 주고받을 수 있다. 이 통신은 전송할 때마다 새로운 http 연결이 아니라 하나의 영구적 연결을 통해 이루어진다.

3. Closing Connection
client와 server는 언제든 ws 연결을 닫을 수 있다.

#
# 4. benefits
1. Reduced Latency
하나의 오픈된 연결을 사용하므로 http req에 비교해 지연이 크게 적다.

2. Efficiency
헤더에 대한 바이트 단위의 오버헤드가 적어 HTTP 폴링에 비해 더 적은 대역폭이 사용된다.

3. Real-Time
실시간으로 데이터를 주고 받을 수 있다.

#
# 5. Glossary
1. overhead
http 통신의 각 req, res에는 header가 포함된다.
이런 header에는 콘텐츠 유형, 크기, 쿠키 및 기타 메타데이터 등의 정보가 포함된다.
이 정보는 http가 제대로 작동하는데 필요하지만 각 req, res에 추가 데이터를 추가하는데, 이를 overhead라고 한다.

2. Polling
http를 사용에 data를 실시간 동기화하려는 경우 polling이라는 기술을 사용할 수 있다.
여기서는 client가 새 data를 확인하기 위해 일정 간격으로 http 요청을 반복 전송한다.
이런 각 요청에는 http header의 overhead가 발생하고, 매번 새로운 연결이 생성되므로 리소스 부하가 크다. (그래서 ws를 쓰는게 낫다.)