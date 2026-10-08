```c++
#include <bits/stdc++.h>
using namespace std;
 
vector<int> vec;
 
int main() {
	string s;
    cin >> s;
    
    for(int i=0; i<s.size(); i++){
        if(s[i] != '+'){
            int aux = s[i] - 48;
            vec.push_back(aux);
        }
    }
    
    sort(vec.begin(), vec.end());
 
    for(int i=0; i<vec.size(); i++){
        char aux = '0' + vec[i];
        if(i != vec.size()-1) cout << aux << '+';
        else cout << aux << endl;
    }
 
	return 0;
}
```