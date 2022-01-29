# Partition Equal Subset Sum

```cpp
// Initial Template for C++

#include <bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
// User function Template for C++

class Solution{
public:

    bool subsetsum(int n,int arr[],int sum){
       vector<vector<bool>>dp(n+1,vector<bool>(sum+1,false));
       for(int i=0;i<n+1;i++){
           for(int j=0;j<1;j++){
               dp[i][j]=true;
           }
       }
       for(int i=1;i<n+1;i++){
           for(int j=1;j<sum+1;j++){
               if(arr[i-1]<=j){
                   dp[i][j] = (dp[i-1][j-arr[i-1]] or dp[i-1][j]);
               }
               else{
                   dp[i][j]=dp[i-1][j];
               }
           }
       }
       return dp[n][sum];
   }
   int equalPartition(int n, int arr[])
   {
       // code here
       int sum=0;
       for(int i=0;i<n;i++){
           sum+=arr[i];
       }
       if(sum%2){
           return 0;
       }
       else{
           if(subsetsum(n,arr,sum/2)){
               return 1;
           }
           return 0;
       }
   }
};

// { Driver Code Starts.

int main(){
    int t;
    cin>>t;
    while(t--){
        int N;
        cin>>N;
        int arr[N];
        for(int i = 0;i < N;i++)
            cin>>arr[i];

        Solution ob;
        if(ob.equalPartition(N, arr))
            cout<<"YES\n";
        else
            cout<<"NO\n";
    }
    return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/subset-sum-problem2014/1)
