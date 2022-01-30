# Generate Binary Numbers

```cpp



 // } Driver Code Ends

//Function to generate binary numbers from 1 to N using a queue.
vector<string> generate(int N)
{
	// Your code here
	vector<string>v;
	queue<string>q;
	q.push("1");
	for(int i=0;i<N;i++)
	{
	    string curr = q.front();
	    q.pop();
	    v.push_back(curr);
	    q.push(curr+"0");
	    q.push(curr+"1");
	}
	return v;
}


// { Driver Code Starts.

int main()
{
	int t;
	cin>>t;
	while(t--)
	{
		int n;
		cin>>n;
		vector<string> ans = generate(n);
		for(auto it:ans) cout<<it<<" ";
		cout<<endl;
	}
	return 0;
}  // } Driver Code Ends

```

## [Question Link](https://practice.geeksforgeeks.org/problems/generate-binary-numbers-1587115620/1/)
