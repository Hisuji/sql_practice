# Weather Observation Station 19

🔒 [문제 보기](https://www.hackerrank.com/challenges/weather-observation-station-19/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT ROUND(SQRT(POWER((MAX(lat_n) - MIN(lat_n)), 2) 
                  + POWER((MAX(long_w) - MIN(long_w)), 2)), 4) 
FROM station;
```

------

#### 💡 Euclidean distance

