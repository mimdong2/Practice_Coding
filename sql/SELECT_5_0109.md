[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/131537)

## Lessons learned
### UNION ALL, UNION
- UNION ALL : 두개 이상의 쿼리문을 합칠 수 있다. 
- UNION :  두개 이상의 쿼리문을 합칠 수 있다. 다만 UNION ALL과 다른 점은, 중복되는 로우는 하나만 출력된다.

## 풀이
```sql
SELECT DATE_FORMAT(SALES_DATE,'%Y-%m-%d') AS SALES_DATE, PRODUCT_ID, NULL AS USER_ID, SALES_AMOUNT
FROM OFFLINE_SALE
WHERE DATE_FORMAT(SALES_DATE,'%Y-%m') = '2022-03'

UNION ALL

SELECT DATE_FORMAT(SALES_DATE,'%Y-%m-%d') AS SALES_DATE, PRODUCT_ID, USER_ID, SALES_AMOUNT
FROM ONLINE_SALE
WHERE DATE_FORMAT(SALES_DATE,'%Y-%m') = '2022-03'

ORDER BY SALES_DATE, PRODUCT_ID, USER_ID;
```
