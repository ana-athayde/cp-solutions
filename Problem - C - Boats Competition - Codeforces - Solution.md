```c++
#include <bits/stdc++.h>
using namespace std;
 
int solve(int s, vector<int> ar){
    int n = ar.size();
    int times = 0;
    set<int> usados;
    for(int i = 0; i < n; i++)
        for(int j = 0; j < n; j++)
            if(ar[i] + ar[j] == s && i != j && (usados.find(i) == usados.end()) && (usados.find(j) == usados.end())){
                times++;
                usados.insert(i);
                usados.insert(j);
            }
    return times;
}
 
int main() {
	int t;
  cin >> t;
  
  while(t--){
    int n;
    cin >> n;
    vector<int> pesoParticipante;
    
    for(int m = 0; m < n; m++){
      int input;
      cin >> input;
      pesoParticipante.push_back(input);
    }
    
    int times = 0;
    for(int s = 0; s <= 100; s++)
        times = max(times, solve(s, pesoParticipante));
    cout << times << endl;
    
  }
	return 0;
}
```