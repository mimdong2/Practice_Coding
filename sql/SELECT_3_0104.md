[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/131536)

## 풀이
```sql
SELECT USER_ID, PRODUCT_ID
FROM ONLINE_SALE
GROUP BY USER_ID, PRODUCT_ID
HAVING count(*) >= 2
ORDER BY USER_ID, PRODUCT_ID DESC;
```
