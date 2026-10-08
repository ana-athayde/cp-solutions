```c++
#include <bits/stdc++.h>
using namespace std;
 
int main() {
	int n, soma = 0;
    cin >>  n;
    vector<int> vec;
    
    for(int i=0; i<n; i++){
        int input;
        cin >> input;
        vec.push_back(input);
    }
    
    if(n == 1){
        cout << 1 << ' ' << 0 << endl;
        return 0;
    }
    
    int barAlice = 0, posAlice = 0, barBob = 0, posBob = n-1;
    
    while(n > (barAlice+barBob)){
            if(vec[posAlice] > vec[posBob]){
                // se o tempo da alice for maior, o bob anda um
                vec[posAlice] -= vec[posBob];
                posBob--;
                barBob++;
                
                if(posAlice == posBob){
                    barAlice++;
                    break;
                }
            }else if(vec[posBob] > vec[posAlice]){
                // se o tempo do bob for maior, alice anda um
                vec[posBob] -= vec[posAlice];
                posAlice++;
                barAlice++;
                if(posAlice == posBob){
                    barBob++;
                    break;
                }
            }else if(vec[posAlice] == vec[posBob]){ //se o tempo dos dois forem iguais           
                //se chegaram ao mesmo tempo, e o bob nao estava antes              
                barAlice++;
                barBob++;
                posAlice++;
                posBob--;
                if(posAlice == posBob){
                    barAlice++;   
                }
            }
    }
 
    cout << barAlice << " " << barBob << endl;
 
	return 0;
}
```