# Caching And CDN

#
# 1. Keywords
- content delivery network (CDN)
- caching
- Cloudfront
- Akamai
- Fastly

#
# 2. Overview
CDN(컨텐츠 전송 네트워크)은 사용자의 지리적 위치, 웹 페이지의 출처,
콘턴츠 전송 서버에 따라 사용자에게 콘텐츠를 전송하는 서버의 분산 네트워크이다.
지연을 줄이고, 컨텐츠 전송 속도를 늘리고, 보안을 강화하는데 사용된다.

Caching은 CDN의 중요한 요소이다. 캐시된 컨텐츠는 동적, 정적 컨텐츠 모두를 포함하며, 사용자와 가까운 edge server에 저장되어 자주 요청하는 컨텐츠에 빠르게 엑세스할 수 있다. 이로 인해 원본 서버의 부하와 최종 사용자가 경험하는 지연 시간이 크게 줄어든다.

#
# 3. Pros
1. Performance
CDN은 웹 사이트의 로딩 시간을 줄일 수 있고, ux를 향상시킬 수 있다.

2. Reliability
지리적으로 컨텐츠가 여러 곳에 걸쳐 분산되어 있다면 한 지점의 실패로 인한 영향이 최소화된다. 만약 하나의 서버가 다운되더라도 다른 서버가 컨텐츠 제공을 계속할 수 있다.

3. Scalability
CDNs 트래픽 급증을 효과적으로 처리할 수 있어 사이트를 쉽게 확장할 수 있다.

4. Security
DDos 공격에 대한 보호 계층을 제공하며, 사이트 보안을 강화하기 위해 SSL/TLS offloading(**&&)을 제공하는 경우가 많다.

#
# 4. use case
1. Video streaming Platform
글로벌하게 퍼져있는 사용자들을 대상으로한 스트리밍 서비스에서 cdn은 중요한 역할을 한다. (netflix도 이를 사용)

2. E-commerce Websites
사용자 ux 를 위한 빠르고 믿을만한 컨텐츠 제공이 필요하다.

#
# 5. ref
- https://www.cloudflare.com/ko-kr/learning/cdn/what-is-a-cdn/
- https://www.imperva.com/learn/performance/what-is-cdn-how-it-works/
- https://velog.io/@yunjin5450/WebSocket-socket.io