# Top Competitors

🔒 [문제 보기](https://www.hackerrank.com/challenges/full-score/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT a.hacker_id, a.name
FROM(  
    SELECT DISTINCT
      submissions.hacker_id, 
      COUNT(submissions.submission_id) OVER (PARTITION BY submissions.hacker_id) AS cnt, 
      hackers.name
    FROM 
       submissions, 
       challenges, 
       difficulty, 
       hackers
    WHERE submissions.score > 0
      AND submissions.challenge_id = challenges.challenge_id
      AND challenges.difficulty_level = difficulty.difficulty_level
      AND submissions.score = difficulty.score
      AND hackers.hacker_id = submissions.hacker_id
    ORDER BY cnt DESC, submissions.hacker_id ASC
) a
WHERE a.cnt >= 2;
```

------

#### 💡 OVER()

- 분석 함수
  - 행 그룹 기반으로 집계 값을 계산
  - 각 그룹에 대해 여러 행 반환
  - analytic_function(arguments) OVER(analytic_clause)
    - analytic_clause : 행 그룹 정의

#### 💡 PARTITION BY

- 집계 함수는 GROUP BY를 사용해 행을 그룹화하고 분석 함수는 PARTITION BY로 행을 그룹화한 후 질의 결과 분할
  - 집계 함수
    - 그룹별 계산을 수행하고 단일 값을 반환하며 GROUP BY 절에 의해 쿼리 결과 row 수가 줄어든다.
    - COUNT(*) 제외한 집계 함수는 Null 값 무시
  - 분석 함수
    - 그룹별 계산을 수행하고 여러 행을 반환하며 쿼리 결과 row 수가 줄어들지 않는다.
- PARTITION BY (expr)

