
# 📘 Binary Search Summary

## 🔍 What is Binary Search?

Binary Search is an efficient algorithm to find the position of a target value within a **sorted** array or list. It repeatedly divides the search interval in half, eliminating half of the elements each time.

---

## ⚙️ How It Works

1. Start with the entire sorted array.
2. Find the middle element.
3. Compare the middle element with the target:
   - If equal → 🎯 Return the index.
   - If target < middle → 🔽 Search the **left half**.
   - If target > middle → 🔼 Search the **right half**.
4. Repeat until the interval is empty (target not found).

---

## 🧠 Key Properties

| Property          | Value                                |
|------------------|--------------------------------------|
| Time Complexity   | `O(log n)`                           |
| Space Complexity  | `O(1)` (iterative) or `O(log n)` (recursive) |
| Input Requirement | Array must be **sorted**             |

---

## ✅ Example (Iterative in Java)

```java
public int binarySearch(int[] nums, int target) {
    int left = 0, right = nums.length - 1;
    
    while (left <= right) {
        int mid = left + (right - left) / 2;
        
        if (nums[mid] == target)
            return mid;
        else if (nums[mid] < target)
            left = mid + 1;
        else
            right = mid - 1;
    }
    
    return -1; // Not found
}
```

---

## 🆚 Linear Search vs Binary Search

| Feature         | Linear Search | Binary Search  |
|----------------|----------------|----------------|
| Time Complexity| `O(n)`         | `O(log n)`     |
| Sorted Input   | Not required   | Required       |
| Performance    | Slower for large datasets | Much faster |

---

## ⚠️ Common Pitfalls

- ❌ Using binary search on an **unsorted array**
- ⚠️ Integer overflow with `mid = (left + right) / 2` (prefer `left + (right - left) / 2`)
- 🔁 Infinite loop if update conditions (`left` and `right`) are incorrect

---

## 🧪 Variants

- Find **first or last occurrence** of a duplicate
- Search in **rotated sorted arrays**
- Find the **smallest/largest value** that satisfies a condition
