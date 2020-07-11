# 문자열 내 p와 y의 개수

> ## 목차
> * [문제](#문제)
> * [알고리즘](#알고리즘)
> * [코드](#코드)

## 문제
![문제](https://github.com/ryusehui/algorithm/blob/master/programmers/level1/problems/%EB%AC%B8%EC%9E%90%EC%97%B4%20%EB%82%B4%20p%EC%99%80%20y%EC%9D%98%20%EA%B0%9C%EC%88%98.PNG)
<hr/>

## 알고리즘

<hr/>

## 코드
### c++
```c++
#include <string>
#include <iostream>
using namespace std;
 
bool solution(string s)
{
    int p = 0;
    int y = 0;
    
    for(int i=0; i<s.length(); i++) {
        if(s[i] == 'p' || s[i] == 'P')
            p++;
        else if(s[i] == 'y' || s[i] == 'Y')
            y++;
    }
    
    if(p == y) return true;
    else return false;
}
```

### java
```java
class Solution {
    boolean solution(String s) {
        int p = 0;
        int y = 0;
    
        for(int i=0; i<s.length(); i++) {
            if(s.charAt(i) == 'p' || s.charAt(i) == 'P')
                p++;
            else if(s.charAt(i) == 'y' || s.charAt(i) == 'Y')
                y++;
        }
 
        if(p == y) return true;
        else return false;
    }
}
```
