# Weather Observation Station 14

🔒 [문제 보기](https://www.hackerrank.com/challenges/weather-observation-station-14/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT TRUNC(MAX(lat_n), 4)
FROM station
WHERE lat_n < 137.2345;
```

------

#### 💡 TRUNC()

- TRUNC(n1, n2)
  - n1을 n2 자리에서 절삭
  - n2가 음수인 경우 소수점 기준 왼쪽 방향으로 절삭

