```c++
#include <iostream>
using namespace std;
 
#include <bits/stdc++.h>
#define MAXN 1000010
typedef long long ll; 
typedef long double ld; 
typedef pair<int, int> ii;
typedef vector<int> vi;
typedef vector<ii> vii;
 
int n;
vector<string> grid;
vector<vector<bool>> visited;
 
bool dfs(int i, int j){
    if(i < 0 || i >= 2 || j < 0 || j >= n) return false;
    if(grid[i][j] == '1') return false; // armadilha
    if(visited[i][j]) return false;
 
    if(i == 1 && j == n-1) return true; // chegou no fim
 
    visited[i][j] = true;
 
    // movimentos 
    return dfs(i, j+1) ||   // direita
           dfs(1-i, j+1) || // diagonal pra frente
           dfs(1-i, j) ||   // troca de linha
           dfs(i, j-1);
}
 
int main(){
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
 
    int t;
    cin >> t;
 
    while(t--){
        cin >> n;
        grid.resize(2);
        cin >> grid[0] >> grid[1];
 
        visited.assign(2, vector<bool>(n, false));
        
        if (dfs(0, 0)) { cout << "YES\n"; } 
        else { cout << "NO\n"; }
    }
}
```