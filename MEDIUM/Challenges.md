# Challenges

🔒 [문제 보기](https://www.hackerrank.com/challenges/challenges/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT a.hacker_id, a.name, a.cnt_challenge
FROM(
      SELECT 
          challenges.hacker_id AS hacker_id, 
          hackers.name AS name, 
          COUNT(challenges.challenge_id) AS cnt_challenge,
          LAG(COUNT(challenges.challenge_id)) OVER (ORDER BY COUNT(challenges.challenge_id)) AS previos_row,
          LEAD(COUNT(challenges.challenge_id)) OVER (ORDER BY COUNT(challenges.challenge_id)) AS next_row
      FROM hackers, challenges
      WHERE challenges.hacker_id = hackers.hacker_id
      GROUP BY challenges.hacker_id, hackers.name
      ORDER BY cnt_challenge DESC, challenges.hacker_id
)a
WHERE a.cnt_challenge != a.previos_row
  AND a.next_row != a.cnt_challenge
  OR a.cnt_challenge = (
                         SELECT MAX(COUNT(challenges.challenge_id)) 
                         FROM hackers, challenges
                         WHERE challenges.hacker_id = hackers.hacker_id
                         GROUP BY challenges.hacker_id
                       );
```

------

#### 💡 LAG()

- 현재 행 기준 이전 행에 엑세스 가능
- `LAG(expression [, offset ] [, default ]) OVER ( [ query_partition_clause ]  order_by_clause )`
  - offset 기본 값 : 1
  - default : offset이 테이블 범위를 벗어나면 기본 값 반환, 생략 시 NULL 반환
  - query_partition_clause : LAG() 함수가 적용될 파티션
  - order_by_clause : LAG() 함수가 적용되는 파티션의 행 순서 지정

#### 💡 LEAD() 
- 현재 행 기준 다음 행에 엑세스 가능
- `LEAD(expression [, offset ] [, default ]) OVER ( [ query_partition_clause ]  order_by_clause )`
