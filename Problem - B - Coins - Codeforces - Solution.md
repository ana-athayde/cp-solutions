```c++
#include <iostream>
using namespace std;
 
int main() {
  int a = 3, b = 3, c = 3;
  
  for(int i=0; i<3; i++){
    string s;
    cin >> s;
    if(s[1] == '<'){
      char aux = s[0];
      s[0] = s[2];
      s[1] = '>';
      s[2] = aux;
    }
    if(s[0] == 'A'){
      a--;
    }else if(s[0] == 'B'){
      b--;
    }else{
      c--;
    }   
  }
  
  if(a == b || b == c || a == c){
    cout << "Impossible" << endl;
  }else{
    if(a > b && a > c){
      if(b > c){
        cout << "ABC" << endl;
        //a b c
      }else{
        cout << "ACB" << endl;
        //a c b
      }
    }else if(b > a && b > c){
      if(a > c){
        cout << "BAC" << endl; 
        //b a c
      }else{
        cout << "BCA" << endl;
        //b c a
      }
    }else{
      if(a > b){
        cout << "CAB" << endl;
        //c a b
      }else{
        cout << "CBA" << endl;
        //c b a
      }
    }
  }
  
  
 
  
  // cout << a << endl;
  // cout << b << endl;
  // cout << c << endl;
	return 0;
}
```