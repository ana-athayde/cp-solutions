```c++
#include <bits/stdc++.h>
using namespace std;
 
int a[200005], n;
int visitado[200005], valorcalculado[200005];
vector<int> mapa[200005];
 
// 1 2 3 4 5 6
// 1 2 3 1 3 2
 
// 1 : 1 4
// 2 : 2 6
// 3 : 3 5 7 10 15 16 18
 
int solve(int pos){
    if(pos == n) return 0;
    if(visitado[pos]) return valorcalculado[pos];
    visitado[pos] = 1;
    int r1 = solve(pos+1) + 1;
    int cor = a[pos];
    int found = lower_bound(mapa[cor].begin(), mapa[cor].end(), pos) - mapa[cor].begin();
    found = found + 1;
    // for(int i = pos+1; i <= n; i++)
    //     if(a[i] == a[pos]){
    //         found = i;
    //         break;
    //     }
    int r2;
    if(found >= mapa[cor].size()) r2 = 1e9;
    else r2 = solve(mapa[cor][found]) + 1;
    
    valorcalculado[pos] = min(r1,r2);
    return min(r1, r2);
}
 
int main(){
    
    cout.sync_with_stdio(0);
    cin.tie(0);
  
    int t; cin >> t;
    while(t--){
        cin >> n;
        for(int i = 1; i <= n; i++)
            cin >> a[i];
        for(int i = 1; i <= n; i++)
            mapa[a[i]].push_back(i);
        for(int i = 1; i <= n; i++)
            visitado[i] = 0;
        cout << solve(1) << endl;
        
        for(int i = 1; i <= n; i++)
            mapa[a[i]].pop_back();
        
    }
	return 0;
}
```