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
 
 
ii st[25][10005];
int logzera[10005];
 
bool ispalindrome(string s){    
    int n = s.size();
    for(int i = 0; i < n/2; i++){
        if(s[i] != s[n-i-1])
            return false;
    }
    return true;
}
 
char s[30];
ll mod = 1e9 + 7;
 
int readInt () {
	bool minus = false;
	int result = 0;
	char ch;
	ch = getchar();
	while (true) {
		if (ch == '-') break;
		if (ch >= '0' && ch <= '9') break;
		ch = getchar();
	}
	if (ch == '-') minus = true; else result = ch-'0';
	while (true) {
		ch = getchar();
		if (ch < '0' || ch > '9') break;
		result = result*10 + (ch - '0');
	}
	if (minus)
		return -result;
	else
		return result;
}
 
int gethash(int len){
    int hash = 0;
    int pot = 97;
    for(int i = 0; i < len; i++){
        hash = (hash * 1LL * pot + s[i]) % mod;
    }
    return hash;
}
 
int contapalindrome(int n){
    vector<int> d1 (n);
    int l=0, r=-1;
    for (int i=0; i<n; ++i) {
    int k = i>r ? 1 : min (d1[l+r-i], r-i+1);
    while (i+k < n && i-k >= 0 && s[i+k] == s[i-k])  ++k;
    d1[i] = k;
    if (i+k-1 > r)
        l = i-k+1,  r = i+k-1;
    }
    vector<int> d2 (n);
    l=0, r=-1;
    for (int i=0; i<n; ++i) {
    int k = i>r ? 0 : min (d2[l+r-i+1], r-i+1);
    while (i+k < n && i-k-1 >= 0 && s[i+k] == s[i-k-1])  ++k;
    d2[i] = k;
    if (i+k-1 > r)
        l = i-k,  r = i+k-1;
    }
    
    int res = 0;
    for(int i = 0; i < n; i++)
        res += d1[i] + d2[i];
 
    // for(int i = 0; i < n; i++)
    //     cout << "d1[" << i << "] = " << d1[i] << endl;
    
    
    // for(int i = 0; i < n; i++)
    //     cout << "d2[" << i << "] = " << d2[i] << endl;
    // return 0;
    
    return res;
    // int n = s.size();
    // int contador = 0;
    // for(int i = 0; i < n; i++)
    //     for(int j = i; j < n; j++){
    //         string sub = s.substr(i, j-i+1);
    //         if(ispalindrome(sub))
    //             contador++;
    //     }
    // return contador;
}
 
 
int main(){
 
    // cout.sync_with_stdio(0);
    // cin.tie(0);
 
    int t = readInt();
    while(t--){
        int n, q; // scanf("%d %d", &n, &q);
        n = readInt();
        q = readInt();
        vector<int> vec;
        map<int, int> mapa;
        for(int i = 0; i < n; i++){
            scanf("%s", s);
            int len = strlen(s);
            mapa[gethash(len)] = i;
            vec.push_back(contapalindrome(len));
        }
        
        logzera[1] = 0;
        for(int i = 2; i <= n; i++)
            logzera[i] = logzera[i/2] + 1;
        
        
        for(int i = 0; i < n; i++)
            st[0][i] = ii(vec[i], -i);
        for(int j = 1; j < 15; j++)
            for(int i = 0; i + (1 << j) <= n; i++)
                st[j][i] = max( st[j-1][i], st[j-1][i + (1 << (j-1))] );
        
        while(q--){
            
            scanf("%s", s);
            int esq = mapa[gethash(strlen(s))];
            scanf("%s", s);
            int dir = mapa[gethash(strlen(s))];
            
            if(esq > dir) swap(esq, dir);
            int j = logzera[dir - esq + 1];
            ii res = max(st[j][esq], st[j][dir - (1 << j) + 1]);
            int foi = -res.second;
            
            printf("%d\n", foi+1);
            // int idx = esq;
            
            // for(int i = esq; i <= dir; i++)            
            //     if(vec[i] > vec[idx])
            //         idx = i;
            // cout << idx+1 << endl;
            //
        }
    }
 
 
    return 0;
}
```