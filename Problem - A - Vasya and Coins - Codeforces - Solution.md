```c++
#include <bits/stdc++.h>
using namespace std;
#define MAXN 1000010
#define inf 1e10+7
#define mod 1000000007
typedef long long ll; 
typedef long double ld; 
typedef pair<int, int> ii;
typedef vector<int> vi;
typedef vector<ii> vii;
 
 
int main(){   
    ll t; cin >> t;
    while(t--){
        ll a, b; cin >> a >> b;
        if(b == 0){
            cout << a+1 << endl;
        }else if(a == 0){
            cout << 1 << endl;
        }else{
            cout << 2*b+a+1 << endl;
        }
    }
    return 0; 
}
```