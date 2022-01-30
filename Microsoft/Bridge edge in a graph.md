# Bridge edge in a graph

```cpp
#include<bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution
{
	public:
    //Function to find if the given edge is a bridge in graph.
   void bfs(vector<int> adj[],bool visited[],int V,int src){
       visited[src]=true;
       queue<int> q;
       q.push(src);

       while(!q.empty()){
           int node = q.front();
           q.pop();
           for(int i=0;i<adj[node].size();i++){
               if(visited[adj[node][i]]==false){
                   visited[adj[node][i]]=true;
                   q.push(adj[node][i]);
               }
           }
       }
   }


   int isBridge(int V, vector<int> adj[], int c, int d)
   {
       // Code here
       bool visited[V];
       memset(visited,false,sizeof(visited));

       int count1 = 0;
       int count2 = 0;

       for(int i=0;i<V;i++){
           if(visited[i]==false){
               count1++;
               bfs(adj,visited,V,i);
           }
       }

       vector<int>::iterator it = find(adj[c].begin(),adj[c].end(),d);
       adj[c].erase(it);
       it = find(adj[d].begin(),adj[d].end(),c);
       adj[d].erase(it);

       memset(visited,false,sizeof(visited));
       for(int i=0;i<V;i++){
           if(visited[i]==false){
               count2++;
               bfs(adj,visited,V,i);
           }
       }
       if(count1==count2)return 0;
       return 1;


   }
};

// { Driver Code Starts.


int main()
{
    int t;
    cin >> t;
    while (t--) {
        int V, E;
        cin >> V >> E;
        vector<int> adj[V];
        int i=0;
        while (i++<E) {
            int u, v;
            cin >> u >> v;
            adj[u].push_back (v);
            adj[v].push_back (u);
        }

        int c,d;
        cin>>c>>d;

        Solution obj;
    	cout << obj.isBridge(V, adj, c, d) << "\n";
    }

    return 0;
}

  // } Driver Code Ends

```

## [Question Link](https://practice.geeksforgeeks.org/problems/bridge-edge-in-graph/1)
