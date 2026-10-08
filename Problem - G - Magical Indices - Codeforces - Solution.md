```c++
#include <bits/stdc++.h>
#include <bits/extc++.h>
#include <ext/pb_ds/detail/standard_policies.hpp>
using namespace std;
using namespace __gnu_pbds;
typedef long long ll;
typedef long double ld;
typedef pair<int,int> ii;
typedef tuple<int,int,int> i3;
typedef tuple<int,int,int,int> i4;
#define debug(x) cout << #x << ' ' << x << endl;
#define all(x) x.begin(), x.end()
#define sz(x) int(x.size())
#define rep(i, j, k) for(int i = j; i < k; i++)
typedef vector<ll> vi;
typedef vector<vi> vvi;
 
int a[1000005], esq[1000005], dir[1000005];
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
 
    int t; cin >> t;
    while(t--){
        
        
        int n; cin >> n;
        for(int i = 1; i <= n; i++)
            cin >> a[i]; 
        esq[1] = a[1];
        for(int i = 2; i <= n; i++)
            esq[i] = max(esq[i-1], a[i]);
        dir[n] = a[n];
        for(int i = n-1; i >= 1; i--)   
            dir[i] = min(dir[i+1], a[i]);
        
        int contador = 0;
        for(int i = 2; i < n; i++){
            if(esq[i] <= a[i] && a[i] <= dir[i])
                contador++;
        }
        cout << contador << endl;
    }
 
 
    return 0;
}
```