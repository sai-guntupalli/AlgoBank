---
title: Binary Search Tree
description: Binary Search Tree Basics.
---

## Find Minimum value in BST

### Solution

```js
def find_min(node):
    while node and node.left:
        node = node.left

    return node.val

```

## Find Maximum value in BST

### Solution

```js
def find_max(node):
    while node and node.right:
        node = node.right

    return node.val

```

## Search for a Value

### Solution

```js
def search_node(node, val):
    if node.val == val:
        return True

    if val <= node.val and node.left:
        return search_node(node.left, val)
    elif val >= node.val and node.right:
        return search_node(node.right, val)
    else:
        return False
```
