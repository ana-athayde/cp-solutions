```c++
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
ll k,x;
 
 
 
ll quantidadeCarinha(ll mid){
  ll num=0;
  if(mid<=k) num=(mid*(mid+1))/2;
  else{
    num+=(k*(k+1))/2;
    num+=((k-1)*k)/2;
    num-=((2*k-1-mid)*(2*k-mid))/2;
    }
    return num;
}
 
 
 
 
 
int main(){
 
    cout.sync_with_stdio(0);
    cin.tie(0);
    int t;cin>>t;
 
   while(t--){
     cin>>k>>x;
     ll esq=1, dir=2*k-1, mid=0, r=1;
    //  cout<<x<<endl;
     while(esq<=dir){
       mid=(esq+dir)/2;
       ll qnt=quantidadeCarinha(mid);
       if(qnt>x){
         dir=mid-1;
       }else{
         r=mid;
         esq=mid+1;
       } 
     }
     if(quantidadeCarinha(r)==x) cout<<r<<endl;
     else if(r==2*k-1)cout<<r<<endl;
     else cout<<r+1<<endl;
     
   }
         
    return 0; 
 
}
```