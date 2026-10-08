```c++
#include<bits/stdc++.h>
#include <iostream>
using namespace std;
 
int main() {
  //Beautiful Paintings
  int n, repetidos = 0;
  cin >> n;
  vector<int> vec;
  set <int> conjunto;
  
  for(int i=0; i<n; i++){
    int input;
    cin >> input;
    if(conjunto.find(input) != conjunto.end()){ // não esta entrando aqui?
      vec.push_back(input);
      repetidos++;
    }
    conjunto.insert(input);
  }
  
  if(conjunto.size() == n){
    cout << n-1 << endl;
  }else{
    sort(vec.begin(), vec.end());
    // sort na lista dos repetidos, para ficar do menor para o maior
    // agora lidar com os que são iguais
    // criar um laço de repetição que passa pelo array de repetidos
    // se sou diferente do proximo e ja repeti duas vezes
    // 4  9 100 4 9 100 9
    int numeroMax = conjunto.size()-1;
    
    while(vec.size() > 0){
        int elmentoAtual = vec[0];
        for(int i=0; i<vec.size(); i++){
            if(vec[i] > elmentoAtual){
                elmentoAtual = vec[i];
                vec.erase(vec.begin()+i); 
                i--;
                numeroMax++;
            }
        }
        vec.erase(vec.begin());
    }
    
    cout << numeroMax << endl;
    // int aux = 0, numeroMax;
    // if(vec[i] < ultimoAdicionado){
    //   // ele iria excluir da lista de repetidos
    //   // cada vez que vai de um menor pra maior soma no numero Max     
    //   ultimoAdicionado = vec[i];
    //   vex.erase(vex.begin() + i);
    //   aux++;
    //   if(aux == 2){
    //     numeroMax ++;
    //     aux = 0;
    //   }
    // }
    // 4 4 9 9 9 100 100 100
    // 4 9 100 4 9 100
  }
  
//   cout << "repetidos: " << endl;
//   for (auto i = vec.begin(); i != vec.end(); ++i)
//         cout << *i << " ";
  
//   cout << " " << endl;
//   cout << "Nao repetidos: "<< endl;
//   set<int >::iterator it ;
//   for (it = conjunto.begin() ; it != conjunto.end() ; it++ ) {
//     cout << *it<<" ";
//   }
    
//   cout << " " << endl;
//   cout << "repetidos: " << repetidos << endl;
//   cout << "diferentes: " << conjunto.size() << endl;
    
  //if(conjunto.find())
  //for(int i=0; i<n; i++){
  //  cout << arr[i] << endl;
  //}
  
	return 0;
}

```