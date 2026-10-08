```c++
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
typedef long double ld;
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
   
    ll xo, yo, r, n; cin >> xo >> yo >> r >> n;
    int cont=0; 
    //set<ld>ang[5]; 
    set<ii> ang;
    for(int i=0; i<n; i++){
        ll x1=0, y1=0, distx=0, disty=0; 
        ld dist = 0;
        cin >> x1 >>y1; 
        distx=x1-xo;
        disty=y1-yo; 
        
        int mmc = __gcd(distx, disty);
        ii par = make_pair(disty/abs(mmc), distx/abs(mmc));
  
        dist = sqrt((pow(distx,2))+(pow(disty, 2)));     
        if(dist<=r){
          if(ang.count(par)==0){
            ang.insert(par);  
            cont++;
          }
        }
    }
 
    cout << cont << endl; 
    return 0;
}
```