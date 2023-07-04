# CI/CD

#
# 1. Keywords
- Continuous Integration (CI)
- Continuous Deployment (CD)
- Continuous Delivery
- Pipeline
- Jenkins
- GitLab CI
- GitHub Actions

#
# 2. Intro
Continuous Integration (CI, 지속적 통합) 와 Continous Deployment (CD, 지속적 배포)는 코드 변경 사항을 자주 통합하고, production 환경에 자동으로 배포하는 소프트웨어 개발 방식이다.
이런 개발 방식은 개발 프로세스를 개선하고, 코드 품질을 보장하며, 신속한 기능 및 버그 수정을 가능하게 한다.

#
# 3. Key Concepts
1. Continuous Integration (CI) : CI는 여러 명의 기여자가 중앙 경로에 자주 (보통 하루에 몇 번) 바뀐 코드를 통합하는 방식이다.

2. Continous Deployment (CD) : CD는 통합한 코드 변화를 바로 production 환경에 자동으로 배포하는 방식이다.

3. Continuous delivery : CI의 확장된 개념이다. continous delivery는 코드의 통합에서 한 단계 더 나가서 releaseable state로 유지되게끔 한다. 다만 반드시 자동화된 것은 아니고, 수동 승인이 필요할 수 있음.

4. Pipeline
CI/CD pipeline은 코드 변화를 테스트, 빌드, 배포하도록하는 일련의 자동화된 스탭이다. 이 파이프라인은 workflow(**&&)로 시각화될 수 있다.

#
# 4. use case
1. Rapid Release cycles
프로젝트가 웹 어플리케이션에 대해 빈번한 release cycle을 가지길 원할 경우, CI/CD를 구현해 코드를 자주 통합, 테스트할 수 있다. 예를 들어 SaaS(**&&) 기업은 CI/CD 파이프라인을 사용해 하루에 여러 번 기능을 업데이트, 배포할 수 있음.

2. Collaborative Development
여러 기여자가 작업하는 오픈 소스 프로젝트의 경우, CI가 서로 다른 소스의 기여를 test, integrate하는데 도움을 줄 수 있음. 예를 들어 GitHub action을 사용해 오픈 소스 리포지토리에서 pull reqeust testing을 자동화할 수 있다.

#
# 5. Pros
- 빠른 release cycle
- 코드 수정에 대한 즉각적 피드백
- 통합 이슈 감소
- 자동 테스트, 배포 > 사람의 실수로 인한 에러 감소
- 사용자에게 즉각적인 제공

#
# 6. Cons
- 최초의 CI/CD pipeline 구축 단계는 어려울 수 있음
- 개발 방식에 대한 문화적 시프트가 필요
- CD의 경우, 문제가 있는 변화를 배포할 수 있음

#
# 7. ref
- intro to CI/CD : https://docs.gitlab.com/ee/ci/introduction/
- Jenkins 문서 (**&&) : https://www.jenkins.io/doc/
- 깃헙 핵션 문서 : https://docs.github.com/en/actions

#
# 8. Glossary
1. SaaS (Software as a Service)
인터넷을 통해 소프트웨어가 제공되는 소프트웨어 라이센스 및 제공 모델이다.
클라우드 컴퓨팅의 한 형태로, 사용자는 개별 PC에 소프트웨어를 설치하지 않고 브라우저를 통해 소프트웨어 및 해당 기능에 엑세스할 수 있다.

- Accessibility : 인터넷에 연결된 어떤 기기와도 연결 가능
- Subscription-Based : 구독 기반의 가격 모델을 많이 사용하므로 사용자가 유연하게 사용 여부를 결정할 수 있음
- 자동 업데이트, 유연한 확장 가능

예시로는 구글 워크스페이스, ms office 365등이 있음.

SaaS 기업은 이런 SaaS 어플리케이션을 만들고 유지, 관리하는 조직임. 경쟁이 치열하고 빠르게 움직여야하기 때문에 서비스를 지속적으로 업데이트, 개선해야 하므로 CI/CD 프로세스를 사용하는 경우가 많다.


2. Jenkins
Jenkins는 소프트웨어 개발 프로세스의 다양한 단계를 자동화하는 데 사용되는 오픈 소스 자동화 서버이다. Jenkins는 Git과 같은 버전 관리 도구를 지원하며 애플리케이션 빌드, 테스트 및 배포를 위한 일련의 명령을 실행할 수 있으며, 
CI/CD를 구현하는 데 중요한 역할을 한다.

일반적인 CI/CD 셋업의 경우, 개발자가 git 등의 버전 컨트롤 시스템에 코드를 commit하면, Jenkins가 이를 pull해서 build, test를 거친다.
test 과정에서 문제가 없다면 production에 배포한다.
Jenkins pipeline은 보통 `Jenkinsfile`을 이용해 정의되며 이는 pipeline을 코드로 묘사한 텍스트 파일이다.
