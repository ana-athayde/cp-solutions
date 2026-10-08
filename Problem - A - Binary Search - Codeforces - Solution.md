```c++
#include <bits/stdc++.h>
using namespace std;
 
int main() {
  // A - Binary Search
  int n, k;
  cin >> n >> k;
  vector<int> a(n);
  
  for(int i=0; i<n; i++) cin >> a[i];
  
  for(int i=0; i<k; i++){
    int x; cin >> x;
    int l = 0, r = n - 1;
    bool teste = false;
    while (r >= l){
      int m = (l + r)/2;
      if(a[m] == x){
        teste = true;
        break;
      }else if(a[m] < x){
        l = m + 1;
      }else if(a[m] > x){
        r = m - 1;
      }
    }
    if (teste) cout << "YES" << endl;
    else cout << "NO" << endl;
  }
  
	return 0;
}

```