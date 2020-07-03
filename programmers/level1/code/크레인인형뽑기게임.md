### c++
```
#include <string>
#include <vector>
 
using namespace std;
 
 int findDoll(vector<vector<int>> board, int move) {        
    for(int i=0; i<board.size(); i++) {
        if(board[i][move] != 0) {
            return i;
        }
    }
        
    return -1;
}
 
int solution(vector<vector<int>> board, vector<int> moves) {
    int answer = 0;
    vector<int> basket;
    int index = 0;
    
    for(int i=0; i<moves.size(); i++) {
        int find = findDoll(board, moves[i]-1);
        
        if(find != -1) {
            basket.push_back(board[find][moves[i]-1]);
            board[find][moves[i]-1] = 0;
            index++;
            if(index > 1) {
                if(basket[index-1] == basket[index-2]) {
                    basket.pop_back();
                    basket.pop_back();
                    index -= 2;
                    answer += 2;
                }
            }
        }
    }
    
    return answer;
}
```

### java
```
class Solution {
    public int solution(int[][] board, int[] moves) {
        int answer = 0;
        int[] basket = new int[900];
        int index = 0;
        
        for(int i=0; i<moves.length; i++) {
            int find = findDoll(board, moves[i]-1);
            
            if(find != -1) {
                basket[index] = board[find][moves[i]-1];
                board[find][moves[i]-1] = 0;
                index++;
                if(index > 1) {
                    if(basket[index-1] == basket[index-2]) {
                        basket[index-1] = 0;
                        basket[index-2] = 0;
                        index -= 2;
                        answer += 2;
                    }
                }
            }
        }
        
        return answer;
    }
    
    int findDoll(int[][] board, int move) {        
        for(int i=0; i<board.length; i++) {
            if(board[i][move] != 0) {
                return i;
            }
        }
        
        return -1;
    }
}
```

### javascript
```
function solution(board, moves) {
    var answer = 0;
    
    let basket = [];
    let index = 0;
    
    let i;
    for(i=0; i<moves.length; i++) {
        let find = findDoll(board, moves[i]-1);
        
        if(find != -1) {
            basket[index] = board[find][moves[i]-1];
            board[find][moves[i]-1] = 0;
            index++;
            
            if(index>1) {
                if(basket[index-1] == basket[index-2]) {
                    basket[index-1] = 0;
                    basket[index-2] = 0;
                    index -= 2;
                    answer += 2;
                }
            }
            
        }
    }
    
    return answer;
}
 
function findDoll(board, move) {      
    let i;
    for(i=0; i<board.length; i++) {
        if(board[i][move] != 0) {
            return i;
        }
    }
        
    return -1;
}
```
