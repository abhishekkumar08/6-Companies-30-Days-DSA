# Minimum Size Subarray Sum

```cpp
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int ans=INT_MAX;
        int left=0;
        int sum=0;
        for(int i=0;i<nums.size();i++){
            sum+=nums[i];

            while(sum>=target)
              {
                ans=min(ans, i+1-left);
                sum-=nums[left];
                left++;
              }
        }
        return ans != INT_MAX ? ans : 0;
    }
};
```

## [Question Link](https://leetcode.com/problems/minimum-size-subarray-sum/)

## Explanation

- In this solution, humlog two pointer ka use kar rahe hai, jisme ki humlog ek left pointer ko rakhenge jo 0 se start ho raha. And array ko loop through karenge taaki uska sum ko ek variable me store karte jaye.
- Jab wo value target se bada ya target ke equal ho jayega to humlog uss subarray ka length find karenge. Length find karne ke baad humlog left pointer ka value ko sum se minus kar denge aur tab tak minus karenge jab tak wo target se chhota na ho jaye.
- And then array ka agla value add karenge. Isi tarah se humlog sabse shortest subarray length find karenge.
