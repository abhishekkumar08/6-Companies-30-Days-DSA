# Squares in N\*N Chessboard

```cpp

#include <bits/stdc++.h>
using namespace std;

 // } Driver Code Ends

class Solution {
  public:
    long long squaresInChessBoard(long long N) {
        // code here
        return (N*(N+1)*(2*N+1))/6;
    }
};

// { Driver Code Starts.
int main() {
    int t;
    cin >> t;
    while (t--) {
        long long N;

        cin>>N;

        Solution ob;
        cout << ob.squaresInChessBoard(N) << endl;
    }
    return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/squares-in-nn-chessboard1801/1)

## Time Complexity: O(1) Space Complexity: O(1)

## Explanation :

- If we take example for the values of n such as
  - n=1 output=1
  - n=2 output=5
  - n=3 output=14
- As visualised in the above code snippet, we can see that the number of squares in chessboard of size n*n is n*(n+1)*(2*n+1)/6. i.e.,The sum of squares of first n natural number.
