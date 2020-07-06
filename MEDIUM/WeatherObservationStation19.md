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

- 유클리드 공간에서 두 점 사이의 거리
  - 유클리드 공간
    - 유클리드가 연구했던 평면과 공간을 일반화한 것
    - 유클리드 기학의 5개의 공준이 성립하는 공간
      - 1) 두 점을 잇는 직선은 유일하다.
      - 2) 두 점을 잇는 선분은 무한대로 늘릴 수 있다. (직선으로 만들 수 있다.)
      - 3) 임의의 한 점과 임의의 길이를 반지름으로 하는 원을 그릴 수 있다.
      - 4) 모든 직각은 서로 같다.
      - 5) 한 직선이 두 직선과 만나고 같은 쪽에 있는 두 각의 합이 두 직각보다 작을 때, 두 직선을 끝없이 늘이면 두 직선은 그쪽에서 만난다.
 - (X<sub>1</sub>, Y<sub>1</sub>)와 (X<sub>2</sub>, Y<sub>2</sub>) 사이의 유클리디안 거리 측정하는 방법
   - &radic; (X<sub>2</sub> - X<sub>1</sub>)<sup>2</sup> + (Y<sub>2</sub> - Y<sub>1</sub>)<sup>2</sup>



#### 💡 Euclidean distance와 Manhattan distance 비교
- [월간조선 뉴스룸](http://monthly.chosun.com/client/news/viw.asp?ctcd=F&nNewsNumb=201708100056)
