# 🚀 LeetCode 3201 – Max Length of Valid Subsequence I

This repo contains a clean Python solution for LeetCode [3201](https://leetcode.com/problems/find-the-maximum-length-of-valid-subsequence-i/).

## 🧠 Problem
Find the longest subsequence where the parity of the sum of every adjacent pair stays the same.

## 💡 Approach
- Try both cases:
  1. All pair sums are **even** → need same parity elements
  2. All pair sums are **odd** → need alternating parity
- Use greedy simulation to build the longest valid subsequence in both cases.

## ✅ Code Snapshot
```python
class Solution:
    def maximumLength(self, nums):
        def get_max_length(p):
            length, prev = 1, nums[0]
            for i in range(1, len(nums)):
                if (prev + nums[i]) % 2 == p:
                    length += 1
                    prev = nums[i]
            return length
        return max(get_max_length(0), get_max_length(1))

🔁 Example
Input: [1, 8, 4, 2, 4]
Output: 4

🙋‍♂️ Author
Made by Swayam Sharma 🧠✨
