# TDD (Test-driven Development)

#
# 1. Overview
TDD는 코드 이전에 테스트가 먼저 쓰여지는 소프트웨어 개발 접근법이다.
이 방식은 
테스트 작성 > 코드 작성(테스트를 통과하는) > 코드가 기준을 맞출 수 있도록 refactor


#
# 2. Key Concept
1. Red, green, Refactor : TDD의 핵심이다. "red"는 실패한 테스트를 작성하는 것, "green"은
테스트를 통과하도록 코드를 작성하는 것, refactor는 test를 "green"으로 유지하면서 코드를 정리하는 것을 의미한다.

2. Unit Testing
TDD는 시스템의 가장 작은 유닛을 테스트하는데 집중한다. (보통 method, func)


#
# 3. Use cases
1. Preventing Regression
TDD는 시스템을 철저히 테스트하고 기능을 추가하거나 변경할 때 새로운 버그가 발생하는 regression을 방지하는데 도움이 된다.

2. Documentation
test는 시스템에 대한 일종의 문서를 제공한다. 다른 개발자는 테스트를 보고 method가 수행해야 하는 작업을 이해할 수 있다.


#
# 4. Pros
1. Prevent Bugs
버그를 개발 프로세스의 이른 단계부터 잡을 수 있음.

2. Siimplifies Integration
소프트웨어의 다른 부분과의 통합을 쉽게 해줌.

3. Improves code quaility
Red, green, Refactor cycle은 코드 조직과 가독성을 향상 시킴.


#
# 5. Cons
1. Time consuming
기능의 작은 단위 하나 하나를 다 테스트해야하므로 시간이 오래 걸린다.

2. Learning Curve 
개발에 대한 마인드셋의 교체가 필요하므로 익숙해지는데 시간이 걸림.