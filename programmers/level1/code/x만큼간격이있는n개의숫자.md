# x만큼 간격이 있는 n개의 숫자

> ## 목차
> * [문제](#문제)
> * [알고리즘](#알고리즘)
> * [코드](#코드)

## 문제
![문제](https://github.com/ryusehui/algorithm/blob/master/programmers/level1/problems/x%EB%A7%8C%ED%81%BC%20%EA%B0%84%EA%B2%A9%EC%9D%B4%20%EC%9E%88%EB%8A%94%20n%EA%B0%9C%EC%9D%98%20%EC%88%AB%EC%9E%90.PNG)
<hr/>

## 알고리즘
배열의 0번째에 시작 숫자를 넣음   
n-1만큼 반복문을 돌면서 배열에 (이전 배열의 수 + 증가 수)를 넣어줌
<hr/>

## 코드
### c++
```c++
#include <string>
#include <vector>
 
using namespace std;
 
vector<long long> solution(int x, int n) {
    vector<long long> answer;
    int a = x;
    
    for(int i=0; i<n; i++) {
        answer.push_back(x);
        x+=a;
    }
    
    return answer;
}
```

### java
```java
class Solution {
  public long[] solution(int x, int n) {
      long[] answer = new long[n];
      answer[0] = x;
      
      for(int i=1; i<n; i++) {
          answer[i] = answer[i-1] + x;
      }
      
      return answer;
  }
}
```
