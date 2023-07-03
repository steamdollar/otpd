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
# 3. use case
1. Rapid Release cycles
프로젝트가 웹 어플리케이션에 대해 빈번한 release cycle을 가지길 원할 경우, CI/CD를 구현해 코드를 자주 통합, 테스트할 수 있다. 예를 들어 SaaS(**&&) 기업은 CI/CD 파이프라인을 사용해 하루에 여러 번 기능을 업데이트, 배포할 수 있음.

2. Collaborative Development
여러 기여자가 작업하는 오픈 소스 프로젝트의 경우, CI가 서로 다른 소스의 기여를 test, integrate하는데 도움을 줄 수 있음. 예를 들어 GitHub action을 사용해 오픈 소스 리포지토리에서 pull reqeust testing을 자동화할 수 있다.

#
# 4. Pros
- 빠른 release cycle
- 코드 수정에 대한 즉각적 피드백
- 통합 이슈 감소
- 자동 테스트, 배포 > 사람의 실수로 인한 에러 감소
- 사용자에게 즉각적인 제공

#
# 5. Cons
- 최초의 CI/CD pipeline 구축 단계는 어려울 수 있음
- 개발 방식에 대한 문화적 시프트가 필요
- CD의 경우, 문제가 있는 변화를 배포할 수 있음

#
# 6. ref
- intro to CI/CD : https://docs.gitlab.com/ee/ci/introduction/
- Jenkins 문서 (**&&) : https://www.jenkins.io/doc/
- 깃헙 핵션 문서 : https://docs.github.com/en/actions

#
# 7. Glossary
1. SaaS Company
2. Jenkins

이건 내일 계속..