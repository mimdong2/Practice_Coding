[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/42747)

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


