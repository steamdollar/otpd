# DB normalization

#
# 1. intro
db 표준화는 db의 데이터를 조직화하는 테크닉이다.
테이블을 분해해서 ㄱ, 내부의 데이터의 불필요한 중복이나 작업을 방지하는 시스템적 접근이다.

#
# 2. Concept
표준화는 E.F.Codd에 의해 1970년에 개발되었으며, 이는 간단하고 중복이 없는, 유연한 db 구조를 만드는 것을 목적으로 헀다. 관계가 있는 테이블들로부터 동일한 데이터를 제거하는 여러 단계의 과정으로 이루어진다.


#
# 3. Keywords
1. Anomaly
db에서 발생할수 있는 불일치는 종종 죽복성 및 테이블 간의 적절한 연결 부족으로 인해 발생한다.

2. Functional dependency
db의 관계에서 두 속성 집합 사이의 제약 조건

3. Normal Forms
표준화의 각 단계. 각 정규 형태는 정규화 수준이 높아진 것을 나타내며, 일반적으로 다른 측면을 희생해 db를 일부 개선한다.
가장 일반적으로 사용되는 정규 형식은 1NF, 2NF, 3NF이다.


#
# 4. Benefits
1. 데이터 중복의 감소
각 데이터 조각이 한 장소에만 저장되있는 것을 보장함으로써 표준화는 데이터 저장에 사용하는 용량을 줄일 수 있고, 데이터 일관성을 보장할 수 있다.

2. 데이터 무결성 강화
각 데이터 조각에 대해 하나의 잘 정의된 장소를 생성함으로써, 표준화는 데이터의 정확성과 무결성을 유지하는걸 쉽게 만들어준다.

3. 데이터 검색 효율 최적화
데이터를 전체의 일부를 묘사하는 각각의 논리 그룹으로 배열함으로써, 표준화는 데이터의 검색과 정렬을 효율적으로 만든다.

#
# 5. challenges
1. 과도 표준화
지나친 표준화는 성능 이슈와 복잡한 db 디자인을 유발할 수 있다.

2. 성능
특정 케이스에서 쓰기 작업을 할 일이 많다면 표준화되지 않은 구조가 더 효율적일 수 있다.

#
# 6. ref
- https://www.guru99.com/database-normalization.html