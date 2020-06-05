# Weather Observation Station 6

🔒 [문제 보기](https://www.hackerrank.com/challenges/weather-observation-station-6/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT DISTINCT(city)
FROM station
WHERE REGEXP_LIKE(city, '^a|^e|^i|^o|^u', 'i');
```

------

#### 💡 REGEXP_LIKE

- 정규식 함수
  - Oracle 10g 이상부터 가능
  - REGEXP_LIKE(source_string, pattern, match_parameter)
    - source_string
      - 검색 값으로 사용되는 문자 표현식
    - pattern
      - 정규표현식
    - match_parameter
      - i : 대소문자 구분X
      - c : 대소문자 구분
      - m : source_string이 다중 라인의 문자열인 경우 한 줄로 취급


