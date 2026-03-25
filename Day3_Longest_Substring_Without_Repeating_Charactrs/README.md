# 🔠 Longest Substring Without Repeating Characters

## 📌 Problem Statement

Given a string `s`, find the length of the **longest substring** without repeating characters.

- A substring is a contiguous sequence of characters.
- The answer must be a substring, not a subsequence.

---
LINK : https://leetcode.com/problems/longest-substring-without-repeating-characters/

## 🧪 Examples

### Example 1

**Input:**

s = "abcabcbb"


**Output:**

3


**Explanation:**  
"abc" is the longest substring without repeating characters.

---
### Example 2

**Input:**

s = "pwwkew"


**Output:**

3


**Explanation:**  
"wke" is the longest substring.

---

## 🚧 Approaches

### 1️⃣ Brute Force

- Generate all substrings
- Check for duplicates
- Track maximum length

**Time Complexity:** `O(n²)`  
**Space Complexity:** `O(256)`

---

### 2️⃣ Sliding Window + Hashing (Optimized)

- Use two pointers (`l`, `r`)
- Store last index of characters in hash array
- Move left pointer when duplicate appears
- Update maximum length

**Time Complexity:** `O(n)`  
**Space Complexity:** `O(256)`

