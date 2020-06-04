# Weather Observation Station 3

🔒 [문제 보기](https://www.hackerrank.com/challenges/weather-observation-station-3/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT DISTINCT(city)
FROM station
WHERE MOD(id, 2) = 0;
```

------

#### 💡 MOD()

- MOD(Dividend, Divisor)
  - Dividend를 Divisor로 나눈 나머지 값을 반환

