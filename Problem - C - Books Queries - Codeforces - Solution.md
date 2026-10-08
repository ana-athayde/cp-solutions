```c++
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long long ll;
 
//C. Books Queries
 
int main() {
    int ct; cin>>ct;
    int pos[500010];  
    // r, l
    // R 4 - > pos[4]=r;
    // r++;   
    // l--;
    // [1][3][1]
    // -2 -1 0 1 
    // 1  2  3 
    
    // ? 3
        ct--;
        char a;int b;cin>>a>>b;
        pos[b]=1; 
        int l=0, r=2;
        int contleft=0;
        int qnt=1;
 
        while(ct--){
            cin>>a>>b;
            if(a=='R'){
                pos[b]=r;
                r++;
                qnt++;
            }else if(a=='L'){
                pos[b]=l;
                l--;
                contleft++;
                qnt++;
            }else{
                // cout<<"qnt "<<qnt<< " cont "<<contleft<<" pos "<<pos[b]+contleft<<endl;
                // cout<<"inicial "<< pos[b]+contleft-1<<endl;
                // cout<<"final "<< qnt-(pos[b]+contleft)<<endl;
                int dist=min(pos[b]+contleft-1,qnt-(pos[b]+contleft));
                cout<<dist<<endl;
            }
        }
        
  
	return 0;
}
```