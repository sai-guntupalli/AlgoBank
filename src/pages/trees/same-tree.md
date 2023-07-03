---
title: Validate if two trees are same
description: Validate if two trees are same
---

[https://leetcode.com/problems/same-tree/](https://leetcode.com/problems/same-tree/)

Given the roots of two binary trees p and q, write a function to check if they are the same or not. Two binary trees are considered the same if they are structurally identical, and the nodes have the same value.

Input: p = [1,2,3], q = [1,2,3]

Output: true

## Solution

```js
from typing import Optional, List

class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

class Solution:
    def isSameTree(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:

        def validate(p, q):
            if not p and not q:
                return True
            elif not p or not q:
                return False
            else:
                return p.val == q.val and validate(
                    p.left, q.left) and validate(p.right, q.right)

        res = validate(p, q)
        return res

```
