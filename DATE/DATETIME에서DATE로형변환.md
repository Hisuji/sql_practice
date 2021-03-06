## **DATETIME에서 DATE로 형 변환**

🔒 [문제 보기](https://programmers.co.kr/learn/courses/30/lessons/59414)

🔑 풀이 답안 - Oracle

```SQL
SELECT animal_id, name, TO_CHAR(datetime, 'yyyy-mm-dd')
FROM animal_ins
ORDER BY animal_id
```

------

#### 💡 TO_CHAR()

- DATE, DATETIME, TIMESTAMP, NUMBER 등의 데이터 타입을 VARCHAR2로 변환한다.
- 날짜 변환 형식
  - YYYY : 4자리 연도
  - MM :  01 ~ 12 형태로 월 표시
  - DD : 01 ~ 31 형태로 일 표시
  - HH : 01 ~ 12 형태로 시간 표시
    - HH24 : 00 ~ 23 형태로 시간 표시
  - MI : 00 ~ 59 형태로 분 표시
  - SS : 00 ~ 59 형태로 초 표시