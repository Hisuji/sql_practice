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

- 직각으로 축을 따라 측정 된 두 점 사이의 거리
  -  (X<sub>1</sub>, Y<sub>1</sub>)와 (X<sub>2</sub>, Y<sub>2</sub>) 사이의 맨하튼 거리 측정하는 방법
    - (X<sub>1</sub> - X<sub>2</sub>) + (Y<sub>1</sub> - Y<sub>2</sub>)



🍀 참고사이트

- [101computing](https://www.101computing.net/manhattan-distance-calculator/)

