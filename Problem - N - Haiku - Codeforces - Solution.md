```c++
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
    
    int t;cin>>t;
    while(t--){
      int n1,n2,n3; cin>>n1>>n2>>n3;
      string a="", b="", c="";
      for(int i=0;i<n1;i++){
        string x;cin>>x;a+=x;
      }
      for(int i=0;i<n2;i++){
        string x;cin>>x;b+=x;
      }
      for(int i=0;i<n3;i++){
        string x;cin>>x;c+=x;
      }
      
      int contVA=0, contYA=0, flag=1;
      for(int i=0;i<a.size();i++){
        char aux=tolower(a[i]);
        if(aux=='a'|| aux=='e' || aux=='i' || aux=='o'||aux=='u' ) contVA++;
        if(aux=='y') contYA++;
      }
      
  
      if(contVA>5) flag=0;
      if(contVA+contYA<5) flag=0;
      
      int contVB=0, contYB=0;
      for(int i=0;i<b.size();i++){
        char aux=tolower(b[i]);
        if(aux=='a'|| aux=='e' || aux=='i' || aux=='o'|| aux=='u' ) contVB++;
        if(aux=='y') contYB++;
      }
      
      if(contVB>7) flag=0;
      if(contVB+contYB<7) flag=0;
      
      int contVC=0, contYC=0;
      for(int i=0;i<c.size();i++){
        char aux=tolower(c[i]);
        if(aux=='a'|| aux=='e' || aux=='i' || aux=='o'||aux=='u' ) contVC++;
        if(aux=='y') contYC++;
      }
      if(contVC>5) flag=0;
      if(contVC+contYC<5) flag=0;
       
      if(flag==0) cout<<"NO"<<endl;
      else cout<<"YES"<<endl;
      
      
      
      
    }
    
    
    
     
     
    return 0; 
 
}
 
```