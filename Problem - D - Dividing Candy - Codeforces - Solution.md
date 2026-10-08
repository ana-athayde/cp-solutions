```c++
#include <bits/stdc++.h>
using namespace std;
#define MAXN 1000001
typedef long long ll; 
typedef pair<int, int> ii;
typedef vector<int> vi;
typedef vector<ii> vii;
set<int> caixas;
 
void inserir(int x){
  if(caixas.count(x)){
    caixas.erase(x);
    inserir(x+1);
  }else caixas.insert(x);
}
 
 
int main(){
    
    cout.sync_with_stdio(0);
    cin.tie(0);
 
    int n;cin>>n;
 
    for(int i=0;i<n;i++){
        int x;cin>>x;
        inserir(x);
    }
    
    if(caixas.size()>2 || n==1) cout<<"N"<<endl;
    else cout<<"Y"<<endl;    
 
    return 0; 
}
```