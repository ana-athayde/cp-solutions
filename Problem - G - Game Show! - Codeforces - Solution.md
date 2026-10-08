```c++
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
typedef pair <int,int> ii;
int c, v[110], prefix[110];
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
    cin>>c;
    cin>>v[0];
    prefix[0]=v[0];
    int maior=0;
 
    for(int i=1;i<c;i++){
      cin>>v[i];
      prefix[i]=prefix[i-1]+v[i];
    }
    
    for(int i=0;i<c;i++) maior=max(maior, prefix[i]);
 
 
    cout<<maior+100<<endl;
  
    return 0; 
}
```