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

#### 💡 SET SERVEROUTPUT ON

- PL/SQL에서 DBMS_OUTPUT 패키지에 의해 생성된 메시지 출력 인쇄 여부 ( 기본값 : OFF )
  - 즉, PL/SQL은 기본적으로 출력이 표시되지 않는데 ON으로 설정 시 출력

#### 💡 PL/SQL - Block Structure

- ```
  DECLARE -- 선언부
    -- 변수, 상수, CURSOR, USER_DEFINE Exception 선언
  BEGIN -- 실행부 *필수
    -- SQL, 반복분, 조건문 실행
    -- 실행부는 BEGIN으로 시작하고 END로 종료
  EXCEPTION -- 예외처리부
    -- 예외에 대한 처리
  END; -- *필수
  ```
  
#### 💡 FOR LOOP 반복문

- ```
  FOR 인덱스 IN [REVERSE] 초기값..최종값
  LOOP
    -- 처리문
  END LOOP;
  ```

  - 인덱스는 초깃값에서 최종값까지 루프 돌며 1씩 증가(＋)
  - REVERSE는 최종값에서 초깃값까지 루프 돌며 1씩 감소(－)




##### 🔎 Reference

- [구루비](http://www.gurubee.net/lecture/1342)
- [더북](https://thebook.io/006696/part02/ch09/01/05/)