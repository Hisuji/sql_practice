# SQL Project Planning

🔒 [문제 보기](https://www.hackerrank.com/challenges/sql-projects/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT CONNECT_BY_ROOT start_date, end_date
FROM projects
WHERE CONNECT_BY_ISLEAF = 1
START WITH start_date IN (SELECT start_date FROM projects MINUS SELECT end_date FROM projects)
CONNECT BY PRIOR end_date = start_date
ORDER BY LEVEL, start_date;
```

------

#### 💡 CONNECT_BY_ROOT

- 



#### 💡 CONNECT_BY_ISLEAF

- 



#### 💡 START WITH

- 




#### 💡 CONNECT BY

- 



#### 💡 MINUS

- 
