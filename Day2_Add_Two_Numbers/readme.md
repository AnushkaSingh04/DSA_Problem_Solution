# ➕ Add Two Numbers

## 📌 Problem Statement

Given two non-empty linked lists representing two non-negative integers, where digits are stored in **reverse order**, add the two numbers and return the sum as a linked list.

- Each node contains a single digit  
- No leading zeros except the number 0 itself  


---
LINK : https://leetcode.com/problems/add-two-numbers/description/
## 🧪 Example

**Input:**

l1 = [2,4,3]
l2 = [5,6,4]


**Output:**

[7,0,8]


**Explanation:**

342 + 465 = 807


---

## 🚀 Approach

- Use a dummy node to simplify list construction  
- Traverse both linked lists simultaneously  
- Add digits + carry  
- Store `(sum % 10)` in new node  
- Update carry using `(sum / 10)`  
- Handle remaining carry at the end  

---

## 🧾⏱️Code Complexity
- Time Complexity: O(max(n, m))
- Space Complexity: O(max(n, m))
