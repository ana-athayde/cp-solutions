```c++
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
    
    int t; cin >> t;
    while(t--){
      int n, a, b; cin >> n >> a >> b;
     // cout <<  "a: "<< a << endl;
      int ans[n+1]; 
      int contMaior=n-a+1, contMenor=b;
      int mid=n/2;
      if(b>a){
        contMenor--;
        contMaior--; 
      }
      
      if(contMaior >= mid && contMenor >= mid){
         ans[0] = a; 
         ans[n/2] = b; 
         
        int cont=n;
        if(n==b) cont--;
        //  for(int i=1; i<n/2; i++){
           int i=1;
           while(i<n/2){
             if(cont!= a && cont!=b){
             ans[i] = cont; 
             i++;
           }
            cont--;
              
           }
           
        //  }
         
         cont=1;
         if(a==1) cont++;
        //  for(int i=n-1; i>n/2; i--){
           i=n-1;
           while(i>n/2){
             if(cont!= a && cont!=b){
              ans[i] = cont; 
              i--;
           }
           cont++;
           }
           
             
        //  }
         
         
         for(int i=0; i<n; i++){
           cout << ans[i] << " ";
         }
         cout << endl;
      }
      else cout << -1 << endl;
      // cout << mid << " "<< contMaior << " "<< contMenor << endl; 
     
    
    }
    
     
     
    return 0; 
 
}
```