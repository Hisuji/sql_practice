# Weather Observation Station 11

🔒 [문제 보기](https://www.hackerrank.com/challenges/weather-observation-station-11/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT DISTINCT(city)
FROM station
WHERE REGEXP_LIKE (city, '^[^aeiou]|[^aeiou]$', 'i');
```

------

#### 💡 REGEXP_LIKE

- 정규표현식

|표현식|뜻|
|:---:|:---:|
|[^a]|a를 제외한 모든 문자|
|\||OR|


