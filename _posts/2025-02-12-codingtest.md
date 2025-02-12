---
title: "[codingtest] 짝수는 싫어요"
excerpt: "."

writer: Audrey
categories: [codingtest]

toc: true
toc_sticky: true

date: 2025-02-12 14:55:00 +09:00
last_modified_at: 2025-02-12 14:55:00 +09:00

tags: [codingtest]
---


**문제**

정수 `n`이 매개변수로 주어질 때, `n` 이하의 홀수가 오름차순으로 담긴 배열을 return하도록 solution 함수를 완성해주세요.

일단 n이하의 홀수를 구해야 하므로 2로 나누었을 때 0인지 아닌지에 따라 answer 배열에 요소들을 넣어준다. 이때 answer 배열의 크기를 정해야 하는데 n이 짝수인지 홀수인지에 달라지는 홀수의 개수들을 일반화 해서 배열의 크기를 설정한다.

### 내 코드

```java
class Solution {
    public int[] solution(int n) {

        int[] answer = {};

        if(n % 2 == 0) {
            answer = new int[n/2];
        } else {
            answer = new int[(n+1)/2];
        }
        
        int index = 0;
        for(int i = 1; i <= n; i++) {
            if(i % 2 != 0) {
                answer[index] = i;
                index++;
            }
        }
        return answer;
    }
}
```

### 개선할 점

1. 배열 크기 설정을 더 간결하게 하자.
    
    ```java
    answer = new int[(n+1) / 2];
    ```
    
    - n이 짝수든 홀수든 (n+1)/2하면 항상 원하는 크기가 나온다.

1. 반복문을 더 효율적으로 만들기
    - 현재 for(int i = 1; i ≤ n; i++)를 돌면서 if(i % 2 ≠ 0)으로 홀수를 판별했는데 애초에 for문을 2씩 증가하면 더 효율적이다.

### 개선한 코드

```java
class Solution {
    public int[] solution(int n) {
        int[] answer = new int[(n + 1) / 2]; // 배열 크기 설정 간단 수정정

        for (int i = 0, num = 1; num <= n; i++, num += 2) {
            answer[i] = num; // 2씩 증가시켜 홀수만 바로 저장했다.
        }

        return answer;
    }
}
```