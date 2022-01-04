# Find the position of M-th item

```cpp


#include <bits/stdc++.h>
using namespace std;

 // } Driver Code Ends


class Solution {
  public:
    int findPosition(int N , int M , int K) {
       if (M <= N - K + 1)
        return M + K - 1;

        M = M - (N - K + 1);

        return (M % N == 0) ? N : (M % N);
    }
};

// { Driver Code Starts.
int main() {
    int t;
    cin >> t;
    while (t--) {
        int N,M,K;

        cin>>N>>M>>K;

        Solution ob;
        cout << ob.findPosition(N,M,K) << endl;
    }
    return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/find-the-position-of-m-th-item1723/1)

## Time Complexity: O(1) Space Complexity: O(1)

## Explantion:

- Visualise the ques by taking an example.
- We check if the number of items to be distributed is greater than our remaining positions in current cycle of circle or not. If yes, then we simply return m + k – 1 (We distribute items in same cycle starting from k). Else we compute number of remaining items after completing current cycle and return mod of remaining items.

