```c++
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
 
int main(){
  ll n; cin>>n;
  ll v[n];
  for (int i=0;i<n;i++){
    cin>>v[i];
  }
  
  sort(v, v+n);
  int flag=0;
  ll div=n-(n%3);
  for(ll i=div;i>0;i=i-3){
    if(i==n){
      cout<<v[i-1]<<endl;
      flag=1;
      break;
    }else if(v[i]!=v[i-1]){
      cout<<v[i-1]<<endl;
      flag=1;
      break;
    }
  
}
 
if(flag==0) cout<<-1<<endl;
return 0;
}
 
```