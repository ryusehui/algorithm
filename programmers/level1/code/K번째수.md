### c++
```
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
```
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
```
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
