## 📅 Day 1 - Two Sum

### 🧠 Problem Summary

Given an array `nums` and a target value, find **two indices** such that their elements add up to the target.

* Each input has **exactly one solution**
* Same element cannot be used twice
* Return indices in any order

---
**LINK:** https://leetcode.com/problems/two-sum/description/

### 💡 Approach 1: Brute Force

**Idea:**
Check every possible pair and see if their sum equals the target.

**Steps:**

1. Run two loops:

   * Outer loop → pick first element
   * Inner loop → check all elements after it
2. If `nums[i] + nums[j] == target`, return `[i, j]`

**Time Complexity:** ⏱️ `O(n²)`
**Space Complexity:** 🧠 `O(1)`

---

### 💡 Approach 2: Two Pointer (Better but NOT valid here directly)

**Idea:**
Sort the array and use two pointers:

* One at start (smallest)
* One at end (largest)

**Steps:**

1. Sort the array
2. Initialize:

   * `left = 0`
   * `right = n - 1`
3. While `left < right`:

   * If sum < target → move left++
   * If sum > target → move right--
   * If equal → found answer

⚠️ **Important Note:**
This approach **does NOT work directly** because:

* Sorting changes original indices
* Problem requires **original indices**

👉 Can only be used if:

* You store indices along with values OR
* Problem asks only for values

**Time Complexity:** ⏱️ `O(n log n)` (due to sorting)

---

### 💡 Approach 3: Optimized (Hash Map) ✅

**Idea:**
Instead of checking all pairs, store elements in a hashmap and check if the **required pair already exists**.

**Concept:**
If

```
first + second = target
=> second = target - first
```

**Steps:**

1. Create a hashmap `m` → (value → index)
2. Traverse array:

   * Let `first = nums[i]`
   * Compute `second = target - first`
3. Check:

   * If `second` exists in map → return indices
4. Else:

   * Store `first` in map

---

### ⚙️ Code (C++)

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int,int> m;

        for(int i = 0; i < nums.size(); i++) {
            int first = nums[i];
            int second = target - first;

            if(m.find(second) != m.end()) {
                return {m[second], i};
            }

            m[first] = i;
        }
        return {};
    }
};
```

---

### ⏱️ Complexity

| Approach    | Time Complexity | Space Complexity |
| ----------- | --------------- | ---------------- |
| Brute Force | O(n²)           | O(1)             |
| Two Pointer | O(n log n)      | O(1)             |
| Hash Map    | O(n)            | O(n)             |

---

### 📌 Key Takeaways

* Hashing is the **most efficient approach** for lookup problems
* Always try to convert:

  ```
  a + b = target  →  b = target - a
  ```
* Use `unordered_map` for **O(1)** average lookup
* Store values **after checking**, not before (important!)

---

