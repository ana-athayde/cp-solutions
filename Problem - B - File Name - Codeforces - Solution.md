```c++
#include <bits/stdc++.h>
using namespace std;
 
int main() {
	
  int n, conteliminados=0, aux=0, cont=0;
  cin>>n;
  char s[n];
 
  for(int i=0; i<n; i++){
    cin>>s[i];
    if(s[i] != 'x'){
      aux = 0;
    }else{
      aux++;
    }
    if (aux >= 3){
      conteliminados++;
    }
  }
    // != x, aux = 0; 
    // 
      // for(int i=0; i<s.size(); i++){
 
      // }
      // xxx xxx xe xxx x
 
    cout<<conteliminados<<endl; 
  
  
  
	return 0;
}

```