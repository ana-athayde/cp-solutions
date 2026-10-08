```c++
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
typedef pair<int, int> ii;
typedef vector<int> vi;
typedef vector<ii> vii;
#define MAXN 10010
 
 
int main() {
  
  cout.sync_with_stdio(0);
  cin.tie(0);
  int cont=0, cont2=0, ant=0;
 
    int n; cin >> n; 
    
    for(int i=0;i<n+1;i++){
      string s; cin >> s;
      int m = s.size(); 
      string t; 
      int mid = m/2; 
      t= s.substr(mid+1, 2);
      int total=(t[0]-'0')*10+(t[1]-'0');
      
      int conta=(ant+total)%100;
      if(conta!=0 && i!=0) cont++;
      ant=conta;
    }
    cout << cont << endl; 
  
  return 0;
}
```