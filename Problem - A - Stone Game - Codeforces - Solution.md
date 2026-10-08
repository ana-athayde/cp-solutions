```c++
#include <bits/stdc++.h>
 
using namespace std;
 
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
 
vector<int> vec;
vector<int> r;
int maxPos, minPos, n;
 
int solve(){
    maxPos = max_element(vec.begin(),vec.end()) - vec.begin();
    minPos = min_element(vec.begin(), vec.end()) - vec.begin();
 
    int op1, op2, op3, op4;
    op1 = max(maxPos, minPos) + 1;
    op2 = (n-1) - min(maxPos, minPos) + 1;
    op3 = (n-1) - maxPos + minPos + 2;
    op4 = (n-1) - minPos + maxPos + 2;
 
    return min({op1, op2, op3, op4});
}
 
int main() {
    int t; cin >> t;
    while(t--){
        cin >> n;
        for(int i=0; i<n; i++){
            int input; cin >> input;
            vec.push_back(input);
        }
        r.push_back(solve());
        vec.clear();
    }
    for(int i=0; i<r.size(); i++){
        cout << r[i] << endl;
    }
 
    return 0;
}
```