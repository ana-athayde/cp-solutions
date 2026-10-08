```c++
#include <bits/stdc++.h>
using namespace std;
 
 
int main() {
    string userName; cin >> userName;
    set<char> conjunto;
    int diferentes = 0;
    
    for(int i=0; i<userName.length(); i++){
        if(conjunto.count(userName[i]) == 0){
            conjunto.insert(userName[i]);
            diferentes++;
        }
    }
    
    if(diferentes % 2 == 0) cout << "CHAT WITH HER!" << endl;
    else cout << "IGNORE HIM!" << endl;
    // cout << diferentes << endl;
    return 0;
}
```