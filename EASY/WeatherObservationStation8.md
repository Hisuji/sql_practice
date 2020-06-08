# Weather Observation Station 8

🔒 [문제 보기](https://www.hackerrank.com/challenges/weather-observation-station-8/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT city
FROM station
WHERE REGEXP_LIKE (city, '^[aeiou].*[aeiou]$', 'i');
```

------

#### 💡 REGEXP_LIKE

- 정규표현식

|표현식|뜻|
|:---:|:---:|
|^|문자열의 시작|
|$|문자열의 종료|
|.|임의의 한 문자|
|*|0개 이상|


