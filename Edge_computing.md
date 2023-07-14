# Edge Computing

#
# 1. KeyWords
- Edge Computing
- Latency Reduction
- Bandwidth Efficiency
- Real time processing

#
# 2. Overview
엣지 컴퓨팅은 계산과 데이터 저장을 필요한 위치에 가깝게 배치해 응답 시간을 줄이고 bandwidth를 정략할 수 있는 분산 컴퓨팅 패러다임이다.
클라우드에서 실행되는 프로세스를 줄이고, 해당 프로세스를 사용자의 PC, IoT 장치, 엣지 서버 등의 로컬 위치로 이동시켜 client와 server 사이에 필요한 장거리 통신의 양이 감소한다.

#
# 3. Key Concept
1. Latency Reduction
소스와 가까운 곳에서 데이터를 처리함으로써, 중앙 서버나 클라우드로 데이터를 전송, 처리할 때 발생할 수 있는 지연 시간을 줄여준다.

2. Bandwidth efficiency
클라우드에 처리를 위해 대량의 데이터를 전송하면 상당한 대역폭이 소모된다. 엣지 컴퓨팅은 데이터를 로컬에서 처리해 지속적인 고대역폭 연결의 필요성을 줄인다.

3. 실시간 처리
의료 모니터링, 자율 주행등 실시간 처리가 필요한 상황에서 신속한 대응을 제공할 수 있음.

#
# 4. Use cases
1. IoT (internet of things) : IoT 디바이스는 소스 근처에서 더 효율적으로 처리할 수 있는 대량의 데이터를 생성하므로 클라우드와의 지속적인 상호작용을 줄일 수 있음.
   
2. CDNs (Content Delivery Networks) : 사용자와 가까운 서버에 미디어 컨텐츠의 사본을 저장, 전송하므로 속도가 빨라지고 ux 향상

#
# 5. Pros
1. Speed : 데이터가 네트워크를 거쳐 데이터 센터, 클라우드까지 가지 않아도 되므로 빠른 데이터 처리와 응답이 가능하다.

2. Reliability : 네트워크 연결 상태가 appl의 성능에 미치는 영향을 줄일 수 있다.

3. Security : 데이터가 로컬에서 처리되고 저장되므로 잠재적인 보안 위협에 대한 노출을 줄일 수 있다.

#
# 6. Ref
1. https://www.geeksforgeeks.org/edge-computing/
2. https://www.cloudflare.com/ko-kr/learning/serverless/glossary/what-is-edge-computing/