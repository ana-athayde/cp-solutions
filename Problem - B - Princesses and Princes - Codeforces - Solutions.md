```c++
#include <iostream>
using namespace std;
 
int main() {
  int n, t;     
  cin >> t;
  
  while(t--){
    cin >> n;
 
    int cont = 0;
    int listaPrincesas[n] = {0};
    int listaPrincesos[n] = {0}; 
 
    for (int i = 0; i < n; i++) { //princesa
      // descrição da lista de cada princesa
        int k;
        cin >> k;
        int listaPricPrincesa [k];
        
        for (int m = 0; m < k; m ++) { // a lista dos principes dela
          int principeQuer;
          cin >> principeQuer; 
          if (listaPrincesos[principeQuer-1] == 0 && listaPrincesas[i]==0){
            listaPrincesos[principeQuer-1] = 1;
            listaPrincesas[i] = 1;
            cont++;
 
          }    
        }
        
    }
    // boa, achei engraçadinho
    if (cont == n) {
      cout << "OPTIMAL" << endl;
      
    } else {
      
      int princesaSolteira=-1;
      int princesoSolteiro=-1;
      
      for (int i = 0; i < n; i++) {
        if (listaPrincesas[i] == 0 && princesaSolteira == -1) {
          princesaSolteira = i+1;
        }
        if (listaPrincesos[i] == 0 && princesoSolteiro == -1) {
          princesoSolteiro = i+1;
        }
      }  
      
      cout << "IMPROVE" << endl;
      cout << princesaSolteira << " " << princesoSolteiro << endl; 
    }
  }
	return 0;
}
```