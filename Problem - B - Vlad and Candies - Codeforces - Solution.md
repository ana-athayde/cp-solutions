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
        ll n; cin >> n;
        map<ll, ll> candies;
        // vector<int> candies;
        ll maior = -1;
        for(ll i=0;i<n;i++){
            ll inp; cin >> inp;
            candies[inp]++;
            // candies.push_back(inp);
            maior = max(maior, inp);
        }
        if(n == 1 && maior > 1) cout << "NO" << endl;
        else if(n == 1 && maior == 1) cout << "YES" << endl;
        else if (candies[maior] > 1) cout << "YES" << endl;
        else{
            ll segMaior = -1;
            map<ll, ll>::iterator it;
            for(it=candies.begin(); it!=candies.end(); ++it){
                if(it->first != maior){
                    segMaior = max(segMaior, it->first);
                }
            }
            if(abs(maior-segMaior)>1){
                cout << "NO" << endl;
            }else{
                cout << "YES" << endl;
            }
        }
    }
    return 0; 
}
```