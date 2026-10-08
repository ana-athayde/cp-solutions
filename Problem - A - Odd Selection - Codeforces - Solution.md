```C++
#include <bits/stdc++.h>
using namespace std;
 
int main() {
    int t;
    
    cin >> t;
    
    while(t--){
        int n, x, impar = 0, par = 0, numeroEscolhidosImpar = 0;
        cin >> n >> x;
        long long int vetor [n];
        
        for(int i=0; i<n; i++){
          cin >> vetor[n]; 
          if(vetor[n]%2 == 0){
            par++;
          }else{
            if(impar <= x){
              impar++;
            }
            
          }
        }
        
        //cout << "Numero impares: " << impar << endl;
        // par+par+par+impar+impar (impar)
        //se nao tiver nenhum impar, a soma nao pode ser impar
        //se nao tiver par, se x for div por 2 NAO caso contrario SIM
        // Key Idea: The sum of x numbers can only be odd if we have an odd number of numbers 
        // which are odd.
       // impar <= x;
        
   // 11 14 1 6 3 12 3 20 16 - 4 imp
   // (1 3) (3) 1 6 12 14 
         //x=7
        //só conta os impares <= x  => se essa quantidade for impar então pode
        //9 7 => 7 
        
        //impar < x 
        if(impar == 0){
          cout << "No" << endl; 
        }else if(par>=1){// tem que ter pares suficientes para suprir x (quantidades de numeros que ele quer)
          //if()
          
        if(impar%2 != 0){ // pode ser menor que x
          cout << "Yes" << endl; 
        }else{
 
          if(par >= x - (impar-1)){
            cout << "Yes" << endl;
          }else{
            cout << "No" << endl;
          }
        }
        }else{
          if(x%2==0) cout<<"No"<<endl;
          else cout << "Yes"<<endl;
        }
        
 
          //impar < x
          //impar == x
        //   numeros de impar == par 
        //   impar--;
        //   (impar-1) compara com alguma coisa;
        //   se tem par o suficiente para completar a quantidade de numeros === x;
        //   par >= x - (impar-1);
          
        //   if(impar  x){
        //     impar=x x%2!=0 VDD
        //     impar=x par>0 VDD
        //   }
        //   3 3 3 3 3 
        //   x=4 
        // }
        
        // if (impar == 0){
        //   cout << "No" << endl;
        // }else if(impar < x){
        //   if(impar%2 == 0){
        //    if(par >= (x-impar)){
        //     impar --;
        //     cout << "Yes" << endl; 
        //    }else{
        //      cout << "No" << endl;
        //    }
          
        //  }else{
            
        //     cout << "Yes" << endl;
        //   }
          // impar%2 == 0
          
          // excluir um impar, troca pelos pares
          
          // if(par>0){
            
          // }
          //if(impar%2 == 0 && pares>impar-1){
           // cout << "impares: " << impar << endl;
          //  cout << "Yes" << endl;  
          //}else{
          //  cout << "impares: " << impar << endl;
          //  cout << "Teste" << endl;
           // cout << "No" << endl;
          //}
          //101 102 103
          //if(par>0 && x<=n-1){
         //   cout<< "Yes"<<endl;
         // }else{ 
        //    cout << "No" << endl;
        //  }
          
        // }else if (impar%2 != 0){            
        //   cout << "Yes" << endl;
        // }else{
        //   cout << "No" << endl;
        // }
 
        
    }   
      
    return 0;
}

```