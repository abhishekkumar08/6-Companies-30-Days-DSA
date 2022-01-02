# Run Length Encoding

```cpp
#include <bits/stdc++.h>
using namespace std;

string encode(string src);

int main() {

	int T;
	cin>>T;
	while(T--)
	{
		string str;
		cin>>str;

		cout<<encode(str)<<endl;
	}
	return 0;

string encode(string src)
{
  string ans = "";
    int left = 0, curr = 0;
    int count = 0;

    for (int curr = 0; curr < src.length(); curr++)
    {

        if (src[left] == src[curr])
            count++;
        else
        {
            ans += src[left];
            ans += to_string(count);
            left += count;
            count = 0;
            curr--;
        }
    }
    ans += src[left];
    ans += to_string(count);

  return ans;
}
```

## [Question Link](https://practice.geeksforgeeks.org/problems/run-length-encoding/1/#)

## Explanation

- is question me humlog two pointers ka use karenge. Ek pointer for the starting of the value and the other pointer for the end of the value. And then isi tarah har baar ek ans variable me store karte jayenge starting value of the string and then uska count.
