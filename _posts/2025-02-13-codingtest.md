---
title: "[codingtest] 배열의 평균값"
excerpt: "."

writer: Audrey
categories: [codingtest]

toc: true
toc_sticky: true

date: 2025-02-13 14:39:00 +09:00
last_modified_at: 2025-02-13 14:39:00 +09:00

tags: [codingtest]
---

**문제**

정수 배열 `numbers`가 매개변수로 주어집니다. `numbers`의 원소의 평균값을 return하도록 solution 함수를 완성해주세요.

### 내 코드

```java
class Solution {
    public double solution(int[] numbers) {
        
        int sum = 0;
        double answer = 0;
        for(int i = 0; i < numbers.length; i++) {
            sum += numbers[i];
        }
        answer = (double)sum / numbers.length;
        return answer;
    }
}
```

### 개선할 점

1. answer 변수 선언하지 않고 그냥 바로 return문에서 계산해서 반환한다.
2. 향상된 for문을 사용하면 더 코드가 간결해질 수 있다..!

```java
class Solution {
    public double solution(int[] numbers) {
        
        int sum = 0;
        for(int num : numbers) {
            sum += num;
        }
        return (double) sum / numbers.length;
    }
}
```