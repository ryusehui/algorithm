# N개의 최소공배수

> ## 목차
> * [문제](#문제)
> * [알고리즘](#알고리즘)
> * [코드](#코드)

## 문제
n개의 숫자를 담은 배열 arr이 주어질 때, 이 수들의 최소공배수 구하기

입력: 1차원 배열 arr
> ex   
> [2, 6, 8, 14]

출력: 최소공배수
> ex   
> 168

조건
* arr은 길이 1 이상 15 이하인 배열
* arr의 원소는 100 이하인 자연수
<hr/>

## 알고리즘
최소공배수를 구하기 위해 최대공약수를 구하는 함수를 사용한다.   
두 수 a와 b가 주어졌을 때 두 수의 최대공약수는 b가 0이 아닐동안 루프를 돌면서 a=b, b=a%b를 실행하고 b가 0이 되었을 떄의 a값이다.
두 수 a와 b의 최소공배수는 구해놓은 최대공약수로 axb를 나눈 값이다.
구한 값과 배열의 다음 원소를 사용해 최소공배수를 구해나간다.
<hr/>

## 코드
### c++
```c++
#include <string>
#include <vector>
 
using namespace std;
 
int gcd(int a, int b){
    while(b!=0){
        int r = a%b;
        a= b;
        b= r;
    }

    return a;
}
 
int lcm(int a, int b){
    return a * b / gcd(a,b);
}
 
int solution(vector<int> arr) {
    int answer = 0;
    
    answer = lcm(arr[0], arr[1]);
    
    for(int i=2; i<arr.size(); i++) {
        answer = lcm(answer, arr[i]);
    }
    
    return answer;
}
```

### java
```java
class Solution {
  public int gcd(int a, int b) {
      while(b!=0) {
          int r = a%b;
          a = b;
          b = r;
      }
      
      return a;
  }
    
  public int lcm(int a, int b) {
      return a*b / gcd(a, b);
  }
    
  public int solution(int[] arr) {
      int answer = 0;
      answer = lcm(arr[0], arr[1]);
      
      for(int i=2; i<arr.length; i++) {
          answer = lcm(answer, arr[i]);
      }
      
      return answer;
  }
}
```
