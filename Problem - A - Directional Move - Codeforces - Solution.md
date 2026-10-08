```c++
#include <bits/stdc++.h>
typedef long long ll;
using namespace std;
//'0', right. '1' left. left%4
int main() {
  ll ct;
  cin>>ct;
  
  while(ct--){
    ll n, uns=0, zeros=0, maior, resultado;
    cin>>n;
    char c;
    for(int i=0;i<n;i++){
      cin>>c;
      if(c=='1') uns++;
      else zeros++;
    }
 
  
  if(zeros == uns){
    cout<<"E"<<endl;
  }else{
    if(zeros > uns){
      // 0 0 0 0 0 
      zeros -= uns;
      resultado = (zeros%4) * 90;
    }else{
      uns -= zeros;
      resultado = 360 - ((uns%4) * 90);
    }
    
    if(resultado < 90){
      cout << "E" << endl;
    }else if(resultado < 180){ //s n
      cout << "S" << endl;
    }else if(resultado < 270){ // w e
      cout << "W" << endl;
    }else if(resultado < 360){
      cout << "N" << endl;
    }else{
      cout << "E" << endl; 
    }
  }  
  
    
    
  // }else{ 
  //     if(zeros == 0 && uns == 0){
  //       cout << "E" << endl;
  //     }else if(zeros == 0 && uns >= 1){
  //       //só tem 1
  //       resultado = uns % 4;
  //       resultado *= 90;
  //       resultado = 360 - resultado;
  //     }else if(uns == 0 && zeros >= 1){
  //       //só tem 0
  //       resultado = zeros % 4;
  //       resultado *= 90;
  //     }else{
  //       if(uns > zeros){
  //         // cout << "uns: " << uns << endl;
  //         // cout << "zeros: " << zeros << endl;
  //         uns -= zeros;
  //         // cout << "uns " << uns << endl;
  //         // cout << "teste: " << uns << endl;
  //         resultado = 360 - (uns*90);
  //       }else {
  //         zeros -= uns;
  //         // cout << "zeros " << zeros << endl;
  //         resultado = zeros * 90;
  //       }
        
  //       // // tem dos dois
  //       // int restoum = uns%4; // 0 3
  //       // int esquerda = 90*restoum;
  //       // int restozero = zeros%4; // 0 3
  //       // int direita = 90*restozero;
  //       // resultado = direita - esquerda;
        
  //       // if(resultado < 0){
  //       //   resultado = 360 - resultado;
  //       // }
  //     }
      
 
      
      
  //     // int restoum=uns%4; // 0 3
  //     // int restozero=zeros%4; // 0 3
  //     // int direita = 90*restozero;
  //     // int esquerda = 90*restoum;
  //     // resultado = abs(direita-esquerda);
 
  //     // if(uns>zeros){
  //     //   resultado=360-resultado;
  //     // }     
      
    // }    
  }
  
	return 0;
}
```