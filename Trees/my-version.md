---
title: Trees
category: Data Structures
description:
    A two-child tree that can be searched by moving left or right.
authors:
    - Tamara Nelson-Fromm, Wenjie Zhu, Nathan Walters, Drshika Asher
---
# Trees
Trees are a hierarchical data structure with a certain set of properties that distinguish it from graphs. Trees are rooted, which means that there is a pointer to the root node and each child node can be reached via the root. 

<!-- not sure how much detail we want here -->
## Basic tree terminology 
(adapted from CS 173)
- Vertex: “nodes”
- Path: sequence of edges
- Parents: Node **b, d, x** have Node **a** as their parent
- Children: **b, d, x,** are the children of **a**
- Siblings: **b, d, x,** are siblings of each other
- Ancestors: **u** has ancestors **l, d, a**
- Descendants: **x** has **s, m** as its descendants
- Leaves: Vertices with no children

## Tree Property: Height
- **Computation of the tree height**
    - The length of the longest path from the root to the leaf (count edges).
    - If we want to compute recursively:
    
    height(T) = 1 + max(height(TL), height(TR)), where if height(null) = -1, which might be counter-intuitive but it follows the mathematical definition of tree height

## Tree Property: Binary
- A binary tree is either
    - T = {TL, TR, r}, where TL, TR are binary trees
    - T = {} = ∅
    
## Tree Property: Full
- A binary tree is full *if and only if*
    - Either: F = {}
    - Or: F = {TL, TR, r} where TL, TR both have either 0 or 2 children
- **Theorem**: A binary tree with n data items has n+1 null pointers.

![Screen Shot 2021-09-30 at 1.08.00 AM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/89a7d6f2-917d-4446-bd9b-d05a6a479297/Screen_Shot_2021-09-30_at_1.08.00_AM.png)
            
## Tree Property: Perfect
- A perfect tree Ph is defined by its height
    - Ph is a tree of height **h**, with
        - P-1 = {}
        - Ph = {r, Ph-1, Ph-1} when h>=0

![Screen Shot 2021-09-30 at 1.09.07 AM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/344640dc-675b-490c-8080-40b9f852b6f9/Screen_Shot_2021-09-30_at_1.09.07_AM.png)
        
## Tree Property: Complete 
(as defined in data structures)
- A complete tree is
    - A perfect tree except for the last level
    - All leaves must be pushed to the **left**
    - Or, recursively, a complete tree **Ch** of height **h** is
        - C-1 = {}
        - Ch = {r, TL, TR} where
            - Either: TL = Ch-1 and TR = Ph-2
        
        Or:      TL = Ph-1   and   TR = Ch-1
        
        ![Screen Shot 2021-09-30 at 1.09.58 AM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e9786ac3-5632-4b1c-ba9c-baee897714e4/Screen_Shot_2021-09-30_at_1.09.58_AM.png)

<!-- make a diagram to explain this -->
- Full does not imply perfect, so as complete does not imply perfect
- Not full implies not perfect, thus perfect implies full; perfect also implies complete too.

## Tree Traversals
<!--add some description about traversals here instead of bullet points-->
(practice them here: [https://yongdanielliang.github.io/animation/web/BST.html](https://yongdanielliang.github.io/animation/web/BST.html))
- Pre-Order: process the data first, then left child, then the right child
- In-Order: left child, process the data, right child
- Post-Order: left child, right child, process the data last
    
```c++
void BinaryTree<T>::preOrder(TreeNode * cur) {
    if (cur != NULL) {
        func(curr->data);
        preOrder(curr->left);
        preOrder(curr->right);
    }
}

void BinaryTree<T>::inOrder(TreeNode * cur) {
    if (cur != NULL) {
        preOrder(curr->left);
        func(curr->data);
        preOrder(curr->right);
    }
}

void BinaryTree<T>::inOrder(TreeNode * cur) {
    if (cur != NULL) {
        preOrder(curr->left);
        preOrder(curr->right);
        func(curr->data);
    }
}
```

## Searching Trees
<!-- add better descriptions here -->
- BFS: breadth first search: visits nodes at each level (level-order traversal): use a queue
    
    ![Screen Shot 2021-10-19 at 6.27.07 PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/99136597-0789-4fe2-a7ef-d32956672b28/Screen_Shot_2021-10-19_at_6.27.07_PM.png)
    
- DFS: depth first search: find the endpoint of the path quickly (in order, pre order or post order): use a stack
    
    ![Screen Shot 2021-10-19 at 6.27.28 PM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c01e1c6d-e7b8-420d-be08-d10c0ffa1ce4/Screen_Shot_2021-10-19_at_6.27.28_PM.png)

- Traversal vs Search: traverse visits every node vs search visits nodes until you find what you want

## Delete and Insert
<!--stopped here-->