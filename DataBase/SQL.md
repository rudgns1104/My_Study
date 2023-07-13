# SQL

`2023-07-13`

**SQL**(Structured Query Language)은 관계형 데이터베이스 관리 시스템(RDBMS)의 데이터를 관리하기 위해 설계된 특수 목적 프로그래밍 언어이다. - `위키백과`

> 관계형 데이터베이스는 정보를 표 형식으로 저장하며, 행과 열은 다양한 데이터 속성과 데이터 값 간의 다양한 관계를 나타낸다. - `aws`

---

<br>

# SQL시스템의 종류

## Relational / SQL

대표적인 관리 시스템

- MySQL
- PostgreSQL
- SQLite

## Non-Relational / Non-SQL

대표적인 관리 시스템

- mongoDB
- DynamoDB
- CouchDB

---

<br>

# SQL의 구성 요소

SQL은 엑셀 문서와 똑같이 생겼다.

- `SQL`데이터베이스 : 테이블 / `엑셀`문서 : 시트
- `SQL`테이블 : 행(row), 열(column) / `엑셀`문서 : 행(row), 열(column)

---

<br>

# SQL의 명령어

## 정의어(DDL)

**DDL**(Data Definition Language)은 데이터베이스를 정의하는 언어를 말하며 데이터를 생성하거나 수정, 삭제 등 데이터의 전체 골격을 결정하는 언어를 말한다.

- 생성 : `CREATE` TABLE 테이블명

  > `CREATE` 컬럼명 FROM 테이블 WHERE 조건문 <br> `CREATE VIEW` 뷰이름 `AS SELECT` 컬럼1, 컬럼2~ FROM 테이블 WHERE 조건문
  >
  > > VIEW : 유도된 가상 테이블.

- 변경 : `ALTER` TABLE 테이블명 `ADD` 컬럼명 데이터타입
  > `ALTER` TABLE 테이블명 `ADD` 컬럼명 데이터타입 <br> `ALTER` TABLE 테이블명 `MODIFY` 컬럼명 데이터타입 <br> `ALTER` TABLE 테이블명 `DROP` 컬럼명
  >
  > > `ALTER ADD` : ALTER문의 열 추가 <br> `ALTER MODIFY` : ALTER문의 타입 변경 <br> `ALTER DROP` : ALTER문의 열 삭제 <br>
- 제거 : `DROP` TABLE 테이블명 [CASCADE/RESTRICT]
  > DROP TABLE 테이블명 `RESTRICT` <br> DROP TABLE 테이블명 `CASCADE` <br> SELECT `DISTINCT` 컬럼명 FROM 테이블명
  >
  > > `RESTRICT` : 참조 시 삭제 취소 <br> `CASCADE` : 참조 삭제 <br> `DISTINCT` : 중복제거
- 초기화 : `TRUNCATE` 테이블명

## 조작어(DML)

**DML**(Data Manipulation Language)은 DDL에 의해 생성된 스키마 내에서 데이터를 조작하는 데 사용되는 일련의 SQL 명령이다.

- 검색 : `SELECT` 컬럼명 `FROM` 테이블명
  > SELECT 컬럼명 FROM 테이블명 `WHERE 조건문` <br>
  > SELECT 컬럼명 FROM 테이블명 `ORDER BY 컬럼명 ASC` <br>
  > SELECT 컬럼명 FROM 테이블명 `GROUP BY 컬럼명 HAVING 조건문` <br>
  > SELECT 컬럼명 FROM 테이블1 `LEFT JOIN` 테이블2 `ON` 테이블1.컬럼명 = 테이블2.컬럼명
  >
  > > `WHERE` : SQL 기본 조건문 <br> `ORDER BY` : 정렬 (ASC : 오름차순 / DESC : 내림차순) <br> `GROUP BY` : 그룹(조건 작성 시 HAVING) <br> `조인` : INNER JOIN / OUTER JOIN(LEFT/RIGHT/FULL)
  > >
  > > > SELECT `작성` 순서 : SELECT > FROM > WHERE > GROUP BY > HAVING > ORDER BY <br> SELECT `실행` 순서 : FROM > WHERE > GROUP BY > HAVING > SELECT > ORDER BY
- 갱신 : `UPDATE` 테이블명 `SET` 컬럼명 = 수정값
- 삭제 : `DELETE` [`FROM`] 테이블명
- 삽입 : `INSERT INTO` 테이블명 `VALUES` 입력값1, 입력값2 ~

## 제어어(DCL)

**DCL**(Data Control Language)은 데이터베이스에 접근하거나 객체에 권한을 부여하거나 제거하는 등의 역할을 하는 언어를 말한다.

- 완료 : `COMMIT`
  > 트랜잭션의 작업이 정상적으로 완료되었음을 관리자에게 알려준다.
- 취소 : `ROLLBACK`
  > 트랜잭션의 작업이 비정상적으로 종료 되었을 때 원래의 상태로 복구한다.
- 권한부여 : `GRANT` SELECT ON 테이블명 `TO` 컬럼명
  > 특정 데이터베이스 사용자에게 특정 작업에 대한 수행권한을 부여한다.
- 권한제거 : `REVOKE` SELECT ON 테이블명 `FROM` 컬럼명
  > 특정 데이터베이스 사용자에게 특정 작업에 대한 권한을 박탈, 회수한다.
