# Winner of an election

```cpp
#include <iostream>
#include <map>
#include <algorithm>
#include <cstdlib>
#include<bits/stdc++.h>

using namespace std;


 // } Driver Code Ends
class Solution{
  public:

    //Function to return the name of candidate that received maximum votes.
    vector<string> winner(string arr[],int n)
    {
        map<string,int> m;
       int c=0;
       for(int i=0; i<n; i++){
           m[arr[i]]++;
           c=max(c,m[arr[i]]);
       }
       vector<string> r;
       for(auto it:m){
           if(it.second==c){
           r.push_back(it.first);
           break;
         }
       }
       r.push_back(to_string(c));
       return r;

    }
};

// { Driver Code Starts.

int main()
{
    int t;
    cin>>t;

    for(int i=0;i<t;i++)
    {


        int n;
        cin>>n;

        string arr[n];

        for (int i=0;i<n;i++)
        cin>>arr[i];
        Solution obj;
        vector<string> result = obj.winner(arr,n);

        cout<<result[0] << " " << result[1] << endl;
    }
    return 0;
}
  // } Driver Code Ends

```

## [Question Link](https://practice.geeksforgeeks.org/problems/winner-of-an-election-where-votes-are-represented-as-candidate-names-1587115621/1/)
