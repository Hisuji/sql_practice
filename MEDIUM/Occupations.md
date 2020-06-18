# Occupations

🔒 [문제 보기](https://www.hackerrank.com/challenges/occupations/problem)

🔑 풀이 답안 - Oracle

```SQL
SELECT
    Doctor, Professor, Singer, Actor
FROM
(
    SELECT name
           , occupation
           , ROW_NUMBER() OVER (PARTITION BY occupation ORDER BY name) AS num
    FROM occupations 
)
PIVOT
(
    MAX(name) 
    FOR occupation 
    IN ('Doctor' AS Doctor, 'Professor' AS Professor, 'Singer' AS Singer, 'Actor' AS Actor) 
) 
ORDER BY num;
```

------

#### 💡 ROW_NUMBER () OVER()

- ROW_NUMBER () OVER ([PARTITION BY value_exp, ... [n]] order_by_clause)
  - PARTITION BY에 작성된 column을 기준으로 파티션이 나뉘고 ORDER BY에 작성된 순서대로 각 파티션 결과 행에 대해 순서를 결정한다.
  - PARTITION BY를 지정하지 않은 경우 쿼리 집합 결과의 모든 행이 단일 그룹으로 취급된다.

#### 💡 PIVOT()

- Oracle 12c, Oracle 11g 버전에서 사용할 수 있다.

- ```
  PIVOT
  ( 
      aggregate_function(column) -- 집계할 열(집계함수 사용)
      FOR column -- 피벗할 기준 열(그룹화)
      IN (expr1, expr2, ... expr_n) | subquery  -- 피벗할 기준 열에 대한 필터 지정
  )
  ```

  - in 절에 alias 없이 column만 작성하면 출력 시 column에 작은따옴표가 앞뒤로 붙어 출력된다.

    즉, 메인 쿼리에서 조회 시 작은따옴표가 붙은 column 그대로 작성하면 컬럼으로 인식을 하지 못한다.

    - 작은따옴표가 붙은 column에 큰따옴표를 붙이면 column으로 인식된다.

  - ```
    SELECT
        "'Doctor'", "'Professor'", "'Singer'", "'Actor'" 
    FROM
    (
        SELECT name
               , occupation
               , ROW_NUMBER() OVER (PARTITION BY occupation ORDER BY name) AS num
        FROM occupations 
    )
    PIVOT
    (
        MAX(name) 
        FOR occupation 
        IN ('Doctor', 'Professor', 'Singer', 'Actor') 
    ) 
    ORDER BY num;
    ```

#### 💡 MAX(), MIN()

- 이 문제에서는 NULL 값이 아닌 값을 선택하기 위해 사용하였다.

  왜냐하면 MAX()와 MIN()은 비교 대상에서 NULL을 제외하기 때문이다. 

  단, 반환 row가 없으면 NULL을 반환한다.



