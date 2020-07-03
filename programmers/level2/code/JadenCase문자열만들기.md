# JadenCase 문자열 만들기

> ## 목차
> * [문제](#문제)
> * [알고리즘](#알고리즘)
> * [코드](#코드)

## 문제
JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열이다.   
문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 구하기

입력: 문자열 s
> ex   
> "3people unFollowed me"

출력: JadenCase로 바꾼 문자열
> ex   
> "3people Unfollowed Me"

조건
* s는 길이 1 이상인 문자열
* s는 알파벳과 공백문자(" ")로 이루어져 있음
* 첫 문자가 영문이 아닐때에는 이어지는 영문은 소문자로 씀
<hr/>

## 알고리즘
입력 문자열 s를 소문자로 치환 후 공백을 포함한 모든 문자를 배열에 저장한다.   
배열의 0번째 문자열이 영문이라면 대문자로 바꿔주고, 공백 문자 뒤의 문자가 영문이라면 대문자로 바꿔준다.   
배열의 모든 문자를 문자열에 저장해 리턴
<hr/>

## 코드
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
