# Weather Observation Station 13

🔒 [문제 보기](https://www.hackerrank.com/challenges/weather-observation-station-13/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT ROUND(SUM(LAT_N), 4)
FROM station
WHERE LAT_N BETWEEN 38.7880 AND 137.2345;
```

------

#### 💡 BETWEEN

- 정규표현식
  - BETWEEN low AND high
    - 값이 지정된 범위에 있는 행만 리턴
    - value >= low AND vale <= high
