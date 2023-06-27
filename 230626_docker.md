#
# Docker

#
# 1. intro

Docker는 컨테이너에 어플리케이션을 관리, 투입, 구동하는 플랫폼이다.
컨테이너는 원하는 소프트웨어를 실행하는데 필요한 모든 조각 (코드, 런타임, 시스템 툴, 라이브러리, 세팅)을 포함한 실행가능하고 standalone한 소프트웨어 패키지이다.

컨테이너는 가볍고 일관적이고 재현 가능한 환경을 제공하기 때문에 소프트웨어 개발 및 운영에서 많이 사용한다. (devOps)

#
# 2. features

1. Containerization : 어플리케이션과 그 dependencies를 단일 컨테이너에 패키징해 환경에 관계없이 동일하게 구동할 수 있도록 한다.

2. Docker Hub : Docker image를 공유, 검색하는 경로. 다양한 어플리케이션, 서비스에 대한 이미지를 push, pull할 수 있다.

3. Docker Compose : 멀티 컨테이너 도커 어플리케이션을 정의, 구동하는 툴.
    Docker Compose를 이용해 멀티 컨테이너 어플리케이션을 하나의 파일로 정의하고, 하나의 커맨드로 어플리케이션을 실행 가능.

4. Portability and Consistency : 도커 컨테이너는 어디서나 구동할 수 있다. (클라우더, 데이터 센터, 랩탑 등..) 이러한 이식성은 개발 라이프사이클의 여러 단계에 걸쳐 일관성을 보장한다.

5. Integration and CI/CD : Docker는 애플리케이션의 빌드, 테스트 및 배포를 자동화하기 위해 다양한 CI/CD 도구(예: Jenkins, GitLab CI 등)에 통합할 수 있다.
> 이 부분은 잘 와닿지가 않네..

6. Isolation & Security : 각 컨테이너는 다른 컨테이너와 호스트 시스템으로부터 격리된다. 따라서 컨테이너 내부에서 실행 중인 프로세스는 서로 영향을 미치지 않는다.

7. Scalability : 수평적 확장이 쉽다. 컨테이너 갯수만 늘리면 끝.

#
# 3. Use Cases

1. MicroService Architecture : 각 서버가 컨테이너에서 돌아가는 마이크로 서비스에 활용

2. Environment Standardization : 개발, 테스트 및 프로덕션 환경을 표준화하여 애플리케이션이 일관되게 작동하도록 보장한다.

3. Continuous Integration and Deployment : CI/CD tool과의 통합을 통해 어플리케이션의 빌드, 테스트, 배포를 자동화

4. Application Isolation : 보안 및 리소스 관리를 위해 격리된 환경에서 다양한 어플리케이션 또는 그 일부를 실행합니다.

#
# 4. Getting Started

1. 공식 홈페이지에서 Docker 설치
https://docs.docker.com/get-docker/

2. 간단한 컨테이너 구동
``` bash
    # 테스트용 이미지를 다운로드 및 실행
    docker run hello-world
```

3. 공식 문서에서 기본적인 사항 학습
https://docs.docker.com/get-started/