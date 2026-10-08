```c++
#include <iostream>
#include <bits/stdc++.h>
using namespace std;
 
int main() {
	int n;
  cin >> n;
  int ar [n];
  
  set<int> conjunto;
  
  for(int i=0; i<n; i++){
    cin >> ar[i];
    conjunto.insert(ar[i]);
  } 
  
  if(conjunto.size() <= 2)
      cout << "YES" << endl;
  else if(conjunto.size() == 3){ 
      vector<int> vec(conjunto.begin(), conjunto.end());
      if(2*vec[1] == vec[0] + vec[2]) cout << "YES" << endl;
      else cout << "NO" << endl;  
  }else 
      cout << "NO" << endl;
  
	return 0;
}
```