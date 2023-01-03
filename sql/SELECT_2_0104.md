[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/131120)

## Lessons learned
### 날짜에서 일부만 추출하기
날짜 값을 파싱하여 조건으로 가져가야 하는 경우가 있다. (예. 생일이 3월인 사람 조회)
아래 함수를 이용하여 날짜 데이터에서 일부만을 추출할 수 있다.
- YEAR(기준날짜);
- MONTH(기준날짜);
- DAY(기준날짜);
- HOUR(기준날짜);
- MINUTE(기준날짜);
- SECOND(기준날짜);
기준날짜를 '2023-01-04 12:30:45'인 경우,
> SELECT YEAR(2023-01-04 12:30:45);  
> \> 2023  
> SELECT MONTH(2023-01-04 12:30:45);  
> \> 1  
> SELECT DAY(2023-01-04 12:30:45);  
> \> 4  
> SELECT HOUR(2023-01-04 12:30:45);  
> \> 12  
> SELECT MINUTE(2023-01-04 12:30:45);  
> \> 30  
> SELECT SECOND(2023-01-04 12:30:45);  
> \> 45  


### IS NULL, IS NOT NULL
컬럼값이 NULL 이거나 NULL이 아닌 값 불러올 수 있다.
> WHERE column1 IS NULL  
> WHERE column2 IS NOT NULL 


## 풀이
```sql
SELECT MEMBER_ID, MEMBER_NAME, GENDER, DATE_FORMAT(DATE_OF_BIRTH, '%Y-%m-%d') DATE_OF_BIRTH
FROM MEMBER_PROFILE
-- WHERE DATE_FORMAT(DATE_OF_BIRTH, '%m') = 03
WHERE MONTH(DATE_OF_BIRTH) = 3
AND GENDER = 'W'
AND TLNO is NOT NULL
ORDER BY MEMBER_ID;
```
