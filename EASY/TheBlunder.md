# The Blunder

🔒 [문제 보기](https://www.hackerrank.com/challenges/the-blunder/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT CEIL(AVG(SUM(salary)) - AVG(SUM(REPLACE(TO_CHAR(salary), '0', ''))))
FROM employees
GROUP BY id;
```

------

#### 💡 REPLACE

- REPLACE(char, search_string, replacement_string)
  - replacement_string 생략 시, char에서 search_string을 제거 한 문자열 반환

#### 💡 CEIL

- CEIL(n)
  - n과 같거나 가장 큰 정수 반환

![image](https://user-images.githubusercontent.com/47530310/86781877-6aa5c700-c099-11ea-87cf-a4986f699580.png)


##### 🍀 참고문헌
- [더북(TheBook) - 오라클 SQL과 PL/SQL을 다루는 기술](https://thebook.io/006696/part01/ch04/01/01/02/)