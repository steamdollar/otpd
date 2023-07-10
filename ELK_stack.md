# ELK Stack (Elastic Search, Logstash, Kibana)

#
# 1. intro
ELK stack은 로깅, 로그 분석, 시각화를 실시간으로 하기위해 사용되는 오픈 소스 소프트웨어 툴이다.
stack은 다음 요소들로 구성된다.

1. Elastic search (E) : 로그를 저장하는 NoSQL db

2. Logstash (L) : 여러 소스로부터 data를 수집, 변환해 1과 같은 저장소로 전송하는 서버 사이드 데이터 처리 파이프라인

3. Kibana (K) : 데이터의 실시간 요약, 시각화 차트를 제공하는 elasticsearch용 데이터 시각화 도구

4. Beats : 서버에 에이전트로서 설치해 운영 데이터를 elastic search로 전송하는 경량 데이터 수집기 (Logstash가 너무 무거워서 도입됨)

E : 데이터 저장, 분석, 관리
L : 데이터 수집, 입력, 변환, 구조 구축, 출력 및 송신
K : 데이터 탐색, 엑세스 제어


#
# 2. concept
주된 유스케이스는 중앙화된 로깅이며, 이는 특히 여러 개의 서버, 어플리케이션, 네트워크 기기들로부터 오는 모든 로깅을 한 군데에 모아 저장하고 싶을 때 유용하다.
단지 로그들을 수집하는 것만은 아니고, ELK stack을 이용해 이를 리뷰, 분석도 빠르게 할 수 있다.


#
# 3. use cases
1. 중앙화된 로깅 : 여러 소스로부터 다양한 형식의 로그 수집, 저장

2. Security 분석 : 서버 로그를 분석해 수상한 활동이나 보안 위협을 확인할 수 있고, 사고 대응 중 유용한 데이터를 제공 가능.

3. 성능 모니터링(Application Performance Monitoring. APM) : APM 솔루션과의 통합을 통해 ELK를 사용해 실시간으로 appl 성능을 모니터링하고 문제를 해결할 수 있다.


#
# 4. pros
1. scalability : Elastic search는 **&&Lucene 위에 빌드된 것이므로, 확장성이 뛰어나고, 많은 양의 데이터를 저장, 검색할 수 있다.

2. 실시간 분석 : Kibana는 사용자가 데이터를 실시간으로 시각화하고, 현재 경향과 문제점을 확인하기 쉽도록 한다.

3. Flexible Data ingestion : Logstash, beats를 사용해 여러 소스로부터 데이터를 실시간이나 병렬적으로, 다양한 포맷으로 수집할 수 있다. 또, E, L, K를 반드시 모두 사용할 필요 없이 필요한 모듈만 사용하고 다른건 대체할 수도 있음.


#
# 5. ref
1. docu E : https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html
2. docu L : https://www.elastic.co/guide/en/logstash/current/getting-started-with-logstash.html
3. docu K :https://www.elastic.co/guide/en/kibana/current/introduction.html

4. https://velog.io/@holidenty/ELK-ELK-Stack-%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C