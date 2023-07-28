# Progressive Web Apps (PWA)

#
# 1. Keywords
- Web app Manifest
- Service Workers
- Offline First
- App Shell model
  
#
# 2. Overview
**PWA는 최신 웹 기능을 사용해 사용자에게 app-like 경험을 사용자들에게 제공하는 웹 app이다.** 
일반 페이지처럼 로드할 수 있지만 기존에는 native application에서만 사용할 수 있었던 오프라인 작업, 푸시 알림, 하드웨어 엑세스 등의 추가 기능을 제공한다.

#
# 3. Pros
1. Reliability
2. fast
3. good ux

#
# 4. use case
1. Service workers
background syncing, 푸시 알림, 풍부한 오프라인 경험을 제공한다.

2. Web App manifest
사용자들의 그들의 홈 스크린에 web app을 설치할 수 있게 한다.

3. App Shell Model
모바일 웹 앱의 초기 로딩이 앱 ui의 기본 shell을 제공하고, 콘텐츠는 나중에 채워지는 디자인 개념.
가능한 최소한의 사용자 인터페이스를 로딩하는 것에 중점을 두고 있으며, 이를 캐싱해 다음 방문에서 앱의 모든 컨텐츠가 로딩되기 전에 오프라인에서도 사용이 가능하다.
이렇게 하면 ui는 캐시에서 즉시 로딩, 새로운 컨텐츠는 서버로부터 요청한다.
사용자는 무언가를 즉시 보게됨으로서 ux가 향상된다.

#
# 5. ref
- https://developer.mozilla.org/ko/docs/Web/Progressive_web_apps/Tutorials/js13kGames/App_structure
- https://velog.io/@jduckling_1024/PWA