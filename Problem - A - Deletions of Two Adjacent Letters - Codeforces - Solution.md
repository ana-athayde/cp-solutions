```c++
#include <bits/stdc++.h>
using namespace std;
#define MAXN 1000010
typedef long long ll; 
typedef long double ld; 
typedef pair<int, int> ii;
typedef vector<int> vi;
typedef vector<ii> vii;
 
 
int main(){
    int t; cin >> t;
    while(t--){
        string a; char b;
        cin >> a >> b;
        int len = a.length();
 
        vector<int> pos;
        for(int i=0; i<len; i++)
            if(a[i] == b)
                pos.push_back(i);
            
        
        int aux = 0;
        for(auto i: pos){
            if(i==0){
                if(((len-i-1) % 2) == 0) aux = 1;
            }else if(i>1){
                if((i % 2 == 0) && ((len-i-1) % 2 == 0)) aux = 1;
            } 
        }
        if(aux) cout << "YES" << endl;
        else cout << "NO" << endl;
    }
    return 0; 
}
```