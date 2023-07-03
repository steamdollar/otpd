#
# 1. Serverless Architecture
서버리스 아키텍처는 클라우드 공급자가 서버 할당 및 프로비저닝을 동적으로 관리하는 클라우드 컴퓨팅 실행 모델이다. 서버리스 아키텍처에서 개발자는 코드 작성에만 집중할 수 있으며 기본 인프라는 추상화된다.

## 1. key concept
1. Function as a Service (FaaS)
서버리스 아키텍쳐의 핵심 개념. 개별 함수를 작성하고, 이를 이벤트 (e.g. HTTP req, db operatrions)에 대한 응답으로 실행되게끔 함. 예시로는 AWS Lambda, Azure functions, Google Cloud Function등이 있음.

2. Event-Driven
서버리스 함수들은 일반적으로 event-driven이며, 이벤트나 트리거에 대한 응답으로서만 실행된다는 것을 의미한다. 일시적이며 지속적으로 실행되지 않는다.

3. Scaling and Pricing
서버리스 함수는 요청의 숫자와 함께 자동적으로 확장된다. 시간이 아닌 함수의 실행 횟수로 인해 소모된 리소스의 양만큼만 비용을 지불하면 된다.

4. Statelessness
함수는 stateless해, local state에 의존하지 않는다. 매번 다른 서버에서 실행될 수도 있으며, state가 있다면 db나 다른 외부 저장소에 저장되어야 한다.

## 2. Use Cases
- Data processing (e.g. image, video processing)
    **&& how?

- Automation of cloud infrastructure tasks
- Building APIs or microservice
- Handling asynchronous backend tasks

## 3. Pros
- 서버 관리가 필요 없다.
- 가격, 비용 측면에서 유리
- 확장성이 좋다.

## 4. Cons
- cold starts (**&& why?)
    오랜만에 쓰는 함수는 딜레이가 걸림

- 지연이 길어질 수 있음
- 오래 지속되는 함수의 실행에는 제한이 있을 수 있음 (e.g. AWS lambda는 한 함수를 최대 15분 동안 실행할 수 있음)
