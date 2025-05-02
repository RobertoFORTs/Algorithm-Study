# 3. Depth-First Search (DFS) & Breadth-First Search (BFS)

## ✅ Explicação

### Depth-First Search (DFS)

DFS (Busca em Profundidade) explora um grafo ou árvore indo o mais fundo possível em cada ramificação antes de retroceder (backtracking). Pode ser implementado de forma recursiva ou usando uma pilha (stack).

- **Estrutura usada:** Pilha (stack) ou recursão.
- **Ordem de visita:** Vai o mais fundo possível antes de voltar e explorar os vizinhos restantes.

### Breadth-First Search (BFS)

BFS (Busca em Largura) explora todos os nós no mesmo nível antes de avançar para o próximo nível.

- **Estrutura usada:** Fila (queue).
- **Ordem de visita:** Nível por nível (level-order traversal).

---

## 💡 Casos de Uso

| Problema | DFS | BFS |
|---------|-----|-----|
| **Travessia de grafos** | ✅ | ✅ |
| **Verificação de conexões** | ✅ | ✅ |
| **Detecção de ciclos** | ✅ | ✅ |
| **Problemas de labirinto/ilhas** | ✅ | ✅ |
| **Caminho mais curto em grafos não ponderados** | ❌ | ✅ |
| **Ordenação topológica (DAGs)** | ✅ | ❌ |
| **Componentes conexos** | ✅ | ✅ |
| **Problemas de backtracking (ex: sudoku, quebra-cabeças)** | ✅ | ❌ |

---

## 🔁 Variações de Uso

### DFS

- **Pré-ordem / Pós-ordem em árvores**
- **Detecção de ciclo (com stack de chamada)**
- **Ordenação topológica**
- **Encontrar componentes fortemente conectados (Kosaraju, Tarjan)**

### BFS

- **Busca de caminho mínimo (grafo não ponderado)**
- **Flood fill (ex: problemas de imagem, ilhas)**
- **Busca bidirecional (duas BFS simultâneas)**
- **Nível mais próximo com certa condição (ex: menor distância até X)**

---

## 🧠 Complexidade de Tempo

DFS e BFS percorrem todos os vértices e arestas uma única vez:
**O (V + E)**

- `V`: número de vértices (nodes)
- `E`: número de arestas (edges)

---

## 🧪 Exemplo em Java

```java
// DFS - Depth-First Search
public void dfs(Map<Integer, List<Integer>> graph, int node, Set<Integer> visited) {
    if (visited.contains(node)) return;
    visited.add(node);
    for (int neighbor : graph.get(node)) {
        dfs(graph, neighbor, visited);
    }
}
```
```java
// BFS - Breadth-First Search
public void bfs(Map<Integer, List<Integer>> graph, int start) {
    Queue<Integer> queue = new LinkedList<>();
    Set<Integer> visited = new HashSet<>();
    queue.add(start);
    visited.add(start);

    while (!queue.isEmpty()) {
        int node = queue.poll();
        for (int neighbor : graph.get(node)) {
            if (!visited.contains(neighbor)) {
                visited.add(neighbor);
                queue.add(neighbor);
            }
        }
    }
}
```
