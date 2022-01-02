# Ugly Numbers

```cpp
#include <bits/stdc++.h>
using namespace std;
#define ull unsigned long long

class Solution{
public:
	ull getNthUglyNo(int n) {
	   set<ull> st;
	   st.insert(1);
	   n--;
	   while(n--){
	       auto it=st.begin();
	       ull ele=*it;
	       st.erase(it);

	       st.insert(ele*2);
	       st.insert(ele*3);
	       st.insert(ele*5);
	   }
	   return *st.begin();
	}
};

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        Solution ob;
        auto ans = ob.getNthUglyNo(n);
        cout << ans << "\n";
    }
    return 0;
}

```

## [Question Link](https://practice.geeksforgeeks.org/problems/ugly-numbers2254/1/#)

## Time : O(nlogn) Space : O(n)

## Explanation

- In this solution, we would generate the ugly numbers and stote it in an ordered set and then we would find the nth ugly number.
- the nth ugly no would be at the top of the set.
- A more optimal solution would be to use binary search.
