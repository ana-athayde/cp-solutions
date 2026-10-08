```c++v
#include <bits/stdc++.h>
typedef long long ll;
using namespace std;
 
int main() {
  ll ct;
  cin>>ct;
  while(ct--){
    ll n,k, cont=0;
    cin>>n>>k;
    ll v[n];
    for(int i=0;i<n;i++){
      cin>>v[i];
    }
 
    sort(v, v+n);
    ll esq=0, dir=n-1;
    while(esq<=dir){   
      if(v[dir]>=k){
        cont++;
        dir--;
      }else if(v[dir]+v[esq]>=k){
        if(esq!=dir) cont++;      
        dir--;
        esq++;
      }else{
        esq++;
      }
    }
    cout<<cont<<endl;
    
  }
	return 0;
}
 
 
 
// 1 2 3 5 5 
```