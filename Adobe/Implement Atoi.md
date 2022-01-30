# Implement Atoi

```cpp
//Initial template for C++

#include <bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
//User function template for C++

class Solution{
  public:
    /*You are required to complete this method */
    int atoi(string str) {
        //Your code here
        int n = str.size();
       int ans=0;
       if (str[0]=='-'){
           for (int i=1;i<n;i++){
           if (!(str[i]>='0' && str[i]<='9'))return -1;
            ans=ans*10+(str[i]-'0');
          }
          return ans*-1;
       }
       else{
         for (int i=0;i<n;i++){
           if (!(str[i]>='0' && str[i]<='9'))return -1;
           ans=ans*10+(str[i]-'0');
         }
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
		string s;
		cin>>s;
		Solution ob;
		cout<<ob.atoi(s)<<endl;
	}
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/implement-atoi/1/#)
