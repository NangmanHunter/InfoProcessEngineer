# SELECT
## SELECT문
```sql
SELECT [PREDICATE] [테이블명.]속성명 [AS 별칭]
  [, [테이블명.]속성명, …] 
  [, 그룹함수(속성명) [AS 별칭]]
FROM 테이블명[, 테이블명, …]
[WHERE 조건]
[GROUP BY 속성명, 속성명, …]
[HAVING 조건]
[ORDER BY 속성명 [ASC | DESC]];
```


PREDICATE
- ALL
- DISTINCT