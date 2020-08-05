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

#### 💡 PARTITION BY

