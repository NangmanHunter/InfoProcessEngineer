# DDL
## CREATE TABLE
```sql
CREATE TABLE 테이블명
(속성명 데이터_타입 [DEFAULT 기본값] [NOT NULL], …
  [, PRIMARY KEY(기본키_속성명, …)]
  [, UNIQUE(대체키_속성명, …)]
  [, FOREIGN KEY(외래키_속성명, …)]
    [REFERENCES 참조테이블(기본키_속성명, …)]
    [ON DELETE 옵션]
    [ON UPDATE 옵션]
  [, CONSTRAINT 제약조건명] [CHECK (조건식)]);
```

Select
```sql
CREATE TABLE 신규테이블명 
AS SELECT 속성명[, 속성명, …] FROM 기존테이블명;
```

## CREATE VIEW
```sql
CREATE VIEW 뷰명[(속성명[, 속성명, …])]
AS SELECT문;
```

## ALTER TABLE
ADD
```sql
ALTER TABLE 테이블명 ADD 속성명 데이터_타입 [DEFAULT ‘기본값’];
```

ALTER | MODIFY
```sql
ALTER TABLE 테이블명 ALTER | MODIFY 속성명 [SET DEFAULT ‘기본값’];
```
- ```sql
  ALTER TABLE 테이블명 MODIFY 속성명 데이터타입;
  ```

DROP COLUMN
```sql
ALTER TABLE 테이블명 DROP COLUMN 속성명 [CASCADE];
```


## DROP TABLE
```sql
DROP TABLE 테이블명 [CASCADE | RESTRICT];
```