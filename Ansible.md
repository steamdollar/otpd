# Ansible

#
# 1. intro
Ansible은 configuration 관리, appl 배포, 작업 자동화, IT ochestration을 
지원하는 오픈 소스 자동화 도구이다.
쉽게 말해 컴퓨터의 인프라 구성을 코드로 작성하는 것. 이를 잘 이용해 필요한 모든 서버에 배포함으로써 특정 환경을 동일하게 유지할 수 있다.
요즘엔 사용하는 서버수가 많아지다보니 필요성이 대두되는 듯.

자동화 작업을 정의하기 위해 YAML 포맷 파일을 사용하므로 배경 지식이 적은 사람도 쉽게 사용할 수 있다.

#
# 2. Key Concept
- Playbooks : YAML로 적힌 자동화 스크립트. playbook에서 원격 머신에서 실행될 작업들을 정의한다.

- Inventory : 관리 중인 서버에 대한 정보가 포함된 파일이다. (Ansible이 관리하는 호스트 이름의 목록.)

- Modules : module은 Ansible이 실행하는 code의 unit. 각 module에는 특정 유형의 db에서 사용자를 관리하는 것 부터 방화벽 규칙 관리 등의 다양한 용도가 있다.

- Roles : 완전히 독립적이고, 재사용가능한 변수, 작업, 템플릿, 모듈의 컬렉션을 위한 프레임워크 제공

- Ad-hoc commands : 단일 라인의 커맨드로, 간단한 테스크를 playbook 작성없이 실행할 수 있게 해줌.

#
# 3. Use case
- Configuration management : Ansible을 이용해 시스템 setup을 자동화하고, 시스템들이 일정하고 제대로 configured 되었는지 보장할 수 있다.

- Continous Deployment : Ansible은 코드 배포 프로세스를 자동화 함으로써, 더 신뢰성있고, 반복이 쉬워지도록 한다.
  
- orchestration : 자주 사용되는 용도로 여러 서버를 협업할수 있도록 조정해줌.
예를 들어 load balancer pool에서 서버를 제거하고, appl을 업데이트한 후 다시 부하 분산 장치 풀에 넣는다.

- Provisioning : 사용자의 인프라에 필요한 다양한 서버를 셋업 가능

#
# 4. Pros
1. simplicity : playbook의 포맷이 yaml이라 이해하고 쉬워서, 처음 사용하는 사람도 어렵지 않게 사용할 수 있음.

2. Agentless : 다른 configuration 관리 툴과 다르게, Ansible은 원격 호스트에서 구동되는 agent가 필요없다. 사용자가 관리하고 싶은 모든 시스템에 설치되어 있다고 가정하는 SSH를 사용한다.

3. Versatility : 구성 관리부터 배포, 오케스트레이션까지 다양한 용도로 사용 가능

4. Efficiency : SSH를 이용하고 기타 다른 것들을 원격 머신에 사용할 필요가 없으므로 경량이고 효율적이다. (다른 프로그램이 pull, ansible은 push 방식으로 동작)

#
# 5. ref
- doc : https://docs.ansible.com/ansible/latest/index.html
- https://velog.io/@honghwahyeong/Ansible-Ansible-%EC%9D%B4%EB%9E%80