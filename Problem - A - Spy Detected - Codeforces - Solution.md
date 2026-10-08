```c++
#include <iostream>
using namespace std;
 
int main() {
  int casosTeste, numeros, aux, posicaoAux;
  cin >> casosTeste;
  
  for (int i=0; i<casosTeste; i++) {
    cin  >> numeros;
    int vetor [numeros];
    
    for (int j=0; j<numeros; j++) {
      cin >> vetor[j]; 
    }
  
    for (int j=0; j<numeros; j++) {
      if (j == 0) {
        aux = vetor[j];
        posicaoAux = j;
      } else {
        if (aux != vetor[j]){
          if (vetor[j] == vetor[j+1]) { 
            aux = vetor[j];
            posicaoAux = j-1;
          } else {
            posicaoAux = j;
          }    
        }
      }
    }
  cout << posicaoAux+1 << endl;
  }
  return 0;
}
```