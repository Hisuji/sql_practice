# Weather Observation Station 20

🔒 [문제 보기](https://www.hackerrank.com/challenges/weather-observation-station-20/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT ROUND(MEDIAN(lat_n) , 4)
FROM station;
```

------

#### 💡 MEDIAN()

- MEDIAN(expr) [OVER(query_partition_clause)]
- 중앙값 반환
- NULL값 무시
- Oracle 10의 새로운 기능
  
  - 이전에는 PERCENTILE_CONT() 사용
- 자료의 개수 n이 홀수라면
  
  - <sup>n + 1</sup><sub>/2</sub> 번째의 값이 중앙값
- 자료의 개수 n이 짝수라면
  
  - <sup>n </sup><sub>/2</sub>, (<sup>n </sup><sub>/2</sub> + 1)번째의 값들의 평균이 중앙값
  



🍀 참고사이트

- [수학방](https://mathbang.net/116)



