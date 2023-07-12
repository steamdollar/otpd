# Rate Limiting
비슷한걸 한 것 같은데 뭐지.. nginx랑 겹치는 내용이 좀 있어서 그런가..

#
# 1. Keywords
- rate limit
- throttling
- quality of service
- Denial of Service (DoS)


#
# 2. Overview
네트워크 트래픽을 제한하기 위한 테크닉. 특정 기간동안 client가 얼만큼의 요청을 보낼 수 있는지에 대한 제한을 설정한다.


#
# 3. Key Concept
1. Rate limit
특정 타임 프레임 동안 client가 보낼 수 있는 요청의 수

2. Throttling
접근을 거부하는 대신, 서비스의 속도를 줄이는 것

#
# 4. Use Case
1. Prevent Abuse
한 명의 사용자가 많은 요청을 보내 서버를 부하시키는걸 방지

2. Cost Management
요청의 속도를 제한함에 따라 어떤 지점에서든 최대 cost를 예측, 컨트롤 할 수 있음

3. Quality of Service
서버 리소스 부족을 방지하고 공평한 사용을 보장

#
# 4. Pros
1. 리소스 관리
2. 보안

#
# 5. Cons
1. 잘 사용하지 못하면 UX에 부정적 영향

#
# 6. Ref
- https://www.nginx.com/blog/mitigating-ddos-attacks-with-nginx-and-nginx-plus/
