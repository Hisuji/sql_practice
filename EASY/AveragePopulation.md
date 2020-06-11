# Average Population

🔒 [문제 보기](https://www.hackerrank.com/challenges/average-population/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT ROUND(AVG(population))
FROM city;
```

------

#### 💡 ROUND()

- 소수점 반올림 함수
- ROUND(n, integer)
  - integer : 소수점 몇 번째 자리로 반올림하는지 지정한다.
    - 디폴트 값은 0
    - 1 : 소수점 첫 번째 자리로 반올림
    - -1 : 소수점 왼쪽 첫 번째 자리에서 반올림



