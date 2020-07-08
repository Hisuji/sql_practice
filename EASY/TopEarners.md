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

- 
