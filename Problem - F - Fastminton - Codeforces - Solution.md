```c++
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
typedef pair <int,int> ii;
int c, v[110], prefix[110];
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
    string s; cin>>s;
    
    //1-esquerda 2-direita
    int bola=1; //começa na esquerda
    int d=0, e=0; //pontos esq e dir
    int jd=0, je=0; //jogadas ganhas
    int andamento=-1;
    
    for(int i=0;i<s.size();i++){
      if(e>=5 && e-d>=2 || e>=10){
        je++;
        e=0;
        d=0;
        bola=1;
        if(je>=2)andamento=1;
      }
      if(d>=5 && d-e>=2 || d>=10){
        jd++;
        e=0;
        d=0;
        bola=2;
        if(jd>=2)andamento=2;
      }
 
 
      if(s[i]=='S'){
        if(bola==1) e++;
        else d++;
      }else if(s[i]=='R'){
        if(bola==1){
          d++;
          bola=2;
        }else{
           e++;
           bola=1;
        }
      }else{
        if(andamento==1){
          cout<<je<<" (winner) - "<<jd<<endl;
        }else if(andamento==2){
          cout<<je<<" - "<<jd<<" (winner)"<<endl;
        }else{
          if(bola==1)cout<<je<<" ("<<e<<"*) - "<<jd<<" ("<<d<<")"<<endl;
          else cout<<je<<" ("<<e<<") - "<<jd<<" ("<<d<<"*)"<<endl;
          
        }
      }
      
    }
 
 
 
  
    return 0; 
}

```