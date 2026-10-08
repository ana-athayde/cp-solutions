```c++
#include <bits/stdc++.h>
using namespace std;
#define MAXN 1000010
#define inf 1e9+5
typedef long long ll; 
typedef long double ld; 
typedef pair<int, int> ii;
typedef vector<int> vi;
typedef vector<ii> vii;
 
 
int main(){
    
    cout.sync_with_stdio(0);
    cin.tie(0);
    
    ll t; cin >> t;
    while(t--){
        ll n; cin >> n;
        ll maior = -1, menor = inf;
        for(int i=0; i<n; i++){
            ll a; cin >> a;
            maior = max(a, maior);
            menor = min(a, menor);
        }
        if(maior == menor) cout << 0 << endl;
        else cout << abs(maior-menor) << endl;
    }
    
    return 0; 
}
```