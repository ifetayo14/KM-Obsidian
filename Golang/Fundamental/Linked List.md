In Go, a linked list is a data structure that consists of a sequence of elements, where each element points to the next one in the sequence. Each element is called a node, and a linked list is formed by connecting these nodes.

```
package main

import "fmt"

// Node represents a node in a singly linked list
type Node struct {
    Data int
    Next *Node
}

// LinkedList represents a singly linked list
type LinkedList struct {
    Head *Node
}

// Append adds a new node with the given data to the end of the linked list
func (list *LinkedList) Append(data int) {
    newNode := &Node{Data: data, Next: nil}
    if list.Head == nil {
        list.Head = newNode
        return
    }
    lastNode := list.Head
    for lastNode.Next != nil {
        lastNode = lastNode.Next
    }
    lastNode.Next = newNode
}

// Print prints the elements of the linked list
func (list *LinkedList) Print() {
    current := list.Head
    for current != nil {
        fmt.Print(current.Data, " ")
        current = current.Next
    }
    fmt.Println()
}

func main() {
    // Creating a linked list and adding elements
    linkedList := LinkedList{}
    linkedList.Append(1)
    linkedList.Append(2)
    linkedList.Append(3)

    // Printing the linked list
    linkedList.Print()
}

```

In this example:

- `Node` is a struct representing a node in the linked list. Each node contains an integer value (`Data`) and a reference to the next node (`Next`).
- `LinkedList` is a struct representing the linked list itself. It contains a reference to the head node (`Head`), which is the starting point of the list.
- The `Append` method adds a new node with the given data to the end of the linked list.
- The `Print` method prints the elements of the linked list.

The `main` function demonstrates creating a linked list and adding elements (1, 2, and 3) to it. The final linked list is then printed.

In this example, we used a singly linked list, where each node points to the next node. There are also doubly linked lists where each node points to both the next and the previous node, and circular linked lists where the last node points back to the first node.

Linked lists are useful when you need a dynamic data structure with efficient insertions and deletions, and you don't need random access to elements. They provide flexibility in memory allocation and can be easily resized.