```c++
#include <bits/stdc++.h>
using namespace std;
 
int n;
vector<int> a;
 
    
// 1 3 4 10 10 10 10 10 10
// 1 10
// 2 9
// pega o maior do maior
// pega o menor do menor
// nao estou contando um numero que não conheço
// ta retornando o menor do menor???
int achaMenor(int menor){
  int l, r;
  l = -1;
  r = n;
  
  while(r > l + 1){
    int m = (l + r) / 2;
    if(a[m] >= menor){
      r = m;
    }else{
      l = m;
    }
  }
  
  // preciso retornar meu menorm maior ou igual ao meu menor
  return l + 1;
}
 
 
//ta retornando o maior do maior???
int achaMaior(int maior){
  int l = -1, r = n;
    
  while(r > l + 1){
    int m = (l+r)/2;
    if(a[m] > maior){
      r = m;
    }else{
      l = m;
    }  
  }
  
  //preciso retornar meu maior menor ou igual a meior 
  return r + 1;
}
 
 
int main() {
  // D - Fast search
  cin >> n;
  a.resize(n);
  
  for(int i=0; i<n; i++) cin >> a[i];
  
  sort(a.begin(), a.end());
  
  int k; cin >> k;
  
  for(int i=0; i<k; i++){
    int menor, maior;
    cin >> menor >> maior;
    
    // cout << "_______" << endl;
    // cout << achaMaior(maior) << endl;
    // cout << achaMenor(menor) << endl;
    
    cout << achaMaior(maior) - achaMenor(menor) -1 << endl;
        
  }
  
	return 0;
}

```