### RDBMS VS NOSQL
#### 우선 DBMS란?

> 데이터베이스 관리 시스템으로 사용자와 데이터 사이에서 사용자의 요청에 의해 데이터의 생성 조회 등 데이터베이스를 관리해주는 역할을 한다.

#### SQL이란?
> 관계형 데이터베이스 관리 시스템(RDBMS)의 관리를 위해 제작된 언어로써, 자료의 검색과 재조합, 스키마 생성과 수정과 같은 데이터베이스 객체 조정 관리를 위해 사용되고 있다.


#### RDBMS란?
> R은(Relational)의 약자로 RDBMS는 관계형 데이터베이스 관리 시스템을 의미함. RDBMS에서의 저장 방식은 SQL에 의해 저장되고 있으며 정해진 스키마에 따라 데이터를 저장해야함. 테이블 간 Join이 가능함 


#### NOSQL 이란?
> NoSQL이란(Not Only SQL)의 약자로 말 그대도 위에서 설명한 RDB 형태의 관계형 데이터베이스가 아닌 다른 형태의 데이터 저장 기술을 의미함. 또한 NoSQL에서는 RDBMS와는 달리 테이블 간 관계를 정의하지 않음. 데이터 테이블은 그냥 하나의 테이블이며 테이블 간의 관계를 정의하지 않아 일반적으로 테이블 간 Join도 불가능.

#### RDBMS, NOSQL 장단점
<img width="700" alt="스크린샷 2023-03-11 오후 3 18 51" src="https://user-images.githubusercontent.com/31895069/224469409-d9ee07e4-4d8e-41bc-b9e2-818d928bbb9a.png">



### Redis란?
Redis(레디스)는 REmote DIctionary Server의 약자로 오픈소스(BSD licensed) DBMS입니다.

In-memory(인메모리) 데이터 저장소이며, Key-Value기반의 NoSQL DBMS입니다.

보통 DB, Cache(캐시), 메시지 브로커 등의 용도로 사용합니다.

### REDIS 설치
#### 공식 사이트에서 install 파일 다운로드 받아 설치

#### docker pull 받아서 설치

#### 맥의 경우 Home brew 이용해서 설치

설치는 쉽다.
- https://luran.me/351
- https://gam1532.tistory.com/34

### Redis 사용하는 이유
여러 이유가 있겠으나 대표적인것만 적겠다.
#### in-memory
disk가 아닌 memory에 저장하기 때문에 disk I/O 작업이 발생하지 않아 속도가 빠르며, 휘발성입니다.

#### No-SQL
Not Only SQL를 뜻하며 RDBMS에 비해 속도가 빠른 장점이 있습니다. key-value 형식으로 데이터 저장

일단 속도가 굉장히 빠르고 고가용성 목적으로 사용된다.

### 어떻게 활용할까?
- 세션 캐싱 및 토큰 저장
- 전체 페이지 캐시
- 메시지 대기열 애플리케이션
- 랭킹 보드
- 좋아요 같은 빠른 데이터 처리를 요하는 시스템


