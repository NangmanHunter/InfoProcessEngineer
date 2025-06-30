# SubQuery
## SubQuery문
```sql
SELECT 이름, 주소
FROM 사원
WHERE  이름 = (SELECT 이름 FROM 여가활동 WHERE 취미 
              = ‘나이트댄스’) ;
```
