#
# Database Indexing

#
# 1. Keywords
- Database Performance
- Search Optimization
- B-tree (balanced Tree)
- Query Execution time
- Index scan
- Cardinality

#
# 2. Intro
DB 인덱싱은 db 작업, 특히 data 검색의 성능을 향상 시키는 데 사용되는 기술이다.
전공책에 찾기 쉽게 스티커 붙이는 그런 느낌..

#
# 3. Mechanism
1. Data structures
가장 일반적으로 db는 인덱싱에 B-Tree라고 불리는 데이터 구조를 사용한다.
B-tree는 block에 저장된 데이터를 빠르게 관리, 정렬, 검색할 수 있다.

2. Index Creation
DB table의 하나 이상의 column에 인덱스를 만들 수 있다.
이렇게 indexing할 column을 선택하는 것은 매우 중요하며, appl이 일반적으로 실행하는 쿼리를 기반으로 해야 한다.

3. Query Optimization
쿼리가 실행될 때, db는 index를 이용해 필요한 데이터의 위치를 효율적으로 특정할 수 있다. 전체 table을 전부 스캔하는 것보다 빠르다.

4. Trade-offs
이에 따른 cost도 존재한다. 쓰기 작업 (update, dlete, insert 등)을 할 때 index들도 업데이트 해야하므로 속도가 느려질 수 있고, index 자체가 저장 공간을 소모한다.

#
# 4. Use Cases
- Large Datasets
데이터 보관량이 많을 경우 테이블 전체를 스캔하는 것은 비효율적이므로 indexing을 하는 것이 좋다. (관련 테이블을 따로 하나 만들수도 있음)
  
- Frequent Read Operations
콘텐츠 웹사이트와 같이 읽기 작업이 쓰기 작업보다 훨씬 많은 appls에서.

- Reporting and Data Analysis
데이터를 분석하기 위해 복잡한 쿼리를 실행하는 환경에서

#
# 5. Practical example
많은 주문에 관한 정보를 저장하는 전자 상거래 사이트가 있다고 하자.
이를 관리하려면 주기적으로 특정 기간 내의 주문을 검색해야 한다.
index가 없으면 table 전체를 스캔해 조건에 맞는지를 일일히 확인해야 한다. (slow)
order_date column이 index로서 있다면 확인해야 하는 정보가 매우 감소한다.
그 column만 일단 쭉 읽고, 조건을 만족하는 column을 포함하는 dataset을 가져오면 됨.

#
# 6. ref
- https://velog.io/@bsjp400/Database-DB-%EC%9D%B8%EB%8D%B1%EC%8B%B1Indexing%EC%9D%B4%EB%9E%80

- B-Tree : https://rebro.kr/169?category=484170

- https://velog.io/@emplam27/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%EA%B7%B8%EB%A6%BC%EC%9C%BC%EB%A1%9C-%EC%95%8C%EC%95%84%EB%B3%B4%EB%8A%94-B-Tree