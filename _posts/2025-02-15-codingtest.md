---
title: "[codingtest] 문자열 뒤집기"
excerpt: "."

writer: Audrey
categories: [codingtest]

toc: true
toc_sticky: true

date: 2025-02-15 14:20:00 +09:00
last_modified_at: 2025-02-14 14:20:00 +09:00

tags: [codingtest]
---

문제

문자열 `my_string`이 매개변수로 주어집니다. `my_string`을 거꾸로 뒤집은 문자열을 return하도록 solution 함수를 완성해주세요.

### 내 코드

```java
class Solution {
    public String solution(String my_string) {
        
    String answer = "";
    StringBuilder builder = new StringBuilder();
    
    char[] eng = new char[my_string.length()];
    
    for(int i = 0; i < eng.length; i++) {
      eng[i] = my_string.charAt(i);
    }
    
    for(int j = eng.length - 1; j >= 0; j--) {
      builder.append(eng[j]); 
    }
    
    return builder.toString();
    }
}
```

### 개선할 점

굳이 char[] eng 배열을 생성해서 따로 저장할 필요는 없다. StringBuilder를 직접 활용하면 된다. 그리고 StringBuilder에는 reverse() 메서드가 있어서 직접 뒤집는 기능을 제공한다. 

### 개선한 코드

```java
class Solution {
    public String solution(String my_string) {
        return new StringBuilder(my_string).reverse().toString();
    }
}
```

- 다음번엔 활용할 수 있는 내장 메소드를 찾아보고 해야겠다는 생각이 든다…