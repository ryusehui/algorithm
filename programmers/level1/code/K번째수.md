# K번째 수

> ## 목차
> * [문제](#문제)
> * [알고리즘](#알고리즘)
> * [코드](#코드)

## 문제
![문제](https://github.com/ryusehui/algorithm/blob/master/programmers/level1/problems/K%EB%B2%88%EC%A7%B8%20%EC%88%98.PNG)
<hr/>

## 알고리즘
commands의 길이만큼 for문을 돌면서 i, j, k에 각각 commands[][0], commands[][1], commands[][2] 저장   
조건에 맞게 요소를 뽑아 임시 배열에 저장 후 정렬   
정렬된 임시 배열에서 조건에 맞는 index에 있는 요소에 접근해 answer 배열에 저장
<hr/>

## 코드
### c++
```c++
#include <string>
#include <vector>
#include <algorithm>
using namespace std;
 
vector<int> solution(vector<int> array, vector<vector<int>> commands) {
    vector<int> answer;
    vector<int> tmp;
    
    for(int x=0; x<commands.size(); x++) {
        int i = commands[x][0]-1;
        int j = commands[x][1];
        int k = commands[x][2]-1;
        
        tmp.clear();
        for(int z=i; z<j; z++) {
            tmp.push_back(array[z]);
        }
        
        sort(tmp.begin(), tmp.end());
        
        answer.push_back(tmp[k]);
    }
    
    return answer;
}
```

### java
```java
import java.util.*;
 
class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];
        
        for(int x=0; x<commands.length; x++) {
            int index = 0;
            
            int i = commands[x][0]-1;
            int j = commands[x][1];
            int k = commands[x][2]-1;
            
            int tmp[] = new int[j-i];
            
            for(int z=i; z<j; z++) {
                tmp[index++] = array[z];
            }
            
            Arrays.sort(tmp);
            
            answer[x] = tmp[k];
        }
        
        return answer;
    }
}
```

### javascript
```javascript
function solution(array, commands) {
    var answer = [];
    
    for(let z=0; z<commands.length; z++) {
        let i = commands[z][0];
        let j = commands[z][1];
        let k = commands[z][2];
        let arr = [];
        for(let t=i-1; t<j; t++) arr.push(array[t]);
        arr = arr.sort((a,b)=>a-b);
        answer.push(arr[k-1]);
    }
    
    return answer;
}
```
