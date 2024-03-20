# Rekomendacje
- biblioteczka podstawowych implementacji algorytmów

# Grafy
## Sposoby reprezentacji grafów
- lista sąsiedztw `vector<vector<int>> adj(n)`
- macierz sąsiedztw
## Algorytmy przeszukiwania grafu
### Depth-First Search
#### Działanie
- Wybieramy wierzchołek startowy
- Dodajemy wierzchołek do listy odwiedzonych
- Wywołujemy rekurencyjnie z pierwszym dzieckiem
- Gdy nie ma dzieci to wracamy
#### Przykładowa implementacja
```cpp
vector<vector<int>> adj(n, vector<int>());
vector<bool> visited(n, false); // shorthand for n-elements initialized to 'false'
void dfs(int v) {
    visited[v] = true;
    for(int u : adj[v]) {
        if(!visited[u]) dfs(u);
    }
}

// Weighted graph - init
vector<vector<pair<int, int>>> wAdj(n);

// entering data
using namespace std;
int n, m; // vertices, edges
for(int i = 0; i < m; i++>) {
    cin >> a >> b >> w;
    wAdj[a].pushback({b, w});
    wAdj[b].pushback({a, w});
}

```
### Breadth-First Search
#### Działanie
- Wybieramy wierzchołek startowy
- Dodajemy wierzchołek do listy odwiedzonych
- Idziemy poziomami, preferując dzieci najbliżej wierzchołka startowego
#### Przykładowa implementacja
```cpp
void bfs(int v) {
    vector<vector<int>> adj(n, vector<int>());
    visited[v] = true;
    for(int u : adj[v]) {
        if(!visited[u]) dfs(u);
    }
}
```
### A*
### Djikstry
### Bellmana-Forda na relaksację krawędzi
# Inne przydatne rzeczy
## Modulo i inwersja
1e9+7 = 1 000 000 007\
(a + b)%MOD = (a%MOD + b%MOD)%MOD\
(a - b)%MOD = ...\
(a * b)%MOD = ...\
(a / b)%MOD = 
\
Wyprowadzenie:\
`a^(p-1)` przystaje do 1 (mod p), czyli `a^(p-1)%p = 1`\
Z `a*a^-1 = 1` wynika, że skoro `a*a^(p-2) = 1 (mod p)`, to `a^(p-2) = a^-1`\
Nasz bardzo wysoki wykładnik to MOD,
więc (18/6)%7 to (18*6^5)%7
### Szybkie potęgowanie
W czasie O(logn) można obliczyć a^n, poprzez liczenie a*a, potem to ^2, itd...\
Przykład: 6^1023 = 6^(1+2+4+8+16+...+512)
### Implementacja
```cpp
int fastPow(int a, int n) {
    if (!n) return 1;
    if (n%2) return n*fastPow(a, n-1);
    int w = fastPow(a, n/2);
    return w*w;
}
```
# Struktury danych
