## Quando usar
- inserir/remover nas duas pontas

## Operações
- push_front / push_back → O(1)

## Problemas comuns
- sliding window

## Exemplo

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    deque<int> dq;

    dq.push_back(1);
    dq.push_front(2);

    cout << dq.front(); // 2
}
```

## Problemas relacionados