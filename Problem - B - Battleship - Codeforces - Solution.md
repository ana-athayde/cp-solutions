```c++
#include <bits/stdc++.h>
using namespace std;
 
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
 
bool valid(int x, int y) {
        return x >= 1 && x < 11 && y >= 1 && y < 11;
}
 
int n;
int matriz[11][11];
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
    
    cin >> n;
    int valido = 1;
    
    while(n--){
        int d, l, r, c; cin >> d >> l >> r >> c;   
        if(d == 0){ // posicionado horizontalmente
            for(int y=c; y<=c+l-1; y++){
                if(!valid(r,y) || matriz[r][y] == 1){
                    valido = 0;
                    break;
                }
                matriz[r][y] = 1;
            }
        }else{ // posicionado verticalmente
            for(int x=r; x<=r+l-1; x++){
                if(!valid(x,c) || matriz[x][c] == 1){
                    valido = 0;
                    break;
                }
                matriz[x][c] = 1;
            }
        }
   
    }
 
    // for(int i=1; i<=10; i++){
    //     for(int j=1; j<=10; j++){
    //         cout << matriz[i][j] << ' ';
    //     }
    //     cout << endl;
    // }    
 
    if(valido == 1) cout << 'Y' << endl;
    else cout << 'N' << endl;
 
    return 0; 
}
```