# Nginx

#
# 1. Keywords
- static content
- reverse proxy
- load balancer
- http cache
- media streaming
- event-driven architecture

#
# 2. intro
웹 서버, reverse proxy server로서 개발된 오픈 소스 소프트웨어.
2004년에 처음 나왔는데, 시간이 지나면서 load balancing, http caching, media streaming까지 지원할 수 있도록 발전해왔다.
높은 성능, 안정성, 간단한 configuration, 낮은 리소스 소모량이 장점이라 웹 개발자와 시스템 관리자들에게 자주 사용됨.

#
# 3. Key Concepts and Features
1. Web Server
Nginx는 HTML, CSS, img와 같은 정적 콘텐츠를 serving하는 것을 잘한다. event driven architecture를 통해 최소한의 리소스 사용으로 많은 수의 동시 연결을 처리할 수 있다.

2. Reverse Proxy
client와 서버 사이에 위치해 client req를 서버로 전달한다. nginx 뒤에 있는 서버가 응답하면 nginx는 응답을 클라이언트로 다시 보낸다.
이는 로드 밸런싱, 캐싱, offloading SSL processing에 사용될 수 있다.

3. Load Balancer
nginx는 들어오는 요청을 여러 백엔드 서버로 분산할 수 있다. 이를 통해 리소스 사용, 처리량을 최적화할 수 있고, 시스템 과부하를 방지한다.

4. HTTP cache
Nginx는 웹 페이지 응답을 저장하고 cache에서 직접 제공할 수 있습니다. 따라서 백엔드 서버의 작업 부하가 크게 줄어들고 성능과 응답성이 향상됩니다.

5. Media streaming
미디어 스트리밍 효율성을 조절할 수도 있다. 스트리밍 사이트에서 많은 동시 연결을 처리하는 nginx의 기능에 의존함.

#
# 4. usecase
인터넷 쇼핑몰의 경우, 웹 페이지는 동적으로 생성되지만 제품 이미지나 묘사 등은 자주 변하지 않는다. 이런 경우 nginx를 이용해, cache, reverse proxy기능을 추가할 수 있다.
Nginx가 이미지등의 정적 컨텐츠를 serve하고 자주 변하지 않는 페이지들을 cache 한다.
이 경우, appl 서버로의 부하가 감소되고, 동적 컨텐츠를 처리하는데에 더 집중할 수 있게 된다.

#
# 5. 사용법
1. install
우분투에서는 apt-get으로 설치
``` bash
    sudo apt-get update
    sudo apt-get install nginx
```

2. configuration
config 파일 경로는 보통 `etc/nginx/nginx.conf`에 있음. 이 파일에 들어오는 요청을 어떻게 처리할지에 대한 설정을 한다.

3. Starting and Enabling Nginx
구동은 다음과 같이 한다.
``` bash
    sudo systemctl start nginx
    
    # boot시 시작되게 하고 싶으면
    sudo systemctl enable nginx
```

4. Testing
nginx는 디폴트 페이지를 제공한다. 직접 들어가보면 됨..

#
# 6. Ref
- guide : http://nginx.org/en/docs/beginners_guide.html
- https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04

