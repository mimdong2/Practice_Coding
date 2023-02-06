[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/12916)

## 초기 풀이
```java
class Solution {
    boolean solution(String s) {

        char[] charArray = s.toCharArray();
        int countP = 0;
        int countY = 0;
        
        for (int i=0; i<charArray.length; i++) {
            if (charArray[i] == 'p' || charArray[i] == 'P') {
                countP++;
            }
            if (charArray[i] == 'y' || charArray[i] == 'Y') {
                countY++;                
            }
        }
        
        return (countP==countY) ? true : false;
    }
}
```

## 다른 풀이 참고
```java
class Solution {
    boolean solution(String s) {

        s = s.toLowerCase();
        int count = 0;
        
        for (int i=0; i<s.length(); i++) {
            if (s.charAt(i) == 'y') {
                count++;
            } else if (s.charAt(i) == 'p') {
                count--;
            }
        }
        
        return (count==0) ? true : false;
    }
}
```

## 다른 풀이 참고
- 리소스 낭비라고 하나 람다를 써서 다르게 접근한게 신기했다.
```java
class Solution {
    boolean solution(String s) {
        s = s.toUpperCase();

        return s.chars().filter( e -> 'P'== e).count() == s.chars().filter( e -> 'Y'== e).count();
    }
}
```
