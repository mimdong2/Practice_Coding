[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/131118)

## Lessons learned
### 반올림
- ROUND(숫자 혹은 열이름, 반올림할 자릿수)
- 반올림할 자릿수 : 0이 소수점 첫째 자리
> ROUND(3456.1234567)  
> \> 3456  
> ROUND(3456.1234567, 1)  
> \> 3456.1  
> ROUND(3456.1234567, 4)  
> \> 3456.1235  
> ROUND(3456.1234567, -1)  
> \> 3460  
> ROUND(3456.1234567, -2)  
> \> 3500  
### 버림
- TRUNC(숫자 혹은 열이름, 버림할 자릿수)
- 반올림할 자릿수 : 0이 소수점 첫째 자리
> TRUNC(3456.1234567)  
> \> 3456  
> TRUNC(3456.1234567, 4)  
> \> 3456.1234  
> TRUNC(3456.1234567, -1)  
> \> 3450  
> TRUNC(3456.1234567, -2)  
> \> 3400  

## 풀이
```sql
SELECT review.REST_ID REST_ID, info.REST_NAME REST_NAME, info.FOOD_TYPE FOOD_TYPE, info.FAVORITES FAVORITES, info.ADDRESS ADDRESS, ROUND(AVG(review.REVIEW_SCORE),2) SCORE
FROM REST_REVIEW review
INNER JOIN REST_INFO info
ON review.REST_ID = info.REST_ID
GROUP BY review.REST_ID
HAVING ADDRESS like '서울%'
ORDER BY SCORE DESC, FAVORITES DESC;
```
