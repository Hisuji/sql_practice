# Contest Leaderboard

🔒 [문제 보기](https://www.hackerrank.com/challenges/contest-leaderboard/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT a.hacker_id, a.name, a.score
FROM (
    SELECT DISTINCT 
        hackers.hacker_id AS hacker_id, 
        hackers.name AS name, 
        SUM(MAX(submissions.score)) OVER(PARTITION BY hackers.hacker_id) AS score
    FROM hackers, submissions
    WHERE submissions.hacker_id = hackers.hacker_id
    GROUP BY hackers.hacker_id, hackers.name, submissions.challenge_id
    ORDER BY score DESC, hacker_id ASC
)a
WHERE a.score != 0;
```

------



