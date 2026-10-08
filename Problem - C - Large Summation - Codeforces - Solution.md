```c++
#include <bits/stdc++.h>
using namespace std;
 
int mod = 1e9 + 7;
 
int main(){
    
    cout.sync_with_stdio(0);
    cin.tie(0);
  
    int t; cin >> t;
    while(t--){
        int n; cin >> n;
        vector<int> a(n);
        for(int i = 0; i < n; i++)
            cin >> a[i];
        vector<int> b = a;
        sort(b.begin(), b.end());
        
        map<int,int> freq;
        for(int i = 0; i < n; i++)
            freq[b[i]]++;
        
        for(int i = 0; i < n; i++){
            int res = 0;
            int x = mod - a[i];
            
            int p1 = lower_bound(b.begin(), b.end(), x) - b.begin();
            p1--;
            
            if(p1 >= 0 && b[p1] == a[i] && freq[a[i]] == 1) p1--;
            
            int p2 = n-1;
            
            if(b[p2] == a[i] && freq[a[i]] == 1) p2--;
            
            if(0 <= p1 && p1 < n) res = max(res, (a[i] + b[p1]) % mod);
            if(0 <= p2 && p2 < n) res = max(res, (a[i] + b[p2]) % mod);
            
            cout << res << ' ';
        }
        cout << endl;
    }
	return 0;
}

```