[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/42747)

## Lessons learned
### 문제의 핵심을 정확하게 파악해야 한다.
전체 논문의 인용 횟수를 값으로 가진 배열에서,  
"전체 n 편의 논문 중 h회 이상 인용 된 논문이 h편 이상"이다.  
#### 풀이
1. 인용횟수를 값으로 가진 배열을 정렬
> Arrays.sort(배열);      // 오름차순 정렬
2. "h > h회 이상 인용된 논문 개수" 를 부합하는 h의 최대 값
> 배열요소 값 > h회 이상 인용된 논문 개수

## 
```java
import java.util.*;

class Solution {
    public int solution(int[] citations) {

        // 오름차순 정렬 (0,1,3,5,6)
        Arrays.sort(citations);
        
        int answer = 0;
        
        for (int i=0; i<citations.length; i++) {
            int h = citations.length - i;   // 논문 개수
            
            if (citations[i] >= h) {
                answer = h;
                break;
            }
        }
        
        return answer;

    }
}
```

## 1차 풀이
테스트 케이스는 성공했으나, 문제 제출 시 시간 초과 발생
```java
import java.util.*;

class Solution {
    public int solution(int[] citations) {

        // 오름차순 정렬 (0,1,3,5,6)
        Arrays.sort(citations);
        // H-Index
        int h = 0;

        for (int i=0; ;i++) {
            h += i;

            // H-Index 보다 작거나 같은 논문 수
            int down = 0;
            int up = 0;

            for (int j=0; j<citations.length; j++) {
                if (h>citations[j]) {
                    down ++;
                } else if (h==citations[j]){
                    down ++;
                    up ++;
                } else {
                    up ++;
                }
            }

            if (down == up && down == h) {
                break;
            } else {
                continue;
            }

        }

        return h;
    }
}
```


