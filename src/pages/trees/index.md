---
title: Trees
pageTitle: CacheAdvance - Never miss the cache again.
description: Cache every single thing your app could ever do ahead of time, so your code never even has to run at all.
---

## Tree Terminology

**Vertex/Node** : It contains the key or value or pointers to child vertex. Bottom most node is called as leaf node or external node. It has no link going down from it. A node having a child node and is below root is called internal node.

**Root** : It is the top most node

**Edges** : It is a link between two node.

**Height of a Tree** : It is the height of the root node or the depth of the deepest node.

**Height of a Node** : It is the number of edges from the node to the last leaf (deepest node) of the tree.

**Depth of a Node** : It is the number of edges from the root to the node.

**Degree** : It is the total number of branches of that node.

**Forest** : It is the collection of disjoint trees.

## Types of Trees

### Binary Tree

A binary tree is a tree data structure in which **each parent node can have at most two children**. Each node of a binary tree consists of three items:

- data item
- address of left child
- address of right child

#### Types of Binary Tree

**Full Binary Tree**

A full Binary tree is a special type of binary tree in which every parent node/internal node has either two or no children.
![Full Binary Tree](images/full-binary-tree_0.webp)

**Perfect Binary Tree**

A perfect binary tree is a type of binary tree in which every internal node has exactly two child nodes and all the leaf nodes are at the same level.
![Perfect Binary Tree](images/perfect-binary-tree_0.webp)

**Complete Binary Tree**

A complete binary tree is just like a full binary tree, but with two major differences

- Every level must be completely filled
- All the leaf elements must lean towards the left.
- The last leaf element might not have a right sibling i.e. a complete binary tree doesn't have to be a full binary tree.
  ![Complete Binary Tree](images/complete-binary-tree_0.webp)

### Binary Search Tree (BST)

Binary search tree is a data structure that quickly allows us to maintain a sorted list of numbers.
It is called a binary tree because each tree node has a maximum of two children.
It is called a search tree because it can be used to search for the presence of a number in O(log(n)) time.

The properties that separate a binary search tree from a regular binary tree is

- All nodes of left subtree are less than the root node
- All nodes of right subtree are more than the root node
- Both subtrees of each node are also BSTs i.e. they have the above two properties
  bst-vs-not-bst
  ![Binary Search Tree](images/bst-vs-not-bst.webp)

## Tree Traversal

Traversing a tree means visiting every node in the tree. You might, for instance, want to add all the values in the tree or find the largest one. For all these operations, you will need to visit each node of the tree.

### Depth-first search (DFS) algorithm

It starts with the root node and first visits all nodes of one branch as deep as possible before backtracking. It visits all other branches in a similar fashion.

> InOrder Traversal, PreOrder Traversal, PostOrder Traversal

### Breadth-first search (BFS) algorithm

This also starts from the root node and visits all nodes of current depth before moving to the next depth in the tree.

> LevelOrder Traversal

### Inorder Traversal

- Visit all the nodes in the left subtree
- Then the root node
- Visit all the nodes in the right subtree

> Inorder traversal of a binary search tree will always give you nodes in a sorted manner.

```js
def in_order_traversal(root):
    if not root:
        return
    in_order_traversal(root.left)
    print(root.val, end=" ")
    in_order_traversal(root.right)

```

![InOrder Traversal](images/inorder-traversal.gif)

### PreOrder Traversal

- First the root node
- Visit all the nodes in the left subtree
- Visit all the nodes in the right subtree

```js
def pre_order_traversal(root):
    if not root:
        return

    print(root.val, end=" ")
    pre_order_traversal(root.left)
    pre_order_traversal(root.right)

```

![Preorder Traversal](images/preorder-traversal.gif)

### PostOrder Traversal

- Visit all the nodes in the left subtree
- Visit all the nodes in the right subtree
- Then the root node

```js
def post_order_traversal(root):
    if not root:
        return
    post_order_traversal(root.left)
    post_order_traversal(root.right)
    print(root.val, end=" ")

```

![Postorder Traversal](images/postorder-traversal.gif)

### Level Order Traversal

It will visit all the nodes present at the same level one-by-one from left to right, and then it moves to the next level to visit all the nodes of that level.

![Level order Traversal](images/levelorder-traversal.gif)
