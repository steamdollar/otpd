# SSR (Server side rendering)

#
# 1. Concept
SSR은 일반적으로 client측 SPA를 서버에서 렌더링한 후 완전히 헨더링된 페이지를
클라이언트로 전송하는데 널리 사용되는 기술이다. 이 후, client 번들이 이를 이어받아
SPA가 정상적으로 작동할 수 있다.


#
# 2. Pros
1. Improved SEO (search engine optimization)
일부 검색 엔진은 js를 완전히 처리하지 못하는데, 서버 렌더링된 어플리케이션은
검색 엔진이 사이트의 컨텐츠를 전부 탐색할 수 있게 한다.

2. Faster time-to-content
사이트를 보여주기 전 client side에서 JS가 전부 다운로드 되고, 실행되는 것을 기다리는 대신 사용자는 사이트의 server-rendered version을 거의 즉시 볼 수 있다.

#
# 3. Cons
1. 개발의 어려움
SSR은 개발과 아키텍쳐를 복잡하게 만들 수 있다. window, document등 특정 client side code는 서버 사이드에서 작동하지 않을 수 있다.

2. Server costs
server의 작업양이 많아진다.

#
# 4. ref
- https://www.toptal.com/front-end/client-side-vs-server-side-pre-rendering
- https://legacy.reactjs.org/blog/2020/12/21/data-fetching-with-react-server-components.html
- https://velog.io/@sj_dev_js/Next.js-%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B1%B0%EC%9D%98-%EB%AA%A8%EB%93%A0-%EA%B2%83