### c++
```
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
```
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
