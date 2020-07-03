### c++
```c++
#include <string>
#include <vector>
 
using namespace std;
 
string solution(string s) {
    string answer = "";
    vector<char> v;
    
    for(int i=0; i<s.length(); i++) {
        v.push_back(tolower(s[i]));
    }
    
    for(int i=0; i<v.size(); i++) {
        if((i!=0 && v[i-1] == ' ') || (i==0 && 'a' <= v[0] && v[0] <= 'z')) {
            answer += toupper(v[i]);
        }
        else answer += v[i];
    }
    
    return answer;
}
```

### java
```java
class Solution {
  public String solution(String s) {
      String answer = "";
      
      s = s.toLowerCase();
      String[] ss = s.split(" ");
      
      for(int i=0; i<ss.length; i++) {
          for(int j=0; j<ss[i].length(); j++) {
              if(j==0 && !Character.isDigit(ss[i].charAt(j))) {
                  answer += (char)(ss[i].charAt(0) - 32);
              }
              else {
                  answer += ss[i].charAt(j);
              }
          }
          if(i<ss.length-1) answer += " ";
      }
      
      if(s.substring(s.length()-1).equals(" ")) {
          answer += " ";
      }
      
      return answer;
  }
}
```
