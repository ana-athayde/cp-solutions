```c++
#include <bits/stdc++.h>
#include <iostream>
using namespace std;
 
/*
  Cantinho do jnk
  
    1123121312312
    
    
    busca binaria
     +
    soma de prefixos
 
  
*/
 
int main() {
    //Two cakes
    int n;
    cin >> n;
    vector<int> vec;
    vector<vector<int>> vect(2*n, vector<int>(2));
    
    //int arr[2*n][2];
    // { (1,2) , (2,2) , (2,3)}
    //
 
    for(int i=0; i<2*n; i++){
        int input;
        cin >> input;
        vect[i][0] = input;
        vect[i][1] = i;
    }
    sort(vect.begin(), vect.end());
    
    
    // da os pares para cada um
    // Sasha os pares
    // Dimis os impares
    // soma da diferença das distancias = minima distancia 
    long long int distanciaMinima = vect[0][1] + vect[1][1];
    
    for(int i=2; i<2*n; i++){
        if(i%2 == 0){
          distanciaMinima += abs(vect[i-2][1] - vect[i][1]);
        }else{
          distanciaMinima += abs(vect[i-2][1] - vect[i][1]);
        }
    }  
    
    cout << distanciaMinima << endl;
    
    // 4
    // 4 1 3 2 2 3 1 4
    
    
    
    
    //   0    1        2     3
    //(1, 2) (1, 7) (2, 4) (2, 5)
     //         1             3            5              7
              
    //1 1 2 2 3 3
    
    //1 1 2 2 3 3
    
    //(1,1) (1,2) (2,3) (2,4) (3,5) (3,6)          
    
    // monta os pares (numero, posicaoCasa)
    // ordena pelo numero
 
    
    
    
    return 0;
}
```