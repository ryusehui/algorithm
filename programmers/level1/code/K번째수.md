# K번째 수

> ## 목차
> * [문제](#문제)
> * [알고리즘](#알고리즘)
> * [코드](#코드)

## 문제
배열 array의 i번째 숫자부터 j번쨰 숫자까지 자르고 정렬했을 때, k번째에 있는 수를 구하기
> ex   
> array = [1, 5, 2, 6, 3, 7, 4] / i = 2, j = 5, k = 3
> 1. array의 2번째 부터 5번째까지 자르면 [5, 2, 6, 3]
> 2. 1에서 나온 배열을 정리하면 [2, 3, 5, 6]
> 3. 2에서 나온 배열의 3번째 숫자는 5

배열 array, i, j, k를 원소로 가진 2차원 배열 commands가 매개변수로 주어질 때, commands의 모든 원소에 대해서 실행한 결과는?

입력: 1차원 배열 array, 2차원 배열 commands
> ex   
> array = [1, 5, 2, 6, 3, 7, 4]   
> commands = [[2, 5, 3], [4, 4, 1], [1, 7, 3]]

출력: 결과 배열
> ex   
> [5, 3, 6]

조건
* array의 길이는 1 이상 100 이하
* array의 각 원소는 1 이상 100 이하
* commands의 길이는 1 이상 50 이하
* commands의 각 원소는 길이가 3
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
