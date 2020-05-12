## NULL 처리하기

🔒 [문제 보기](https://programmers.co.kr/learn/courses/30/lessons/59410)

🔑 풀이 답안 - Oracle

```SQL
SELECT animal_type, NVL(name,'No name') name, sex_upon_intake
FROM animal_ins
ORDER BY animal_id
```

------

#### 💡 NULL 관련함수

- NVL(expr1, expr2)
    - expr1의 값이 <span style="color:red">NULL이면 expr2를 반환</span>, expr1의 값이 <span style="color:blue">NULL이 아니면 expr1을 반환</span>
- NVL2(expr1, expr2, expr3)
     - expr1의 값이 <span style="color:red">NULL이면 expr3를 반환</span>, expr1의 값이 <span style="color:blue">NULL이 아니면 expr2을 반환</span>


