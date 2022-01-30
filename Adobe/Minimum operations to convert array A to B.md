# Minimum operations to convert array A to B

```cpp
#include <bits/stdc++.h>
using namespace std;


 // } Driver Code Ends
//User function Template for C++

class Solution {
  public:
   //method of finding LCS using binary search
   int LCS(vector<int> co){
       vector<int>lcs;

       for(int i=0;i<co.size();i++){
           auto j=lower_bound(lcs.begin(),lcs.end(),co[i]);
           if(j!=lcs.end()){
              *j=co[i];
           }
           else{
               lcs.push_back(co[i]);
           }

       }
       return lcs.size();
   }
   int minInsAndDel(int A[], int B[], int N, int M) {
       vector<int>co;
       unordered_set<int>s;
       for(int i=0;i<M;i++){
           s.insert(B[i]);
       }
       for(int i=0;i<N;i++){
           if(s.find(A[i])!=s.end()){
               co.push_back(A[i]);
           }

       }
       return N+M-(2*LCS(co));
   }
};

// { Driver Code Starts.

int main() {
    int t;
    cin >> t;
    while (t--) {
        int N,M;
        cin>>N>>M;

        int A[N], B[M];
        for(int i=0; i<N; i++)
            cin>>A[i];
        for(int i=0; i<M; i++)
            cin>>B[i];

        Solution ob;
        cout << ob.minInsAndDel(A,B,N,M) << endl;
    }
    return 0;
}  // } Driver Code Ends

```

## [Question Link](https://practice.geeksforgeeks.org/problems/minimum-insertions-to-make-two-arrays-equal/1/)
