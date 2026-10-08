```c++
#include <bits/stdc++.h>
using namespace std;
#define MAXN 1000010
#define inf 1e9+5
typedef long long ll; 
typedef long double ld; 
typedef pair<int, int> ii;
typedef vector<int> vi;
typedef vector<ii> vii;
 
 
int main(){
    
    cout.sync_with_stdio(0);
    cin.tie(0);
    
    int t; cin >> t;
    while(t--){
        int arr[3];
        for(int i=0; i<3; i++){
            cin >> arr[i];
        }
        int b = 2*arr[1];
        if(b == (arr[0]+arr[2])) cout << "YES" << endl; 
        else if((arr[0]+arr[2]) % b == 0) cout << "YES" << endl;
        else{
            if((arr[0]+arr[2]) > b) cout << "NO" << endl;
            else if((b-arr[2]) % arr[0] == 0) cout << "YES" << endl;
            else if((b-arr[0]) % arr[2] == 0) cout << "YES" << endl;
            else cout << "NO" << endl;
        }
    }
    return 0; 
}
```