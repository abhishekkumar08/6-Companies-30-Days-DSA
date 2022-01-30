# Unit Area of largest region of 1's

```cpp
#include<bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution
{
    public:
    //Function to find unit area of the largest region of 1s.
    int as=1;
    int dx[8]={0,-1,-1,-1,0,1,1,1};
    int dy[8]={1,1,0,-1,-1,-1,0,1};

    void dfs(int i,int j,vector<vector<int>> &grid){
           if(i < 0 || j<0 || i >= grid.size() || j >= grid[0].size() || grid[i][j] == 0 ){
               return;
           }
           as++;
           grid[i][j]=0;
           for(int d=0;d<8;d++){
               dfs(i+dx[d],j+dy[d],grid);
           }
       }
   int findMaxArea(vector<vector<int>>& grid) {
       int c=0;
       for(int i=0;i<grid.size();i++){
           for(int j=0;j<grid[0].size();j++){
               as=0;
               if(grid[i][j]==1){
                   dfs(i,j,grid);
                   c=max(c,as);
               }
           }
       }
       return c;
   }
};

// { Driver Code Starts.
int main(){
	int tc;
	cin >> tc;
	while(tc--){
		int n, m;
		cin >> n >> m;
		vector<vector<int>>grid(n, vector<int>(m, -1));
		for(int i = 0; i < n; i++){
			for(int j = 0; j < m; j++){
				cin >> grid[i][j];
			}
		}
		Solution obj;
		int ans = obj.findMaxArea(grid);
		cout << ans << "\n";
	}
	return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/length-of-largest-region-of-1s-1587115620/1/)
