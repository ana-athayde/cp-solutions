```c++
#include <bits/stdc++.h>
 
using namespace std;
 
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
 
int l, c, n, cont, visitado[45][45], tamPalavras[21], m[45][45];
string a;
vector<string> vec;
vector<string> palavras;
map<char, int> mapa;
// vector<vector<set<int>>> especial(45);
set<int> especial[45][45];
 
 
int isValid(int x, int y){
  return x>=0 && y>=0 && x<l && y<c;
}
 
void solve(int linha, int coluna){
    //testar para todas as palavras
    for(int i=0; i<n; i++){
        //a partir da posição dele até o tam de cada palavra, cria uma string, da um sort nela e compara se são iguais
        // se forem iguais cont ++;
                
        //horizontal
        string b = "";
        for(int j = coluna; j <= coluna + tamPalavras[i] - 1; j++){
            if(isValid(linha, j))b += vec[linha][j]; 
            else break;
        } 
        sort(b.begin(), b.end());
        if(b == palavras[i])
          for(int j=coluna; j<= coluna + tamPalavras[i] - 1; j++)
            especial[linha][j].insert(i);
          
        
        //vertical
        b = {};
        for(int j = linha; j <= linha + tamPalavras[i] - 1; j++){
            if(isValid(j, coluna)) b += vec[j][coluna];
            else break;
        }
        sort(b.begin(), b.end());
        
        if(b == palavras[i])
            for(int j = linha; j <= linha + tamPalavras[i] - 1; j++) especial[j][coluna].insert(i);
        
        
        //diagonal p direita
        b = {};
        int linhaAux=linha;
        for(int j = coluna; j <= coluna + tamPalavras[i] - 1; j++){
            if(isValid(linhaAux, j)){
              b += vec[linhaAux][j];
              linhaAux++;
            }else break;
        } 
        sort(b.begin(), b.end());
        if(b == palavras[i]){
          linhaAux=linha;
          for(int j = coluna; j <= coluna + tamPalavras[i] - 1; j++){
            especial[linhaAux][j].insert(i);
            linhaAux++;
          } 
        }  
 
        //diagonal p esquerda
        b = {};
        linhaAux=linha;
        for(int j = coluna + tamPalavras[i] - 1; j >= coluna ; j--){
           if(isValid(linhaAux, j)){
              b += vec[linhaAux][j];
              linhaAux++;
            }else break;
        } 
        sort(b.begin(), b.end());
        if(b == palavras[i]){
          linhaAux=linha;
          for(int j = coluna + tamPalavras[i] - 1; j >= coluna ; j--){
            especial[linhaAux][j].insert(i);
            linhaAux++;
          } 
        }            
 
    }
} 
 
int main() {
    cout.sync_with_stdio(0);
    cin.tie(0);
    cin >> l >> c;
 
    for(int i=0; i<l; i++){ cin >> a; vec.push_back(a); }
    cin >> n;
 
    for(int i=0; i<n; i++){ 
        cin >> a; 
        sort(a.begin(), a.end());
        tamPalavras[i] = a.size();
        palavras.push_back(a); 
    }
 
    for(int i=0; i<n; i++)
        for(int j=0; j<palavras[i].size(); j++)
            mapa[palavras[i][j]]++;
        
    for(int i=0; i<l; i++)
        for(int j=0; j<c; j++)
            if(mapa.count(vec[i][j])>0)
                solve(i, j);
            
    for(int i=0;i<l;i++)
        for(int j=0;j<c;j++)
            if(especial[i][j].size()>1) cont++;
        
   
    cout<<cont<<endl;
    
    return 0;
}
```