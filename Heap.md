# 📚 Heap / Priority Queue

## ✅ O que é uma Heap?

Uma **Heap** é uma **árvore binária completa** que segue uma propriedade específica chamada de **propriedade da heap**:

- **Min-Heap**: o valor de cada nó é **maior ou igual** ao valor do seu pai → o **menor elemento** está na raiz.
- **Max-Heap**: o valor de cada nó é **menor ou igual** ao valor do seu pai → o **maior elemento** está na raiz.

Ela é comumente implementada como um **array** (ou vetor), onde para qualquer índice `i`:
- Filho esquerdo: `2*i + 1`
- Filho direito: `2*i + 2`
- Pai: `(i - 1) / 2`

## 🛠 Implementação em Java

Em Java, a classe `PriorityQueue<E>` da biblioteca padrão implementa um **min-heap** por padrão. Para um **max-heap**, usamos um comparador reverso (`Collections.reverseOrder()`).

### Min-Heap (default)
```java
PriorityQueue<Integer> minHeap = new PriorityQueue<>();
minHeap.add(10);
minHeap.add(5);
minHeap.add(20);
System.out.println(minHeap.poll()); // Saída: 5
```

### Max-Heap
```java
PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
maxHeap.add(10);
maxHeap.add(5);
maxHeap.add(20);
System.out.println(maxHeap.poll()); // Saída: 20
```
---
## 💡 Casos de uso

- Obter o **k menor** ou **k maior** elemento de uma coleção
- Algoritmos de **caminho mínimo** (ex: Dijkstra)
- **Merge** de múltiplas listas ordenadas
- **Agendamento de tarefas com prioridades**
- Sistemas de **cache** e **filas de eventos**

---

## ⏱ Complexidade de Tempo

| Operação                 | Complexidade |
|--------------------------|--------------|
| Inserção (`add`)         | O(log n)     |
| Remoção do topo (`poll`) | O(log n)     |
| Acesso ao topo (`peek`)  | O(1)         |
| Construção de heap       | O(n)         |

---

## 🧠 Complexidade de Espaço

- **Espaço total**: O(n), onde `n` é o número de elementos armazenados na heap.
- Utiliza array internamente, com redimensionamento dinâmico conforme necessário.

---

## 🏗 Estrutura Interna

A heap é mantida como um vetor para aproveitamento eficiente de memória e acesso direto aos filhos/pai via cálculo de índice.

### Cálculo dos índices:
- Filho esquerdo: `2*i + 1`
- Filho direito: `2*i + 2`
- Pai: `(i - 1) / 2`

### Exemplo (Min-Heap com array):
```
[5, 10, 20]
Representa:

    5
   / \
 10  20
```

