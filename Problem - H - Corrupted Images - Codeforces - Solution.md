```c++
#include <bits/stdc++.h>
using namespace std;
 
int main(){
    
    cout.sync_with_stdio(0);
    cin.tie(0);
  
    int t; cin >> t;
    while(t--){
        int n, m; cin >> n >> m;
        string vs[n];
        for(int i = 0; i < n; i++)
            cin >> vs[i];
        int zerodentro = 0, umdentro = 0;
        int umtotal = 0, zerototal = 0;        
        
        for(int i = 1; i < n-1; i++)
            for(int j = 1; j < m-1; j++){
                if(vs[i][j] == '0') zerodentro++;
                else umdentro++;
            }
        
        for(int i = 0; i < n; i++)
            for(int j = 0; j < m; j++){
                if(vs[i][j] == '0') zerototal++;
                else umtotal++;
            }
        
        int zeroborda = zerototal - zerodentro;
        int umborda = umtotal - umdentro;
 
            
        if(zeroborda > umdentro){
            cout << "-1" << endl;
        }else{
            cout << zeroborda << endl;
        }    
        
    }
 
	return 0;
}
```