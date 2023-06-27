# Redis

#
# 1. intro
Redis (Remote dictionary server)는 db, cache, message broker로 사용될 수 있는 오픈소스 in-memory data structure store이다.
메모리에 데이터를 캐싱함으로써 app의 성능과 속도를 끌어올려 db나 외부 서비스를 직접적으로 호출하는 횟수를 줄여준다.

그럼 내가 지금 하는 프론트 > 백 > 블록체인 서버 요청을 보내는 것도

이걸 이용해 속도를 끌어올릴 수 있을까?

#
# 2. Data structures
Redis는 다양한 데이터 구조를 지원한다.

i) string

ii) Lists : collection of ordered string

iii) Sets : An unordered collection of strings

iv) Sorted Sets : Sets과 비슷하지만 각 emember에 score가 있고, 이를 기준으로 정렬

v) hashes : string k-v 쌍의 매핑

vi) Bitmaps & Bitfields : Arrays of bits

vii) HyperLogLogs : set 안의 고유 요소를 추정하기 위한 데이터 구조

viii) Streams : 로그나 시계열 데이터와 유사한 추상화를 제공하는 map과 비슷한 항목의 append-only collection

#
# 3. features
i) In memory Storage : 모든 데이터를 메모리에 저장해 db에 비교해 매우 빠르다.

ii) Persistence : 데이터를 (성능을 크게 희생하지 않고) 디스크에 저장하는 다양한 방식을 제공한다. 일정 주기로 이렇게 저장된 데이터를 전부 지운다던가 하는 방식을 커스터마이징 할 수도 있음

iii) Replication : 여러 서버에 대해 동일한 사본 데이터를 가질 수 있게 해서 읽기 퍼포먼스나 데이터 중복을 제공

iv) Clustering : 다양한 인스턴스에 걸쳐 데이터를 파티셔닝해 수평적인 확장을 가능하게 함.

v) Transactions : transaction을 제공, 여러 개의 명령어를 고립되고 atomic하게 실행할 수 있음.

vi) Lua scripting : 서버에서 실행되는 스크립트를 Lua로 작성해 커스텀 명령이나 복잡한 계산에 사용 가능

@ Lua : 경량 프로그래밍 언어의 하나로, 레디스 서버에서 실행될 스크립트를 작성하는데 사용됨.

vii) Pub/Sub Messaging : Publish/Subscribe 메시징 패턴을 지원해 실시간 메시지 유스 케이스를 허용한다.

#
# 4. use cases
몇 가지 상황에서 redis가 사용되는 예시를 알아보자.

i) caching : 가장 자주사용되는 예시. 자주 접근하는 데이터를 메모리에 저장해 어플리케이션이 cost한 동작을 피하고, 응답 시간을 늘려줄 수 있음

ii) Session Storage : 웹 어플리케이션에서 세션 정보를 저장하는데 사용된다.

iii) LeaderBoards and Counting : Sorted set data 구조를 활용해 리더보드, 실시간 분석을 진행할 수 있다.

iv) Real time analysis : 실시간으로 거대한 양의 데이터를 분석하는데 사용할 수 있다.

v) Message Queue : Pub/Sub 기능을 통해 고성능 메시지 큐를 구축할 수 있다.

#
# 5. Getting Started
download : https://redis.io/download/
tutorial : https://redis.io/docs/

