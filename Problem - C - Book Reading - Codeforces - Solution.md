```c++
#include <bits/stdc++.h>
using namespace std;
 
int main() {
  int q;
  cin >> q;
  
  while(q--){
    long long n, m, aux = 0;
    cin >> n >> m;
    n = n/m;
    vector<int> numeros(10);
    
    for (int i = 0; i < 10; i++) {
      numeros[i] = ((i+1)*m) %10;
    }
    for (int i = 0; i < n%10; i++) {
      aux += numeros[i];
    }
    cout << aux + n / 10 * accumulate(numeros.begin(), numeros.end(), 0LL) << endl;
  }
	return 0;
}
```