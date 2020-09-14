# Placements

🔒 [문제 보기](https://www.hackerrank.com/challenges/placements/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT students.name
FROM friends, packages friendPack, students, packages myPack
WHERE friends.friend_id = friendPack.id
  AND friends.id = students.id
  AND students.id = myPack.id
  AND friendPack.salary > myPack.salary
ORDER BY friendPack.salary;
```

------

