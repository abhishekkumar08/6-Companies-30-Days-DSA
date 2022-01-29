# Word Search

```cpp
#include<bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution {
public:

    bool searchWord(int i, int j, int index, string word, vector<vector<char>>& board,vector<vector<bool>>& visited) {
      if(index==word.length())
        return true;

    if(i<0 || i>=board.size() || j<0 || j>=board[i].size()  || word[index]!=board[i][j] || visited[i][j])
        return false;


    visited[i][j]=true;

    if(searchWord(i+1, j, index+1, word, board, visited)||
        searchWord(i-1, j, index+1, word, board, visited)||
        searchWord(i, j-1, index+1, word, board, visited)||
        searchWord(i, j+1, index+1, word, board, visited))
        return true;

    visited[i][j]=false;
    return false;
    }
    bool isWordExist(vector<vector<char>>& board, string word) {
       int rows=board.size();
       int columns=board[0].size();

       vector<vector<bool>> visited(rows,vector<bool>(columns,false));

       for(int i=0;i<rows;i++){
           for(int j=0;j<columns;j++)
            if(word[0]==board[i][j] && searchWord(i,j,0,word,board, visited))
                return true;
       }
       return false;
    }
};

// { Driver Code Starts.
int main(){
	int tc;
	cin >> tc;
	while(tc--){
		int n, m;
		cin >> n >> m;
		vector<vector<char>>board(n, vector<char>(m, '*'));
		for(int i = 0; i < n; i++)
			for(int j = 0; j < m; j++)
				cin >> board[i][j];
		string word;
		cin >> word;
		Solution obj;
		bool ans = obj.isWordExist(board, word);
		if(ans)
			cout << "1\n";
		else cout << "0\n";
	}
	return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/word-search/1/)
