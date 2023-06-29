# GraphQL

#
# 1. Keywords
- Query language
- Data Fetching
- API
- Schema
- Resolvers
- Mutation
- Subcription

#
# 2. Intro
GraphQL은 API용 오픈 소스 데이터 쿼리 및 조작 언어이며, 데이터에 대해 정의한 type system을 상요해 쿼리를 실행하기 위한 런타임이다. 2012년 페이스북이 갤발, 2015에 오픈 소스로 풂.

각 리소스에 대한 엔드포인트의 fixed set을 노출하는 REST와는 다르게, GraphQL은 하나의 엔드포인트를 노출하고, 이를 이용해 모든 상호작용과 요청을 처리한다.

#
# 3. Key Concept
1. Schema Definition Language (SDL)
GraphQL API는 GraphQL 스키마 정의 언어를 이용해 강하게 타입된 스키마로 정의된다.  이 스키마는 쿼리할 수 있는 데이터의 타입과 그 관계를 정의한다.

2. Queries
쿼리는 GraphQL 서버에 어떻게 데이터를 요청할 것인지를 의미한다. 연관된 복수의 리소스들에서 데이터를 fetch해올 때 여러 개의 엔드포인트를 호출해야하는 REST와는 다르게, GraphQL은 Query들을 이용해 하나의 요청으로 필요한 모든 데이터를 가져올 수 있다.

3. Mutation
GraphQL에서 서버의 데이터를 수정하기 위해 사용되는 method

4. Resolvers
Query와 Mutation에 대한 데이터를 resolve하는 서버의 함수. GraphQL 스키마의 각 필드는 Resolver에 의해 지원된다.

5. Subscriptions
GraphQL의 특징 중 하나로, 서버가 `데이터의 변화가 있을때마다` 데이터를 client에 전송하는 것을 의미

6. Over-fetching & Under-fetching
필요없는 데이터를 더 받아오거나, 필요한 데이터를 일부 못 가져오는 문제를 해결했다. Client는 정확히 자신이 원하는 걸 특정할 수 있다.

#
# 4. Use cases
1. REST로 할 수 있는 것보다 더 효율적인 데이터 검색이 필요한 경우
2. front end에서 하나의 요청으로 여러 곳의 리소스를 가져와야 하는 경우
3. 서로 원하는 데이터가 다른 여러 client가 있는 경우
4. versioning 없이 API를 계속 업데이트 하는 경우

#
# 5. Pros
1. Querying data의 유연성
2. 효율적이고 정확한 데이터 검색
3. 강한 typing으로 인한 데이터 통합성
4. Subscription을 사용힌 Real-time data

#
# 6. Cons
1. 간단한 api에 대해선 overkill이 될 수 있음.
2. Query가 복잡하면 성능 이슈가 발생할 수 있음.
3. REST에 익숙해졌다면 러닝 커브가 있을 수 있음.

#
# 7. Ref
- Official Docu : https://graphql.org/
- https://www.howtographql.com/
- https://www.apollographql.com/
- https://www.taniarascia.com/introduction-to-graphql/
- https://www.apollographql.com/blog/graphql/basics/graphql-vs-rest/
