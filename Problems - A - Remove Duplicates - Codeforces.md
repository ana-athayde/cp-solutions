```c++
#include <bits/stdc++.h>
typedef long long ll;
using namespace std;
                 
// map<elemento, posiçãoQualUltimaVezQueOElementoApareceu>
// passa para um vetor
// ordenar pela posições da menor para a maior
 
int main() {
  int n, valor, cont=0;
  cin>>n;
  int valores[n], posicao[1001];
  for(int i=0;i<1001;i++){
      posicao[i]=-1;
  }
  cont=n;
  for (int i=0;i<n;i++){
    cin>>valor;
    valores[i]=valor;
      if(posicao[valor]==-1){
        posicao[valor]=i;
      }else{
        valores[posicao[valor]]=-1;
        posicao[valor]=i;
        cont--;
 
      }
  }
  cout<<cont<<endl;
  for (int i=0;i<n;i++){
      if(valores[i]!=-1){
       cout<<valores[i]<<" ";
      }
  } cout<<endl;
  // v2=-1;
  // v2[1000]
  // v2[1]=2;
  // v2[2]=3;
  
  
	// cout<<"Hello";
	return 0;
}
```