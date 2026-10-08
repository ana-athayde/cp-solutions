```c++
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
 
int main(){
  int n;cin>>n;
  int ano, ano2;
  int flag=0;
  for(int i=0;i<n;i++){
    int a,b;cin>>a>>b;
    int ano = a-b;
    if(i>0){
      if(ano2!=ano)flag=1;
    }
    ano2=ano;
    // cout<<ano<<endl;
  }
  
  if(flag==0) cout<<"idades corretas"<<endl;
  else cout<<"mentiu a idade"<<endl;
  
	return 0;
  
}
 
```