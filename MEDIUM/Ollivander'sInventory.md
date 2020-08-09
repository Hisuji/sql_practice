# Ollivander's Inventory

🔒 [문제 보기](https://www.hackerrank.com/challenges/harry-potter-and-wands/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT 
  wand.id,
  a.age,
  a.coin,
  a.power
FROM Wands wand,( 
  SELECT 
    wands_property.age AS age, 
    MIN(wands.coins_needed) AS coin, 
    wands.power AS power,
    wands.code As code
  FROM wands, wands_property
  WHERE wands.code = wands_property.code
    AND wands_property.is_evil != 1
  GROUP BY wands_property.age, wands.power, wands.code
) a
WHERE wand.code = a.code
  AND wand.coins_needed = a.coin
ORDER BY a.power DESC, a.age DESC;
```

------

#### 💡 GROUP BY

- GROUP BY expression1, expression2, ... expression_n
- GROUP BY 절에서 여러 레코드를 그룹화해 SELECT 문에서 사용한다.
- SELECT 문에 작성된 컬럼의 경우 집계함수를 제외하고는 GROUP BY 절에 모두 작성해줘야 'not a GROUP BY expression' 에러가 발생하지 않는다.

