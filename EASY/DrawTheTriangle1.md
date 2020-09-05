# Draw The Triangle 1

🔒 [문제 보기](https://www.hackerrank.com/challenges/draw-the-triangle-1/problem)

🔑 풀이 답안 - Oracle

```SQL
SET SERVEROUTPUT ON
BEGIN
  FOR i IN REVERSE 1..20
  LOOP
    DBMS_OUTPUT.PUT_LINE(REPLACE(RPAD('*', i, '*'), '*', ' * '));
  END LOOP; 
END; 
/
```

------

