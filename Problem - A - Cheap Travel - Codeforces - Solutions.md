```c++
#include <iostream>
#include <cmath>
using namespace std;
 
int main() {
	int n, m , a, b;
    cin >> n >> m >> a >> b;
    if (n == 1){
      if(a <= b){
        cout << a << endl;
      }else{
        cout << b << endl;
      }
    }else{
      if(a <= b/m){
        cout << n * a << endl;
      }else{
        if(n%m == 0){      
          cout << (n/m) * b << endl;
        }else{      
            double valoresCombo, restoCombo, valoresUnitarios,socombo, combocomsobra;
            restoCombo = n%m;// // b % m
            valoresCombo = b*((n-restoCombo)/m); //  b / m
            valoresUnitarios = restoCombo * a;
            combocomsobra = valoresCombo + valoresUnitarios;
            socombo = valoresCombo + b;
            
            if(socombo<combocomsobra){
              cout<<socombo<<endl;
            }else{
              cout<<combocomsobra<<endl;
            } 
          
        }
      }
 
  }
	return 0;
}

```