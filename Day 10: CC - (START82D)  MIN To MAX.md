You have given an array of size N.
Let M be the minimum value pesent initially.
In one operation, you can choose element Ai (1<=i<=N) and an integer X (1<=X<=100) and set Ai = X.
Determine minimum number of operations required to make M the maximum value in the array.

```cpp
#include <bits/stdc++.h>
#include <vector>
using namespace std;

int main() {
	int t;
	cin>>t;
	while(t--){
	    int n,b, i, count=0;
	    cin>>n;
	    vector <int> ans;
	    for(i=0; i<n; i++){
	        cin>>b;
	        ans.push_back(b);
	    }
      // the simplest approach for this question was to make all numbers equal to the minimum element and count the number of operations to do so 
	    int c=*min_element(ans.begin(), ans.end());
	    for(i=0; i<n; i++){
	        if(ans[i]!=c){
	            ans[i]=c;
	            count++;
	        }
	    }
	    cout<<"\n"<<count;
	}
	return 0;
}
```
