# RESTful APIs

#
# 1. intro
RESTful API (Representational State Transfer)는 네트워크
어플리케이션을 설계하기 위한 몇 가지 규칙이다. COBRA, RPC, SOAP 등의 복잡한 메커니즘을
사용하는 것보다 간단한 http가 머신간의 호출을 생성하는게 낫다는 생각에서 시작헀다.
웹 개발에서 http, rest 원칙을 사용해 api를 설계한다.

#
# 2. Concept

1. Resource : REST에서 리소스는 유형, 연관 데이터, 다른 리소스와의 관계, 해당 리소스에 걸리는 메서드 집합이 있는 object이다. 리소스는 url로 식별된다.

2. HTTP methods : 보통 get, post, put, delete method가 있다.
- get : retrieving data
- post : sending data
- put : updating dat
- delete : delete data

3. Statelessness : client로부터의 각 요청은 서버가 그 요청을 처리하기 위해 필요한 모든 정보를 가지고 있다. 서버는 개별 요청 간 클라이언트의 상태에 대한 정보를 모른다.

4. Representation : 리소스는 json, xml 등의 다양한 형식/표현을 가질 수 있다.

5. Response Code : 스탠다드 http 응답 코드가 api 요청에 대한 성공, 실패를 알려줄 수 있다. 일반적으로 `200`은 성공, `404`는 not found, `500`은 서버 에러를 의미한다.
   

#
# 3. use case
1. CRUD operations
보통은 CURD 작업을 위해 많이 사용된다. 예를 들어 도서관의 책 정보를 관리하는데 사용되는 restful api의 경우
- `GET /books` : 책 리스트 retrieve
- `POST /books` : add new book
- `PUT /books/:id` : update details of a book
- `DELETE /books/:id` : delete a book

2. integration btw different service : RESTful API는 다른 서비스들간의 의사 소통 수단이다. 핸드폰에서 날씨 정보를 가져온다던가..

3. MicroServices Architecture : 마이크로 서비스 아키텍쳐에서 각 microservice는 restful api를 노출해 다른 microservice나 gateway가 접근할 수 있도록 한다.

4. IoT Device : 다양한 IoT 기기가 RESTful API를 이용해 백엔드와 통신한다.

#
# 4. Best Practices
1. 복수형 명사 사용 : 예를 들어 `/order` 대신 `/orders` 를 사용해 order 리소스를 표현한다. 사용자가 이 url이 어떤 역할을 하는지 추론하는 것도 편하고, 논리적으로도 더 맞다.

2. Stateless Authentification : 인증에 세션 대신 token (jwt 등)을 사용한다.
    - stateless : 세션 기반의 인증은 서버가 state를 일부 포함하게 만듦으로써 stateless 원칙을 어기게 됨.
    - 확장성 : session은 서버에 저장해야 하는데 client가 많아질수록 이를 다 저장하기 힘들어진다.
    - cors : 다른 도메인에서 엑세스하는 api를 관리하려고 할 때 토큰을 전송하는게 cors에 문제가 없다.

3. err handling : 적절한 상태 코드와 함께 도움이 되는 err msg를 제공한다.

4. Versioning : API를 버전에 따라 나누는 것도 좋다. (e.g. `/v1/orders`) 이러면 api가 수정되어도 기존 client에게 문제가 없음

5. rate limiting and throttling : client의 최소 요청 주기를 제한해 api를 abuse로부터 보호한다.

#
# 5. etc
rate limit, throttling : 주어진 시간 동안 client들이 서버에 보낼 수 있는 요청의 수를 조절하는 테크닉. 어뷰징을 막는데 중요한 메커니즘이다. 두 개념은 종종 혼용되기도 하지만 디테일한 측면에서는 다름.

## 1. Rate limiting
사용자가 일정 시간 동안 보낼 수 있는 req의 횟수를 제한

몇 가지 전략을 포함한다.

1. fixed window
총 요청 횟수가 일정 시간 간격으로 capped. 이 횟수를 초과할 경우 다음 window까지 기다려야 한다.

2. Sliding Window Log : 각 요청의 타임스탬프를 로그에 기록, 사용자가 특정 기간 동안 일정 횟수의 요청을 할 수 있도록 함.

3. Token bucket : .사용자는 일정 갯수의 token을 가지고 시작하며, 각 req마다 token을 소모한다. 일정 시간 간격으로 토큰은 다시 받을 수 있으며, 이를 다 소모하면 다시 받을때까지 기다려야 함.

## 2. Thottling
스로틀링은 현재 시스템 퍼포먼스에 기반해 rate limit을 동적으로 조정하는 방식이다. 현재 시스템에 부하가 클 경우 허용된 요청의 수를 자동으로 줄인다.

1. Leaky bucket algorithm
바닥에 구멍이 뚫린 버킷을 생각해보면 된다. 들어오는 요청은 버킷을 채우고, 일정 속도로 구멍을 통해 빠져나간다. 버킷이 넘치면 새로운 요청은 버킷에 충분한 공간이 생길때까지 거부된다.

2. Adaptive throttling
cpu, 메모리 사용량 등 서버 성능 지표 기반으로 rate limit를 실시간 조절한다.

## 3. implementation details
1. Headers : 보통 rate limit는 header에 담겨서 클라이언트에 전달됨.
(e.g. `RateLimit-Limit`, `X-RateLimit-Remaining`, `X-rateLimit-Reset`)

2. Return Codes : 사용자가 rate limit을 초과했을 경우 서버는 `429 - Too many Requests`를 리턴한다.

3. IP address, user account, API key : 이것들을 이용해 rate limit을 적용할 수도 있음


# 연관
http, ws, graphql, 마이크로 서비스