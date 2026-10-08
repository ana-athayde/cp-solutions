```c++
#include <bits/stdc++.h>
using namespace std;
#define INF 1e9
typedef unsigned long long ull;
typedef long long ll;
typedef pair <int,int> ii;
typedef vector<int> vi;
vector<vector<ii>> AL(30);
 
int main(){
    
    cout.sync_with_stdio(0);
    cin.tie(0);
    
        string a,b;cin>>a>>b;
        int n;cin>>n;
        for(int i=0;i<n;i++){
            char p,s;cin>>p>>s;
            int w;cin>>w;
            int v=p-'a';
            int u=s-'a';
            AL[v].push_back({u,w});
        }
 
        vector<vector<int>> distancia;
        for(int i=0;i<26;i++){
            vi dist(26, INF); dist[i] = 0;
            priority_queue<ii, vector<ii>, greater<ii>> pq;
            pq.emplace(0, i);
            while(!pq.empty()){
                auto[d, u] = pq.top(); pq.pop();
                if(d > dist[u]) continue;
                for(auto &[v, w] : AL[u]){
                    if(dist[u]+w >= dist[v]) continue;
                    dist[v] = dist[u]+w;
                    pq.emplace(dist[v], v);
                }
            }
            distancia.push_back(dist);
        }
        
        if(a.size()!=b.size()){
            cout<<-1<<endl;
            return 0;
        }
        
        int cont=0, flag=1;
        string frase;
        for(int i=0;i<a.size();i++){
            if(a[i]!=b[i]){      
                int mini=INF;
                char letra;
                for(int j=0;j<26;j++){
                    int a2=distancia[a[i]-'a'][j];
                    int b2=distancia[b[i]-'a'][j];
                    if(a2!=INF && b2!=INF){
                        if(a2+b2<mini){
                            mini=a2+b2;
                            letra=j+'a';
                        }
                    }    
                }      
                
                if(mini==INF){
                    flag=0;
                    break;
                }
                cont+=mini;
                frase+=letra;
            }else frase+=a[i];
        }
        
        if(flag==1) cout<<cont <<endl<< frase <<endl;
        else cout<<-1<<endl;
        
    return 0;
}
```