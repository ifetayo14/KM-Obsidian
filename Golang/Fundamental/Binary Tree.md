In Go, a binary tree is a data structure in which each node has at most two children, referred to as the left child and the right child. Each node in a binary tree contains a value and references to its left and right children (subtrees). The topmost node in the tree is called the root.

```
package main

import "fmt"

// TreeNode represents a node in a binary tree
type TreeNode struct {
    Val   int
    Left  *TreeNode
    Right *TreeNode
}

func main() {
    // Example of creating a binary tree
    root := &TreeNode{Val: 1}
    root.Left = &TreeNode{Val: 2}
    root.Right = &TreeNode{Val: 3}
    root.Left.Left = &TreeNode{Val: 4}
    root.Left.Right = &TreeNode{Val: 5}

    // Traverse the binary tree (e.g., inorder traversal)
    fmt.Println("Inorder traversal:")
    inorderTraversal(root)
}

// Inorder traversal of a binary tree
func inorderTraversal(node *TreeNode) {
    if node != nil {
        // Traverse the left subtree
        inorderTraversal(node.Left)

        // Process the current node
        fmt.Print(node.Val, " ")

        // Traverse the right subtree
        inorderTraversal(node.Right)
    }
}

```

In this example:

- `TreeNode` is a struct representing a node in the binary tree. It contains an integer value (`Val`) and references to its left and right children (`Left` and `Right`).
- The `main` function demonstrates creating a binary tree with a root node and a few child nodes.
- The `inorderTraversal` function performs an inorder traversal of the binary tree, printing the values of the nodes in ascending order.

Binary trees can be used for various purposes, including:

1. **Binary Search Trees (BST):** When the values of nodes in the binary tree are organized such that the left child is less than the parent, and the right child is greater than the parent, it becomes a Binary Search Tree. This allows for efficient searching, insertion, and deletion operations.
    
2. **Expression Trees:** Binary trees can be used to represent mathematical expressions, with operators as internal nodes and operands as leaf nodes.
    
3. **Heap Data Structure:** Binary trees are used to implement priority queues and heaps.
    
4. **Traversal Algorithms:** In addition to inorder traversal, binary trees can be traversed in pre-order and post-order as well, each providing a different sequence of processing nodes.
    

These are just a few examples of how binary trees can be used in programming. The choice of application depends on the problem you are trying to solve.