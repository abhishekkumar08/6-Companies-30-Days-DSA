# 713. Subarray Product Less Than K

```cpp
class Solution {
public:
    int numSubarrayProductLessThanK(vector<int>& nums, int k) {
        if(k<=1) return 0;
        int prod=1;
        int ans=0;

        int left=0, right=0;
        while(right<nums.size()){
            prod*=nums[right];

            while(prod>=k){
                prod/=nums[left];
                left++;
            }

            ans+=right-left+1;
            right++;
        }
        return ans;
    }
};
```

## [Question Link - Leetcode](https://leetcode.com/problems/subarray-product-less-than-k/)

## [Question Link - GFG](https://practice.geeksforgeeks.org/problems/count-the-subarrays-having-product-less-than-k1708/1/#)

## Explantion

- isme humlog sliding window approach ka use karenge. do pointer banayenge humlog left and right and jaise jaise array me aage badhenge uske subarray ke values ka product lete jayenge. Jab product target se equal ya usse bada ho jayega to humlog phir left pointer ko badhayenge and left pointer ke value ko product se hatate hue. this way humlog subarray ka window ko aage badhate jayenge. and then lastly right-left+1 karke subarrays ko count karte jayenge. **use an example to understand this**
