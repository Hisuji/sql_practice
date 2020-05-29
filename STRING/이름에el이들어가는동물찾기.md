## **이름에 el이 들어가는 동물 찾기**

🔒 [문제 보기](https://programmers.co.kr/learn/courses/30/lessons/59047)

🔑 풀이 답안 - Oracle

```SQL
SELECT animal_id, name
FROM animal_ins
WHERE animal_type = 'Dog'
      AND UPPER(name) like '%' || UPPER('el')|| '%'
ORDER BY name
```

------

#### 💡 Oracle 대소문자 구분 없이 검색하는 방법

- UPPER()
  - 소문자를 대문자로 변환
- LOWER()
  - 대문자를 소문자로 변환