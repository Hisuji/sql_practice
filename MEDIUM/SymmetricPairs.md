# Symmetric Pairs

🔒 [문제 보기](https://www.hackerrank.com/challenges/symmetric-pairs/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT fun.x, fun.y
FROM Functions fun, functions funs
WHERE fun.x = funs.y
  AND fun.y = funs.x
GROUP BY fun.x, fun.y
HAVING COUNT(fun.x) > 1 OR fun.x < fun.y
ORDER BY fun.x;
```

------



