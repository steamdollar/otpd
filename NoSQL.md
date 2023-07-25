# NoSQL DB

#
# 1. keywords
- non-relational
- schema-less
- CAP theorum (**&&)

* CAP theorum
CAP 정리는 분산 컴퓨팅의 개념으로,
분산 데이터 저장소가 일관성, 가용성, 분할 내성 세 가지를 동시에 제공하는 것은 불가능하다는 것을 의미한다.

- Consistency (C)
모든 노드가 동일한 시간에 동일한 데이터를 보고 이썽야 한다.

- Availability (A)
모든 요청은 해당 요청이 성공했는지에 대한 응답을 받아야 한다.

- Partition tolerance (T)
네트워크 장애로 인한 임의 파티셔닝에도 시스템이 계속 작동하는 것.

ref : https://www.ibm.com/kr-ko/topics/cap-theorem


#
# 2. Intro
NoSQL db는 관계형 db (SQL)에서 사용되는 table 관계 이외의 방식으로 모델링된

데이터를 저장하고, 검색하는 메커니즘을 제공하는 db를 의미한다.

이런 db는 인터넷의 성장, 속도에 대한 필요성, 기존 sql db로는 충족되지 않는 데이터의 복잡성에 대응하기 위해 등장했다.

#
# 3. Concepts
1. Non-relational
데이터 저장을 위해 테이블 기반 포맷을 사용하는 SQL db와는 다르게 

noSQL은 문서, k-v, wide-column(**&&), 그래프등 다양한 포맷을 사용해 데이터를 저장한다.

* Wide-Column
테이블, 행, 열을 사용하는 NoSQL db의 한 유형이지만 sql과 달리 열의 이름과 형식이 같은 테이블의 행마다 다를 수 있다.
여러 상용 서버에 걸쳐 대규모 데이터세트를 저장하도록 설계되었고, 이로 인해 확장성, 내구력이 좋다.

2. 확장성
데이터 로딩량이 증가해도 쉽게 수용, 확장할 수 있도록 설계되었다.

3. 분산 컴퓨팅
많은 NoSQL db는 분산 컴퓨팅을 활용하므로 
데이터가 여러 시스템에 분산되어 데이터 액세스, 재해 복구에 용이하다.

4. Schemaless
NoSQL db는 보통 스키마가 없어 각 필드가 어떤 데이터를 저장할 지 정의할 필요가 없고, 
여러 타입의 데이터를 함께 저장할 수 있다.

#
# 4. Use case
1. Big Data
종종 빅 데이터 개념과 함께 사용되는데, 이는 빅 데이터가 양은 많되 구조화가 비교적 덜 된 데이터를 처리해야하기 때문.

2. 실시간 web apps
nosql db들은 수평적 확장을 지원하는데, 이는 빠른 read/write 작업과 많은 양의 데이터를 다루는 능력이 필요한
실시간 웹 어플리케이션에 적합하다.

3. Content Management system (**&&)
cms가 다루어야 하는 동적이고 계쏙 변하는 데이터를 저장하기에 적합하다.

* Content Management System (CMS)
디지털 콘텐츠를 만들고 관리하는데 사용되는 소프트웨어 app. 
일반적으로 엔터프라이즈 컨텐츠 관리(ECM), 웹 컨텐츠 관리(WCM)에 사용된다.
CMS는 파일에 대한 버전 제어 엑세스, 공동 편집, 컨텐츠 제작 및 편집을 지원하는 기타 기능을 제공할 수 있다.
e.g. WordPress, Joomla, Drupal