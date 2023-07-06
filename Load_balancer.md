# Load Balancers

#
# 1. intro
load balancer (부하 분산)는 들어오는 네트워크 트래픽을 여러 서버로 분산해,
단일 서버에 너무 많은 부하가 걸리지 않도록 한다.
이는 트래픽이 급증할 때 web appl과 서비스의 안정성, 효율성을 위해 중요하다.

#
# 2. Keywords
- Traffic Distribution
- scalability
- round robin
- least connection
- session persistence
- health checks

#
# 3. What are Load Balancers?
서버의 앞에 앉아 client들의 요청을 속도와 성능을 최대화할 수 있도록 모든 서버에 걸쳐 분배하는 역할을 한다. (과부하된 서버가 생기는걸 방지함) 

#
# 4. Type of Load balancer
1. Hardware Load Balancers
기존 로드 밸런서는 일반적으로 데이터 센터 내에 설치되는 물리적 장치이다.
일반적으로 비용이 많이 들고, 구성하는데 고급 라우팅 지식이 필요할 수 있다.

2. Software Load Balancers
소프트웨어 로드 밸런서는 Nginx, HAProxy, AWS Elastic Load balancing 등이 있으며, 하드웨어 로드 밸런서에 비해 더 유연하고 관리가 쉽다.

3. Layer 4 vs Layer 7 Load Balancing
Layer 4 load balancer는 IP주소 및 TCP port와 같은 네트워크 정보를 기반으로 traffic을 분산하는 반면,

Layer 7 load balancer는 http header, cookie 또는 appl msg와 같은 컨텐츠를 기반으로 트래픽을 분산시킨다.

#
# 5. Load balancing Algorithms
load balancer가 트래픽을 분산하는 알고리즘

1. Round Robin
서버에 따라 순차적으로 req를 분산

2. least Connection
새로운 커넥션 요청을 현재 가장 커넥션이 적은 서버에 전달

3. IP Hash
client의 ip에 따라 어떤 서버가 요청을 받을지 결정


#
# 6. Benefits
1. Scalibilty
트래픽이 증가하면 새로운 서버를 추가해 이를 해결할 수 있다.

2. High Availability
서버 중 하나에 문제가 생기더라도 리디렉션을 통해 다른 서버로 처리 가능

3. Improved UX
appl 성능의 최적화 가능

#
# 9. Ref
- nginx : https://www.nginx.com/resources/glossary/load-balancing/
- MS Azure : https://azure.microsoft.com/en-us/products/load-balancer/
- AWS Elastic load Balancing : https://aws.amazon.com/ko/elasticloadbalancing/