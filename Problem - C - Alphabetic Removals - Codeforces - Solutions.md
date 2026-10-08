```c++
#include <bits/stdc++.h>
typedef long long ll;
using namespace std;
 
int main() {
  int n,k;cin>>n>>k;
  map <char,int> mapa;
  char c[n];
  
  for(int i=0;i<n;i++){
    cin>>c[i];
    mapa[c[i]]++;
  }
  
  for(char i='a';i<='z';i++){
    if(k>0){
      int aux=mapa[i];
      mapa[i]-=k;
      k-=aux;
    }
  }
 
  reverse(c,c+n);
  string final;
  for(int i=0;i<n;i++){
    if(mapa[c[i]]>0){
      final+=c[i];
      mapa[c[i]]--;
    } 
  }
  reverse(final.begin(), final.end());
  cout << final << endl;
     
	return 0;
}
```