```c++
#include <bits/stdc++.h>
using namespace std;
 
int main() {
  int n;
  cin >> n;
  //map(nome, numero de vezes que tentaram adicionar ele)
  map<string, int> nomes;
 
  while(n--){
    string nome;
    cin >> nome;
    
    if(nomes.count(nome) > 0){
      // se ja existe
      // pega o valor do elemento, nomes.count(name);
      int valorAdicionar = 0;
      string valorAdicionarString;    
      
      //pega o numero de vezes que ja tentaram adicionar esse nome, para colocar no final do nome
      valorAdicionar = nomes[nome];
      valorAdicionarString = to_string(valorAdicionar);
      
      // soma em 1 o numero de vezes que ja tentaram adicionar esse nome
      nomes[nome]++;      
      
      //forma o novo nome, printa ele e cria nova key => key + elemento
      nome += valorAdicionarString;
      cout << nome << endl;
      nomes[nome] = 1; 
    }else{
      // se ainda nao existe, cria nova key => map(name, 5);
      nomes[nome] = 1;
      cout << "OK" << endl;
    } 
    
  }
  
	return 0;
}
 
 
      // //
      // // 
      
      // make_pair(1,3)
      // nome[nome]++;
 
      // nomes.count(name)
      
 
      // key elemento
```