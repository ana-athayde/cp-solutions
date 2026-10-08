```c++
#include <bits/stdc++.h>
using namespace std;
 
typedef long long ll;
 
ll n, input, soma, sTotal;
vector<ll> vec;
 
int main() {
	cin >> n;
    
    for(int i=0; i<n; i++){
        cin >> input;
        sTotal += input;
        vec.push_back(input);
    }
    
    sort(vec.begin(), vec.end());
    
    soma = sTotal;
    
    for(int i=0; i<n-1; i++){
        sTotal += soma;
        soma -= vec[i];    
    }
    
    cout << sTotal << endl;
    
	return 0;
}
```