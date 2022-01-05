# Find Missing And Repeating

```cpp
#include <bits/stdc++.h>

using namespace std;

 // } Driver Code Ends
class Solution{
public:
    vector<int> findTwoElement(int *arr, int n) {
    int xor1;

    int set_bit_no;

    int i;
    int x = 0;
    int y = 0;

    xor1 = arr[0];

    for (i = 1; i < n; i++)
        xor1 = xor1 ^ arr[i];

    for (i = 1; i <= n; i++)
        xor1 = xor1 ^ i;

    set_bit_no = xor1 & ~(xor1 - 1);

    for (i = 0; i < n; i++) {
        if (arr[i] & set_bit_no)
            x = x ^ arr[i];

        else
            y = y ^ arr[i];
    }

    for (i = 1; i <= n; i++) {
        if (i & set_bit_no)
            x = x ^ i;

        else
            y = y ^ i;
    }

    // if the values are reversed i.e x is not the missing element then swap them
    int x_count = 0;
    for (int i=0; i<n; i++) {
        if (arr[i]==x)
            x_count++;
    }

    if (x_count==0)
        return {y, x};

    return {x, y};
    }
};

// { Driver Code Starts.

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        int a[n];
        for (int i = 0; i < n; i++) {
            cin >> a[i];
        }
        Solution ob;
        auto ans = ob.findTwoElement(a, n);
        cout << ans[0] << " " << ans[1] << "\n";
    }
    return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/find-missing-and-repeating2512/1)

## Time Complexity: O(n) Space Complexity: O(1)

## Explanation:

- We can use XOR to find the missing and repeating element.
- XOR all the values a[i] and put it in a variable named X
- After that xor X with all the numbers from 1 to n.
- And then we would get the xor of missing and repeating element. X^Y
- And then we would make two baskets and then we would seperate the elements according to the rightmost set bit by looping through the array.
- And then we would do the same thing for values of 1 to n.
- And at last we would find the missing and repeating element.
