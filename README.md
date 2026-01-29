# LeetCode: Contains Duplicate (217)

## Problem Description
Given an integer array `nums`, return `true` if any value appears at least twice in the array, and return `false` if every element is distinct.

## Solution Approach
The initial approach using an `ArrayList` resulted in a **Time Limit Exceeded (TLE)** error due to the $O(n^2)$ complexity of the `.contains()` method.

### Optimized Implementation
I optimized the solution using a **HashSet**, which allows for $O(1)$ average time complexity for both insertions and lookups. 

- **Time Complexity:** $O(n)$ — We traverse the array once.
- **Space Complexity:** $O(n)$ — In the worst case, we store all elements in the set.

## Code
```java
import java.util.HashSet;

class Solution {
    public boolean containsDuplicate(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        for (int num : nums) {
            if (!set.add(num)) return true;
        }
        return false;
    }
}
