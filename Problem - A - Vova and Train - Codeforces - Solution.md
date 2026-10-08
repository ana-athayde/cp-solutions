```c++
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long long ll;
 
int main() {
    int ct; cin>>ct;
    
        while(ct--){
            int final,v,l,r;
            cin>>final>>v>>l>>r;
 
            int cont=0; 
            int totallanternas=final/v;
            int naovejo=(r/v)-((l-1)/v);
            cout<<totallanternas-naovejo<<endl; 
        }
        
  
	return 0;
}
```