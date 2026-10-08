```c++
#include <iostream>
using namespace std;
 
int main() {
  int t;
  cin >> t;
  
  for (int i=0; i<t; i++) {
    int n, m, k;
    cin >> n >> m >> k;
    
    if (((m-1)*1 + (n-1)*m) == k) {
      cout << "Yes" << endl;
    } else {
      cout << "No" << endl;
    }
  }
	return 0;
}

```