# Number following a pattern

```cpp
#include<bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution{
public:
    string printMinNumberForPattern(string S){
        stack<int> st;
        int count=1;
        string ans="";
        for(int i=0;i<S.length();i++){
            if(S[i]=='D')
                {
                    st.push(count++);
                }
            else
                {
                    st.push(count++);
                    while(!st.empty()){
                        ans+=to_string(st.top());
                        st.pop();
                    }
                }
        }
        st.push(count);
        while(!st.empty()){
            ans+=to_string(st.top());
            st.pop();
        }
        return ans;
    }
};


// { Driver Code Starts.
int main()
{
    int t;
    cin>>t;
    while(t--)
    {
        string S;
        cin >> S;
        Solution ob;
        cout << ob.printMinNumberForPattern(S) << endl;
    }
    return 0;
}
  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/number-following-a-pattern3126/1#)

## Time : O(n) Space : O(n) as push and pop in stack takes O(1)

## Explanation

- In this solution, we have to make a pattern where D means a decreasing one and I means an increasing one where we have to come up with a minm no which follows this pattern.
- We would use a stack to store the numbers. If we find a D we would push the number in the stack. and increase the count.
- And if we find an I we would push the number in the stack and then increase it and then we would empty the stack.
- And lastly we would have to repeat the same step to push the count and empty the stack outside the loop.
- for example input: D then the minm no which follows the pattern is 21. The no should be decreasing like 2 > 1
