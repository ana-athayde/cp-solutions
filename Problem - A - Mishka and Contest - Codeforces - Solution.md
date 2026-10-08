```c++
#include <bits/stdc++.h>
typedef long long ll;
using namespace std;
 
int main() {
  int n,k;cin>>n>>k;
  int v[n];
  int cont=0,maior=-1;
  
  for(int i=0;i<n;i++){
    cin>>v[i];
    if(maior==-1 && v[i]<=k) cont++;
    else if(maior==-1) maior=i;
  }
//   8 4
// 4 2 3 1 5 1 6 4
  if(maior!=-1){
    for(int i=n-1;i>maior;i--){
      if(v[i]<=k) cont++;
      else break;
    }
  }
  cout<<cont<<endl;
 
// [4,2,3,1,5,1,6,4]
	return 0;
}

```