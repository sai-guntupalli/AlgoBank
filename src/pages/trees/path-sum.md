---
title: Path Sum
description: Path Sum
---

[https://leetcode.com/problems/path-sum/](https://leetcode.com/problems/path-sum/)

Given the root of a binary tree and an integer targetSum, return true if the tree has a root-to-leaf path such that adding up all the values along the path equals targetSum. A leaf is a node with no children.

Input: root = [5,4,8,11,null,13,4,7,2,null,null,null,1], targetSum = 22

Output: true

## Solution

```js
from typing import Optional

class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

class Solution:
    def hasPathSum(self, root: Optional[TreeNode], targetSum: int) -> bool:

        def hasSum(root, target):
            if not root:
                return False

            if not root.left and not root.right and root.val == target:
                return True

            return hasSum(root.left, target - root.val) or hasSum(
                root.right, target - root.val)

        return hasSum(root, targetSum)

```
