# 💡 MySQL (MariaDB)

🔑 풀이 답안

1. 연봉이 12000 이상되는 직원들의 last_name 및 연봉 조회

```SQL
SELECT last_name, salary 
FROM employees 
WHERE salary > 12000;
```
2. 연봉 5000에서 12000의 범위 이외인 사람들의 last_name 및 연봉 조회

```SQL
SELECT last_name, salary 
FROM employees 
WHERE salary BETWEEN 5000 AND 12000;
```
3. 2018/06/20 ~ 2018/12/01 사이에 고용된 사원들의 last_name, 사번, 고용일자 조회(고용일자순 정렬)

```SQL
SELECT *
FROM employees
WHERE hire_date BETWEEN '2018-06-20' AND '2018-12-01';
```
4. 101번 및 120번 부서에서 근무하는 모든 사원들의 last_name 및 부서 번호를 알파벳순 조회

```SQL
SELECT last_name, department_id
FROM employees
WHERE department_id IN('0101', '0120')
ORDER BY last_name;
```
5. 101번 및 120번 부서에 근무하며 연봉이 5000 ~ 12000 사이인 사원들의 last_name 및 연봉 조회

```SQL
SELECT last_name, salary
FROM employees
WHERE department_id IN('0101', '0120')
  AND salary BETWEEN 5000 AND 12000 
ORDER BY last_name;
```
6. 2017년도에 고용된 모든 사람들의 last_name 및 고용일 조회

```SQL
SELECT last_name, hire_date
FROM employees
WHERE YEAR(hire_date) = '2017';
```
7. 매니저가 없는 사람들의 last_name 및 job_id 조회

```SQL
SELECT last_name, job_id
FROM employees
WHERE manager_id = '';
```
8. 매니저가 있는 사람들의 last_name 및 job_id 조회

```SQL
SELECT last_name, job_id
FROM employees
WHERE manager_id != '';
```
9. 'SEATEAL'에 사는 사람 중 커미션을 버는 모든 사람들의 last_name, 부서명, 지역 id 및 도시명 조회

```SQL
SELECT employees.LAST_NAME, employees.DEPARTMENT_ID, departments.LOCATION_ID, locations.CITY
FROM employees 
    JOIN departments ON employees.DEPARTMENT_ID = departments.DEPARTMENT_ID
    JOIN locations ON departments.LOCATION_ID = locations.LOCATION_ID
WHERE locations.CITY = 'SEATEAL';
```
10. last_name이 'Victoria'인 사람보다 후에 고용된 사원들의 last_name 및 hire_date 조회

```SQL
SELECT last_name, hire_date
FROM employees
WHERE hire_date > ( SELECT STR_TO_DATE(max(hire_Date), '%Y-%m-%d') 
						  FROM employees
						  WHERE UPPER(last_name) = 'Victoria');
```
11. 회사 전체의 최대 연봉, 최소 연봉, 연봉 총 합 및 평균 연봉을 자연수로 포맷하여 조회

```SQL
SELECT MAX(salary), MIN(salary), SUM(salary), ROUND(AVG(salary))
FROM employees;
```
12. 각 job_id 별, 최대 연봉, 최소연봉, 연봉 총 합 및 평균 연봉을 자연수로 포맷하여 조회

```SQL
SELECT job_id, MAX(salary), MIN(salary), SUM(salary), ROUND(AVG(salary))
FROM employees
GROUP BY job_id;
```
13. 사내의 최대 연봉 및 최소 연봉의 차이를 조회

```SQL
SELECT MAX(salary) - MIN(salary)
FROM employees;
```
14. 매니저로 근무하는 사원들의 총 수 조회

```SQL
SELECT COUNT(DISTINCT(MANAGER_ID))
FROM employees;
```
15. 매니저 및 사원들 중 최소 연봉을 받는 사원의 매니저의 사번과 연봉 조회, 매니저가 없는 사람들은 제외, 최소 연봉이 6000 미만인 경우 제외, 연봉 기준 역순으로 조회

```SQL

```
