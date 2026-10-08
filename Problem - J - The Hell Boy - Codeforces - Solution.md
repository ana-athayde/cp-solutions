```c++
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
ll mod = 1e9 + 7;
ll a[100005], dp[100005];
 
int main(){
    
    cout.sync_with_stdio(0);
    cin.tie(0);
  
    int t; cin >> t;
    while(t--){
        int n; cin >> n;
        for(int i = 1; i <= n; i++)
            cin >> a[i];
        dp[0] = 0;
        for(int i = 1; i <= n; i++)
            dp[i] = (dp[i-1] + a[i] * dp[i-1] + a[i]) % mod;
        cout << dp[n] << endl;
    }
	return 0;
}
```