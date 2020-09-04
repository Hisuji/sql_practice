# SQL Project Planning

🔒 [문제 보기](https://www.hackerrank.com/challenges/sql-projects/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT CONNECT_BY_ROOT start_date, end_date
FROM projects
WHERE CONNECT_BY_ISLEAF = 1
START WITH start_date IN (SELECT start_date FROM projects 
                          MINUS 
                          SELECT end_date FROM projects)
CONNECT BY PRIOR end_date = start_date
ORDER BY LEVEL, start_date;
```

------

#### 💡 CONNECT_BY_ROOT

- 계층형 쿼리에서 최상위 로우의 정보를 반환하는 연산자



#### 💡 CONNECT_BY_ISLEAF

- CONNECT BY 조건에 정의된 관계에 따라 해당 로우가 최하위 자식 로우이면 1
- 그렇지 않으면 0을 반환하는 의사 컬럼



#### 💡 START WITH

- 계층형 쿼리의 루트 행 지정




#### 💡 CONNECT BY

- 계층형 쿼리에서 상위 행과 하위 행 사이의 관계 지정
- **PRIOR**
  - 상위 로우 값 참조
  - 이전 행의 end_date가 현재 행의 start_date인 관계



#### 💡 MINUS

- 차집합
- 첫번째 SELECT문 - 두번째 SELECT문



##### 🔍 Reference

[오라클 SQL과 PL/SQL을 다루는 기술](https://thebook.io/006696/)

