# First non-repeating character in a stream

```cpp
#include<bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution {
	public:
		string FirstNonRepeating(string A){
	    string ans = "";
        deque<char> dq;
        int hash[26]={0};

        for(auto it:A){
            int pos = it - 'a';

            if(hash[pos] == 0){
                dq.push_back(it);
            }
            hash[pos]++;

            while(!dq.empty() and hash[dq.front() - 'a'] != 1) dq.pop_front();

            if(dq.empty()) ans += '#';
            else ans += dq.front();
        }
        return ans;
		}

};

// { Driver Code Starts.
int main(){
	int tc;
	cin >> tc;
	while(tc--){
		string A;
		cin >> A;
		Solution obj;
		string ans = obj.FirstNonRepeating(A);
		cout << ans << "\n";
	}
	return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/first-non-repeating-character-in-a-stream1216/1)
