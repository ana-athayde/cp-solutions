```c++
#include <iostream>
#include <vector>
#include <string> 
 
using namespace std;
 
int main() {
    int n;
    string palavras, aux;
    vector <string> palavraMod;
    cin >> n;
    
    for (int i = 0; i < n; i++){
        cin >> palavras;
        if (palavras.length() > 10){
            aux = "";
            aux += palavras.front();
            aux += to_string(palavras.length()-2);
            aux += palavras.back();
            palavraMod.push_back(aux);
        } else {
            palavraMod.push_back(palavras);           
        }   
    }
    
    for (int i = 0; i < n ; i++){
        cout << palavraMod[i] << endl;
    }
    
	return 0;
}

```
