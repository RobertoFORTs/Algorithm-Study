# Two Pointers / Sliding Window

✅ **Explanation**:  
Two pointers is a technique for solving problems involving sorted arrays or strings, using two indices moving through the structure.  
Sliding window is a variation used to find subarrays or substrings with certain properties efficiently.

💡 **Use Cases**:
- Removing duplicates from sorted arrays
- Max/min in subarrays
- Longest substring with constraints

🧠 **Time Complexity**:
- Typically `O(n)`

🧪 **Java Code**:
```java
// Example: Longest substring without repeating characters
public int lengthOfLongestSubstring(String s) {
    Set<Character> seen = new HashSet<>();
    int left = 0, right = 0, maxLength = 0;

    while (right < s.length()) {
        if (!seen.contains(s.charAt(right))) {
            seen.add(s.charAt(right++));
            maxLength = Math.max(maxLength, right - left);
        } else {
            seen.remove(s.charAt(left++));
        }
    }
    return maxLength;
}
```
  **Another Sliding Window Impl**
```java
public int minSubArrayLen(int target, int[] nums) {
    int left = 0, sum = 0, minLength = Integer.MAX_VALUE;

    for (int right = 0; right < nums.length; right++) {
        sum += nums[right];

        while (sum >= target) {
            minLength = Math.min(minLength, right - left + 1);
            sum -= nums[left++];
        }
    }

    return (minLength == Integer.MAX_VALUE) ? 0 : minLength;
}

```
