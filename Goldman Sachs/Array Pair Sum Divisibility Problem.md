# Array Pair Sum Divisibility Problem

```cpp
#include <bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution {
  public:
    bool canPair(vector<int> nums, int k) {
        if(nums.size()%2!=0)
             return false;
        unordered_map<int, int> mp;

        for(int i=0;i<nums.size();i++){
            mp[nums[i]%k]++;
        }

        for(int val: nums){
            int rem=val%k;

            if(rem==0){
                if(mp[rem]%2!=0)
                    return false;
            }
            else if(2*rem == k)
                {
                    if(mp[rem]%2!=0)
                    return false;
                }
            else
                {
                    int index=mp[rem];
                    int mIndex=mp[k-rem];
                    if(index!=mIndex)
                        return false;
                }
        }
        return true;
    }
};

// { Driver Code Starts.
int main() {
    int tc;
    cin >> tc;
    while (tc--) {
        int n, k;
        cin >> n >> k;
        vector<int> nums(n);
        for (int i = 0; i < nums.size(); i++) cin >> nums[i];
        Solution ob;
        bool ans = ob.canPair(nums, k);
        if (ans)
            cout << "True\n";
        else
            cout << "False\n";
    }
    return 0;
}  // } Driver Code Ends

```

## [Question Link](https://practice.geeksforgeeks.org/problems/array-pair-sum-divisibility-problem3257/1#)

## Time : O(n) Space : O(n)

## Explanation

- In this solution we would take a hashmap to store the remainders of the nos i.e., num[i]%k
- And then we would deal with the three cases

1. If the remainder is 0 then we would check if the count of the zero remainder is even or odd. If odd then we would return false.
2. if the remainder is k/2 then we would check if the count of the k/2 remainder is even or odd. If odd then we would return false.
3. the last case would be to find the count of the remainder and the count of the k-remainder. If the counts are not equal then we would return false.
