# 🚀 Day 22 – Binary Search

## 📌 Problem

Given a sorted array of integers `nums` and an integer `target`, return the index of `target` if it exists.

Otherwise, return `-1`.

You must write an algorithm with `O(log n)` runtime complexity.

### Example

```python
Input: nums = [-1,0,3,5,9,12], target = 9
Output: 4
```

Explanation:

```python
9 exists in nums and its index is 4.
```

---

# 💡 Approach – Binary Search

Binary Search works only on sorted arrays.

### Steps:

* Find the middle element
* Compare it with the target
* If target is smaller:

  * search left half
* If target is larger:

  * search right half
* Repeat until target is found or search space becomes empty

This reduces the search space by half every iteration.

---

# ⚙️ Python Solution

```python
class Solution:
    def search(self, nums, target):
        left = 0
        right = len(nums) - 1

        while left <= right:
            mid = (left + right) // 2

            if nums[mid] == target:
                return mid

            elif nums[mid] < target:
                left = mid + 1

            else:
                right = mid - 1

        return -1
```

---

# 🧠 Dry Run

Input:

```python
nums = [-1,0,3,5,9,12]
target = 9
```

| Left | Right | Mid | nums[mid] | Action         |
| ---- | ----- | --- | --------- | -------------- |
| 0    | 5     | 2   | 3         | Move Right     |
| 3    | 5     | 4   | 9         | Target Found ✅ |

Final Answer:

```python
4
```

---

# ⏱️ Complexity Analysis

| Complexity       | Value    |
| ---------------- | -------- |
| Time Complexity  | O(log n) |
| Space Complexity | O(1)     |

---

# 🧠 Key Learning

This problem teaches:

* Divide and conquer strategy
* Efficient searching
* Importance of sorted data

Binary Search is one of the most fundamental algorithms in computer science.

---

# ⚠️ Important Insight

The condition:

```python
while left <= right
```

is critical.

Using incorrect boundary conditions often causes infinite loops or missed answers.

---

# 🔗 LeetCode

Binary Search – LeetCode #704

---

# 📈 Progress Log

✅ Day 22 of DSA Journey
