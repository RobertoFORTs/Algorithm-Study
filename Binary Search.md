# Binary Search

✅ **Explanation**:  
Binary Search is a divide-and-conquer algorithm used to find an element in a **sorted** array. It repeatedly divides the search interval in half.

💡 **Use Cases**:
- Searching in sorted arrays
- Finding boundaries (e.g., first/last occurrence)
- Optimization problems (binary search on answer)

🧠 **Time Complexity**:
- Time: `O(log n)`
- Space: `O(1)` (iterative version)

🧪 **Java Code**:
```java
public int binarySearch(int[] arr, int target) {
    int left = 0, right = arr.length - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
