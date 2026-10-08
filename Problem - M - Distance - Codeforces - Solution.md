```c++
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
 
// int dist(int x1, int y1, int x2, int y2){
//   return abs(x1-x2)+abs(y1-y2);
// }
 
int dist(int x1, int y1, int x2, int y2){
  return abs(x1-x2)+abs(y1-y2);
}
 
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
    
    int t; cin >> t;
    while(t--){
      int x, y; cin >> x >> y;
      double d = abs((x+y)/2);
      //  5 + 4 / 2 = 4.5
      //  d=4;
      // cout << d << endl;
      int flag = 0;
      for(int x3=0; x3<=50; x3++){
        for(int y3=0; y3<=50; y3++){
          if(x3+y3==d){
            // a d(A,C) == d(B,C)
            if(x3+y3 == dist(x, y, x3, y3)){
              cout << x3 << ' ' << y3 << endl;
              flag = 1;
              break;
            }
            
          }
        }
        if(flag) break;
      }
      if(!flag) cout << -1 << ' ' << -1 << endl;
    }
    
         
    return 0; 
 
}
```