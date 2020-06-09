# Higher Than 75 Marks

🔒 [문제 보기](https://www.hackerrank.com/challenges/more-than-75-marks/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT name
FROM students
WHERE marks > 75
ORDER BY SUBSTR(name, -3), id;
```

------

#### 💡 SUBSTR()

- 문자열을 자를 때 사용하는 함수
- SUBSTR(char, position, substring_length)
  - char 문자에 대해 position부터 시작해 substring_length만큼 반환하다.
  - substring_length 생략한 경우, position부터 문자 끝까지 반환하다.
  - position이 음수인 경우, 끝에서부터 계산한다.
