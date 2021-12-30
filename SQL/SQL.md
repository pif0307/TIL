# SQL

> SQL은 관계형 데이터베이스 관리 시스템(RDBMS)의 데이터를 관리하기 위해 설계된 특수 목적의 프로그래밍 언어이다. [Wikipedia](https://ko.wikipedia.org/wiki/SQL)

# 1. 기본 문법
## 1.1. SELECT
### 기본 구조
```SQL
SELECT select_list [ INTO new_table ]  
[ FROM table_source ] [ WHERE search_condition ]  
[ GROUP BY group_by_expression ]  
[ HAVING search_condition ]  
[ ORDER BY order_expression [ ASC | DESC ] ]  
```

### 예시
> _`datas`는 임의로 설정한 테이블이고, `id`, `password`는 `datas`의 칼럼임_

```SQL
SELECT * FROM datas
```

`datas`의 모든 데이터를 꺼냄.

```SQL
SELECT id FROM datas
```

`datas`의 모든 데이터의 `id`만 꺼냄.

```SQL
SELECT id, password FROM datas
```
`datas`의 모든 데이터의 `id`, `password`를 꺼냄. (여러개를 꺼낼 때 사용)

```SQL
SELECT password FROM datas WHERE id = 5
```
`datas`중 `id`가 5인 자료의 `password`만 꺼냄.

```SQL
SELECT * INTO newDatas FROM datas WHERE id = 1
```
`datas`중 `id`가 1인 자료를 `newDatas`라는 새 테이블을 만들어 가져옴.

검색 조건 조합

> AND: [조건1] `AND` [조건2]  
> OR: [조건1] `OR` [조건2]  
> NOT: `NOT(`[조건1]`)`


```SQL
SELECT * FROM datas ORDER BY id [ASC | DESC]
```
`datas`의 데이터중 `id`를 기준으로 하여 오름차순/내림차순으로 정렬한 후 가져옴.
> ASC: 오름차순  
> DESC: 내림차순

## 1.2. INSERT INTO
### 기본 구조
```SQL
INSERT [INTO target_table] (column1, [column2, ...]) values (value1, [value2, ...])
```

### 예시
> _`datas`는 임의로 설정한 테이블이고, `id`, `password`는 `datas`의 칼럼임_

``` SQL
INSERT INTO datas (id, password) value ('aidi113', '12345678!')
```

`datas`에 `id`가 _aidi113_ 이고 `password`가 _12345678!_ 인 새로운 데이터를 추가함.

## 1.3. ALTER TABLE
### 기본 구조
```SQL
ALTER [object_type objectname] [parameters]
```

### 예시
> _`datas`는 임의로 설정한 테이블이고, `id`, `password`는 `datas`의 칼럼임_

```SQL
ALTER TABLE datas DROP COLUMN id
```
`datas`에 `id`칼럼을 삭제함.

```SQL
ALTER TABLE datas ADD phone VARCHAR(10) NOT NULL
```
`datas`에 `phone`이라는 칼럼을 추가함.

```SQL
ALTER TABLE datas ALTER COLUMN phone VARCHAR(50) NULL
```
`datas`의 `phone`이라는 칼럼을 `VARCHAR(50)`, `NULL` 속성으로 변경함.



# 2. 참고 문헌
- [Wikipedia](https://ko.wikipedia.org/wiki/SQL)
- [[SQL] SELECT 문 간단하게 파헤치기 . FROM, WHERE, GROUP BY, ORDER BY, JOIN](https://121202.tistory.com/26)
- [[MSSQL] INSERT INTO 문.테이블에 데이터 추가하기](https://121202.tistory.com/25)
- [[SQL] ALTER TABLE 문. 테이블 수정하기](https://121202.tistory.com/27?category=541709)
