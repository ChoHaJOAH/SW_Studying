# Cache

- 많은 시간이나 연산이 필요한 일에 대한 결과를 저장해 두는 것
- why?
  - 빠른 속도를 위해! -> 자주 사용하는 데이터를 속도가 빠른 cache에 저장해서 사용한다.
  - cache를 사용하면? 균등한 속도, 부하 감소 
- Cache 서비스 
  - Redis
  - Memcached
  - 서비스의 로직 서버와 DB서버가 별도로 분리되어 있기 때문에, 각 DB서버의 동기화가 필요해지기 때문에 이러한 서비스가 필요



# 캐시 메모리

- 컴퓨터 시스템의 성능을 향상시키기 위해 주로 [CPU](https://namu.wiki/w/CPU) 칩 안에 포함되는 일종의 메모리
- 메인 메모리보다 빠르고 작고 매우 비싼 메모리
- [레지스터](https://namu.wiki/w/레지스터)와 함께 [메모리 계층 구조](https://namu.wiki/w/메모리 계층 구조)의 전통적인 핵심 계층 중 하나
- 데이터 지역성을 활용하여 메인 메모리에 있는 데이터를 캐시 메모리에 불러와 두고, CPU가 필요한 데이터를 캐시에서 먼저 찾도록 하면 시스템 성능을 향상시킬 수 있다.