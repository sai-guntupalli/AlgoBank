---
title: Find all lonley nodes in a tree
description: Find all lonley nodes in a tree.
---

[https://leetcode.com/problems/find-all-the-lonely-nodes/](https://leetcode.com/problems/find-all-the-lonely-nodes/)

In a binary tree, a lonely node is a node that is the only child of its parent node. The root of the tree is not lonely because it does not have a parent node.

Given the root of a binary tree, return an array containing the values of all lonely nodes in the tree. Return the list in any order.

Input: root = [7,1,4,6,None,5,3,None,None,None,None,None,2]

Output: [6,2]

## Solution

```js
from typing import Optional, List

class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def getLonelyNodes(self, root: Optional[TreeNode]) -> List[int]:
        lonley_nodes = []
        def find_lonley_nodes(root, parent):
            if not root:
                return

            if parent and (not parent.left or not parent.right):
                lonley_nodes.append(root.val)

            find_lonley_nodes(root.left, root)
            find_lonley_nodes(root.right, root)

        find_lonley_nodes(root, None)
        return lonley_nodes

```
