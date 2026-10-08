```c++
#include <bits/stdc++.h>
typedef long long ll;
using namespace std;
 
int main() {
  ll ct;
  cin>>ct;
  while(ct--){
    ll n, par=0, impar=0;
    cin>>n;
    ll num[n];
 
    for(int i=0;i<n;i++){
      cin>>num[i];
      if(num[i]%2==0) par++;
      else impar++;
    }
    
  // par+()
  if(par!=n){
    if(par>=impar) cout<<impar+(par-impar)<<endl;
    else cout<<par<<endl;
   } else cout<<-1<<endl;   
    
    
  }
  
  
	return 0;
}
```