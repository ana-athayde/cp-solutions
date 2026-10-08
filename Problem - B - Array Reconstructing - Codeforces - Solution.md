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
 
 
 
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
 
    int t; cin >> t;
    while(t--){
        int n, m; cin >> n >> m;
        vector<int> a(n);
        for(int i = 0; i < n; i++)
            cin >> a[i];
        int pos = 0;
        for(int i = 0; i < n; i++)
            if(a[i] != -1)
                pos = i;
        
        for(int i = pos-1; i >= 0; i--)
            a[i] = (a[i+1] - 1 + m) % m;
        for(int i = pos+1; i < n; i++)
            a[i] = (a[i-1] + 1) % m;
        
        for(int i = 0; i < n; i++)
            cout << a[i] << ' ';
        cout << endl;
    }
 
    return 0;
}
```