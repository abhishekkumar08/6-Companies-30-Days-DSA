# IPL 2021 - Match Day 2

```cpp
#include <bits/stdc++.h>
using namespace std;


 // } Driver Code Ends
class Solution {
  public:
    vector<int> max_of_subarrays(vector<int> arr, int n, int k) {
         deque<int>dq(k);
       vector<int>ans;

       int i;

       for(i=0;i<k;++i){
           while(!dq.empty() && arr[i]>=arr[dq.back()]){
               dq.pop_back();
           }
           dq.push_back(i);

       }

       for(;i<n;++i){
           ans.push_back(arr[dq.front()]);

           //shift to new window
           while(!dq.empty() && dq.front()<=i-k){
               dq.pop_front();
           }

           while(!dq.empty() && arr[i]>=arr[dq.back()]){
               dq.pop_back();
           }

           dq.push_back(i);

       }

       ans.push_back(arr[dq.front()]);

       return ans;
    }
};

// { Driver Code Starts.

int main() {

    int t;
    cin >> t;

    while (t--) {

        int n, k;
        cin >> n >> k;

        vector<int> arr(n);
        for (int i = 0; i < n; i++) cin >> arr[i];
        Solution ob;
        vector<int> res = ob.max_of_subarrays(arr, n, k);
        for (int i = 0; i < res.size(); i++) cout << res[i] << " ";
        cout << endl;
    }

    return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/deee0e8cf9910e7219f663c18d6d640ea0b87f87/1/)
