# Print Anagrams Together

```cpp
class Solution{
  public:
    vector<vector<string> > Anagrams(vector<string>& string_list) {
        //code here
        map<string, vector<string>> ars;
        for(int i=0;i<string_list.size();i++){
            string s= string_list[i];
            sort(s.begin(), s.end());
            ars[s].push_back(string_list[i]);
        }
        vector<vector<string>> ans;
        for(auto it:ars){
            ans.push_back(it.second);
        }
        return ans;
    }
};
```

## [Question Link](https://practice.geeksforgeeks.org/problems/print-anagrams-together/1/)

## Explanation

- In this solution, humlog map ka use kar rahe hai. Humlog array ka har ek string ko lete jayenge aur usko sort kar denge.
- And then humlog usko map me store karenge, sorted value as a key and array ka value as a value.
- And then last me usko vector of vector me push kar denge
