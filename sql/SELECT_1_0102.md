[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/132203)

## Lessons learned
### 다중정렬(ORDER BY 여러개)
왼쪽부터 순차적으로 정렬되므로 순서를 고려해야 한다. (즉, 우선순위가 높은 순서대로 나열)
> ORDER BY column1 desc, column2; 라면  
> column1을 기준으로 내림차순으로 정렬 후,  
> column1이 같은 값에 한하여 column2로 오름차순으로 정렬한다.

### 날짜 형식 변환
DATE_FORMAT(date, format)으로 날짜 형식을 변환할 수 있다.
- %Y : 4자리 연도
- %y : 2자리 연도
- %M : 월의 이름(January, February …)
- %m : 2자리 월(00, 01, … ,12)
- %D : 일(1st, 2nd, …)
- %d : 2자리 일(00, 01, … , 31)
> SELECT DATE_FORMAT('20230405', '%Y/%m/%d')  
> \> 2023/04/05  
> SELECT DATE_FORMAT('20230405', '%Y-%m-%d')  
> \> 2023-04-05


## 풀이
```sql
SELECT DR_NAME, DR_ID, MCDP_CD, DATE_FORMAT(HIRE_YMD, '%Y-%m-%d') HIRE_YMD
FROM DOCTOR
WHERE MCDP_CD IN ('CS', 'GS')
ORDER BY HIRE_YMD DESC, DR_NAME;
```
