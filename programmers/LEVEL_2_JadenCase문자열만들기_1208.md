[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/12951#)

## 풀이
- 풀 테스트 시, 런타임 에러로 모든 테스트 케이스를 통과하지 못했다.
- 사실 미완성 풀이다.
```java
import java.util.*;

class Solution {
    public String solution(String s) {
        String answer = "";
        
        // 주의) 공백문자가 연속해서 나올 수 있습니다.
        s = s.replaceAll("\\s+", " ");
        
        // 문자열을 공백문자 기준으로 쪼갠다. 즉 단어의 배열을 생성
        String[] words = s.split(" ");
        
        for (int i=0; i<words.length; i++) {
            answer += toJadenCase(words[i]);
            
            if (i < words.length-1) {
                answer += " ";
            }
        }
        
        return answer;
    }
    
    private String toJadenCase(String word) {
        char[] c = word.toCharArray();
        
        // 첫번째 문자
        if (!(c[0]>=48 && c[0]<=57)) {
            c[0] = Character.toUpperCase(c[0]);
        }
        
        for (int i=1; i<c.length; i++) {
            c[i] = Character.toLowerCase(c[i]);
        }
        
        String convert = new String(c);
        return convert;
    }
}
```

## 다른 사람 풀이
- 타 풀이자의 놀라운 풀이력을 보며 느낀것은, 문제 하나하나 조건마다 따지려는 것보다 때로는 아예 단순하게 생각해버리는 방법도 있다는 점!?!
```java
// Sunhee Shin , 조희준 , LimHanGyeol , wonsangki , 모아나 외 9 명
class Solution {
  public String solution(String s) {
        String answer = "";
        String[] sp = s.toLowerCase().split("");
        boolean flag = true;

        for(String ss : sp) {
            answer += flag ? ss.toUpperCase() : ss;
            flag = ss.equals(" ") ? true : false;
        }

        return answer;
  }
}
```
