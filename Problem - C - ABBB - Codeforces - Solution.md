```c++
#include <iostream>
using namespace std;
 
int main() {
  int n, aux, i,j, e;
  string teste;
  
  cin >> n;
	
  for (int k=0; k<n; k++){
    cin >> teste;   
   
    i = 0;
    j = 1;
    aux = 0;
    e = 0;
    
      
    while(j <= teste.length()){  
      if (teste[j] == 'B'){      
        if(aux == 0){
          i = j+1;
          j += 2; 
    
        }else{
          i -= 1;
          j += 1;
          aux -= 1;
        }      
      e += 2;
      }else{
          j += 1;
          i += 1;
          aux +=1;          
      }  
    }
    cout << teste.length() - e << endl;     
 
  }
	return 0;
}
```