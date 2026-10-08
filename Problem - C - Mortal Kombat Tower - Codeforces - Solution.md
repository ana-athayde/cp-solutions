```c++
#include <bits/stdc++.h>
using namespace std;
 
vector<int> vec;
int n;
 
int teste(){
    int turno = 0;
    int posVec = 0;
    int skipPoints = 0;
 
    
    // 
    // 0 0 0 1 1
 
    /*
        
        0
            se vec[posvec] == 1
                pagamos a moeda
            se vec[posvec+1] == 1 && vec[posvec+2] == 1
                deixo o jogador 1 pegar essas posições
                posvec += 3
            senão
                se vec[posvec+1] == 1
                    deixo o jogador 1 pegar só a proxima posição
                    posvec += 2
                
    
    */
    for(int i=0; i<5; i++) vec.push_back(0);
    
    while(posVec<n){
        if(vec[posVec] == 1) skipPoints++;
        if(vec[posVec+1] == 1 && vec[posVec+2] == 1) posVec += 3;
        else if(vec[posVec+1] == 1) posVec += 2;
        else posVec++;
        
        // 1 0 0 0 0 0 0 | 0 0 0 0 0
        // if(turno == 0){
        //     if(vec[posVec] == 1) skipPoints++;
        //     posVec++;
        //     if(posVec<n && vec[posVec] == 0) posVec++;
        //     turno = 1;
        // }else if(turno == 1){
        //     posVec++;
        //     if(posVec<n && vec[posVec] == 1) posVec++;
        //     turno = 0;
        // }
    }
    return skipPoints;
}
 
int main() {
    int t; cin >> t;
  
    while(t--){
        cin >> n;
        vec.clear();
        for(int i=0; i<n; i++){
            int input; cin >> input;
            vec.push_back(input); 
        }      
        cout << teste() << endl;
    }
    return 0;
}
```