```
Expression #15 of SELECT list is not in GROUP BY clause and contains nonaggregated column 'path' which is not functionally dependent on columns in GROUP BY clause; this is incompatible with sql_mode=only_full_group_by
```

## 해결 방법

```sql
SET GLOBAL sql_mode=(SELECT REPLACE(@@sql_mode,'ONLY_FULL_GROUP_BY',''));
```

을 DB 서버에 접속하여 입력
