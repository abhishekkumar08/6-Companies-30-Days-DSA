# Subarray with given sum

```cpp


 // } Driver Code Ends
class Solution
{
    public:
    //Function to find a continuous sub-array which adds up to a given number.
    vector<int> subarraySum(int arr[], int n, long long s)
    {
        long long sum=0;
        int left=0,i=0;
        for(i=0;i<n;i++){
             if(sum==s)
                return {left+1, i};

            sum+=arr[i];

            while(sum>s){
                sum-=arr[left++];
            }

        }
        // cout << sum <<  " " << s << " " << i << endl;
        if(sum==s)
            return {left+1, i};
        return {-1};
    }
};

// { Driver Code Starts.

int main()
 {
    int t;
    cin>>t;
    while(t--)
    {
        int n;
        long long s;
        cin>>n>>s;
        int arr[n];
        const int mx = 1e9;
        for(int i=0;i<n;i++)
        {
            cin>>arr[i];
        }
        Solution ob;
        vector<int>res;
        res = ob.subarraySum(arr, n, s);

        for(int i = 0;i<res.size();i++)
            cout<<res[i]<<" ";
        cout<<endl;

    }
	return 0;
}  // } Driver Code Ends
```

## [Question Link](https://practice.geeksforgeeks.org/problems/subarray-with-given-sum-1587115621/1)
