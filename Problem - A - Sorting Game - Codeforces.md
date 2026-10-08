```c++
#include <iostream>
using namespace std;
 
#include <iostream>
#include <string>
#include <vector>
#include <algorithm>
 
using namespace std;
 
void solve() {
    int n;
    cin >> n;
    string s;
    cin >> s;
 
    // 1. Verificar se a string já está ordenada
    bool sorted = true;
    for (int i = 0; i < n - 1; i++) {
        if (s[i] > s[i + 1]) {
            sorted = false;
            break;
        }
    }
 
    if (sorted) {
        cout << "Bob" << endl;
        return;
    }
 
    // 2. Contar total de zeros (Z)
    int total_zeros = 0;
    for (char c : s) {
        if (c == '0') total_zeros++;
    }
 
    // 3. Identificar intrusos
    // '1's nas primeiras Z posições e '0's após a posição Z
    vector<int> indices;
    for (int i = 0; i < n; i++) {
        if (i < total_zeros) {
            if (s[i] == '1') indices.push_back(i + 1);
        } else {
            if (s[i] == '0') indices.push_back(i + 1);
        }
    }
 
    // 4. Saída formatada
    cout << "Alice" << endl;
    cout << indices.size() << endl;
    for (int i = 0; i < indices.size(); i++) {
        cout << indices[i] << (i == indices.size() - 1 ? "" : " ");
    }
    cout << endl;
}
 
int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    
    int t;
    cin >> t;
    while (t--) {
        solve();
    }
    return 0;
}
```