# 🔟 Fibonacci (Clássico para Recursão e Programação Dinâmica)

## ✅ Explicação

A sequência de Fibonacci é definida como:

- F(0) = 0
- F(1) = 1
- F(n) = F(n-1) + F(n-2) para n > 1


Cada número é a soma dos dois anteriores.

---

## 💡 Casos de Uso

- Introdução à Programação Dinâmica
- Modelagem de crescimento de populações, árvores, etc.
- Problemas de contagem (ex: número de formas de subir escadas)
- Sequências matemáticas e algoritmos de otimização

---

## 🧠 Complexidade

| Abordagem           | Complexidade |
|---------------------|--------------|
| Recursiva ingênua   | O(2ⁿ)        |
| Recursiva com memo  | O(n)         |
| Iterativa / DP      | O(n)         |
| DP com espaço otimizado | O(n) tempo / O(1) espaço |

---

## 🧪 Implementação em Java

### ✅ Recursiva com Memoization (Top-down)

```java
public int fib(int n, Map<Integer, Integer> memo) {
    if (n <= 1) return n;

    if (memo.containsKey(n)) return memo.get(n);

    int result = fib(n - 1, memo) + fib(n - 2, memo);
    memo.put(n, result);

    return result;
}
```

### Iterativa com Programação Dinâmica (Bottom-up)

```java
public int fibDP(int n) {
    if (n <= 1) return n;

    int[] dp = new int[n + 1];
    dp[0] = 0;
    dp[1] = 1;

    for (int i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }

    return dp[n];
}
```

### Otimizada com Espaço constante

```java
public int fibOptimized(int n) {
    if (n <= 1) return n;

    int a = 0, b = 1;
    for (int i = 2; i <= n; i++) {
        int temp = a + b;
        a = b;
        b = temp;
    }

    return b;
}
```

