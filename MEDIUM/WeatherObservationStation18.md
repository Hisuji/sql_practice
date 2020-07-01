# Weather Observation Station 18

🔒 [문제 보기](https://www.hackerrank.com/challenges/weather-observation-station-18/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT ABS(ROUND((MIN(station.lat_n) - MAX(station.lat_n)) 
           + (MIN(station.long_w) - MAX(station.long_w)), 4)) 
FROM station; 
```

------

#### 💡 Manhattan distance

- 
