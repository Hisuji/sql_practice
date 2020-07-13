# Top Earners

🔒 [문제 보기](https://www.hackerrank.com/challenges/earnings-of-employees/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT 
  MAX(months * salary), 
  COUNT(name)
FROM employee
WHERE 
  (months * salary) = (SELECT MAX(months * salary) FROM employee);
```

------

#### 💡 Subquery

- 외부 쿼리 내에서 SELECT 쿼리의 결과를 재사용할 수 있다.
  - 서브 쿼리가 먼저 실행된 후 외부 쿼리가 실행되기 때문에 서브 쿼리의 결과를 다른 쿼리에서 사용할 수 있다.
- 서브 쿼리는 괄호를 묶어 작성한다. 
- 서브 쿼리의 결과를 내부적으로 사용할 수 없으므로 ORDER BY 절을 추가할 수 없다.



