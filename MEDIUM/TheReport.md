# The Report

🔒 [문제 보기](https://www.hackerrank.com/challenges/the-report/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT
   CASE WHEN grades.grade > 7 THEN students.name ELSE 'NULL' END AS name
    , grades.grade
    , students.marks
FROM students, grades
WHERE students.marks BETWEEN grades.min_mark AND grades.max_mark
ORDER BY grades.grade DESC, name, students.marks;
```

```SQL
SELECT *
FROM(
    SELECT students.name AS name, grades.grade AS grade, students.marks AS marks
    FROM students, grades
    WHERE students.marks BETWEEN grades.min_mark AND grades.max_mark
        AND grades.grade > 7
    UNION
    SELECT 'NULL' AS name, grades.grade AS grade, students.marks AS marks
    FROM students, grades
    WHERE students.marks BETWEEN grades.min_mark AND grades.max_mark
        AND grades.grade <= 7
)
ORDER BY grade DESC, name, marks;
```

------

#### 💡  UNION()
- 분리된 둘 이상의 SQL 쿼리를 병합

  - 각각 쿼리의 조회 컬럼 순서와 개수, 데이터 타입이 같아야 병합 가능
  - 중복된 행은 제외

#### 💡  Combining ORDER BY and UNION
- 첫 번째 방법) SELECT * FROM으로 감싼 후 ORDER BY 사용 - 정렬 기준은 첫 번째 쿼리의 컬럼명, 두 번째 쿼리의 컬럼명 인식X

```
SELECT *
FROM(
    SELECT column1 AS col1
    FROM table1
    UNION 
    SELECT column1
    FROM table2
)
ORDER BY col1;
```

- 두 번째 방법) 두 번째 쿼리에서 ORDER BY 사용 - 정렬 기준은 첫 번째 쿼리의 컬럼명

```
SELECT column1 AS col1
FROM table1
UNION 
SELECT column1
FROM table2
ORDER BY col1;
```

