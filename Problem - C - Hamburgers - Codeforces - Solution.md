```c++
#include <bits/stdc++.h>
typedef long long ll;
using namespace std;
 
string hamPer;
ll qnb, qns, qnc;
ll nb, ns, nc;
ll pb, ps, pc;
ll r;
 
 
bool solve(ll k){
    
    ll qtPaes, qtSalsi, qtChess;
    
    qtPaes = (qnb * k) - nb;
    qtSalsi = (qns * k) - ns;
    qtChess = (qnc * k) - nc;
    
    ll dinheiro = r;
    
    if(qtPaes > 0) dinheiro -= (qtPaes*pb);
    if(qtSalsi > 0) dinheiro -= (qtSalsi*ps);
    if(qtChess > 0) dinheiro -= (qtChess*pc);
 
    // cout << qtPaes << endl;
    // cout << qtSalsi << endl;
    // cout << qtChess << endl;
    
    // cout << dinheiro << endl;
 
    if(dinheiro < 0) return 0;
    else return 1;
}
 
int main() {
    cout.sync_with_stdio(0);
    cin.tie(0);
    
    cin >> hamPer;
    //pega quantidade de B, S, C, para o Hamburguer Perfeito:
    qnb = count(hamPer.begin(), hamPer.end(), 'B');
    qns = count(hamPer.begin(), hamPer.end(), 'S');
    qnc = count(hamPer.begin(), hamPer.end(), 'C');
    
    //leitura quantidade na casa dele, e no mercado
    cin >> nb >> ns >> nc;
    cin >> pb >> ps >> pc;
  
    cin >> r;
  
    // cout << solve(200000000002) << endl;
    //binary search, que vai ver todas as combinações de hamburguer
    //baseado na nossas função solve
    ll l = -1, r = 1e14;
    while(r > l+1){
        ll m = (l+r)/2;
        if(solve(m) == 1){
            l = m;
            //verdade
        }else{
            r = m;
        }
    }
    cout << l << endl;
    // cout << r << endl;
    
	return 0;
}
```