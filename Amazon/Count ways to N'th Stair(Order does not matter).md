# Count ways to N'th Stair(Order does not matter)

```cpp

 // } Driver Code Ends


class Solution
{
    public:
    //Function to count number of ways to reach the nth stair
    //when order does not matter.
    long long countWays(int m)
    {
        return m/2+1;
    }
};

// { Driver Code Starts.
int main()
{
    //taking count of testcases
    int t;
    cin >> t;

    while(t--)
    {
        //taking stair count
        int m;
        cin>>m;
        Solution ob;
        cout<<ob.countWays(m)<<endl; // Print the output from our pre computed array
    }
    return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/count-ways-to-nth-stairorder-does-not-matter1322/1/)

## Explanation

```
Consider that you have N stairs. First of all you have to understand if N is odd or even.

If is even than it will be a multiple of 2: N = 2*S, where S is the number of pair of stairs.

Suppose N = 6 and S = 3. Your first solution is {2,2,2}. than you can change the first 2 stairs with 1 + 1 stairs and you have your second solution {1, 1, 2 ,2}. Since order doesn't matter let's proceed with the next pair and we have our third solution {1, 1, 1, 1, 2} and then the fourth {1, 1, 1, 1, 1, 1}

Given N = 2*S the number of possible solutions are S + 1.

Now suppose N is odd and N = 2S + 1. Let N = 7 and S = 3. Our solutions are {2,2,2,1}, {1,1,2,2,1}, {1,1,1,1,2,1} and {1,1,1,1,1,1,1}. Again, the number of solutions is given by S+1

Now your algorithm is pretty simple:

return N/2 + 1
```
