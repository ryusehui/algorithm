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
