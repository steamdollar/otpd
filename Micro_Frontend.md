# Micro Frontend

#
# 1. keywords
- Modularization
- Frontend
- Isolation
- Independent Deployment

#
# 2. Overview
Micro Frontend는 독립적으로 제공가능한 frontend app들을 하나의 전체로 구성하는 아키텍쳐 스타일이다. 마이크로 서비스가 백엔드를 더 작은 서비스로 분리하는 것을 목표로 하는 것처럼, micro frontend도 이에 대해 동일한 작업을 수행할 수 있다. 
쉽게 말해 마이크로 서비스의 프론트엔드 버전

#
# 3. Benefits
1. Isolation
여러 팀이 동시에 여러 부분에서 작업할 수 있으므로 충돌을 줄일 수 있다.

2. Independent Deployment
각 서비스들은 독립적으로 배포되며, 이로 인해 리스크와 복잡성을 줄일 수 있다.

#
# 4. Use Cases
1. Large Scale Apps
규모가 큰 apps에서 프론트엔드가 복잡해질 수 있는데, Micro frontend는 이런 복잡성을 더 작고 관리하기 용히하도록 쪼갤 수 있다.

#
# 5. Consideration
Micro frontend에서 나오는 어려움도 존재한다. 여러 개의 코드 베이스를 관리하는 게 힘들 수도 있고, ux의 단절이 발생하지 않도록 유의해야 한다. 또, 여러 개의 apps를 로드하기 때문에 성능의 저하가 일어나기도 쉽다.

#
# 6. ref
- https://martinfowler.com/articles/micro-frontends.html