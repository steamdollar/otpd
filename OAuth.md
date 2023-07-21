# OAuth

#
# 1. Overview
Oauth (Open Authorization)은 접근 위임에 대한 개방형 표준으로,
user가 다른 웹사이트나 appl에 비밀번호를 제공하지 않고도 자신의 정보에 대한
접근 권한을 부여하는 방법이다.


#
# 2. Key Concept
1. Third-Party Access
Oauth는 제3자가 사용자가 비밀번호를 제공하지 않아도 사용자의 정보를 교환해갈 수 있게 해준다.

2. Token
Oauth는 authorization token을 사용해 동작한다.

3. Scopes and permissions
app이 Ouath token을 요청하면 필요한 접근의 범위를 함께 특정한다. 
이 후, 사용자가 이를 승인해주어야 한다.


#
# 3. Use cases
1. Social logins
구글, 페이스북 등이 다른 app에서 oauth login을 할 수 있도록 api를 제공한다.

2. 제3자 app
oauth는 제3자 사용자의 pw를 받지 않고도 사용자 data에 access할 수 있게 해준다.


#
# 4. pros
1. ux 개선
oauth는 사용자가 pw 여러 개를 기억할 필요 없이 단일 계정을 사용할 수 있게 해 ux를 개선한다.

2. Security
사용자 credential이 서비스 제공자에 의해 다루어지므로 사용자의 pw등이 유출될 위험이 낮아진다.

3. Control over data
제 3자 app의 접근에 대해 사용자가 어떤 정보를 공개할지에 대한 선택을 용이하게 해준다.


* bearer token (무기명 토큰)
oauth2.0에서 다양한 리소스에 대한 접근 권한을 부여하는데 사용되는 access token의 한 유형이다.
특정 종류의 신원 확인이 필요없기 때문에 `무기명` 토큰이라고 불리며, 이 토큰을 소유한 사람에게만 접근 권한이 부여된다.
다른 사람에게 들어가면 보호된 리소스가 노출되게 됨.

#
# 5. Ref
- https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2
- https://velog.io/@undefcat/OAuth-2.0-%EA%B0%84%EB%8B%A8%EC%A0%95%EB%A6%AC