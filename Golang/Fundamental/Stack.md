In Go, a stack is a data structure that follows the Last In, First Out (LIFO) principle. This means that the last element added to the stack is the first one to be removed. Think of it like a stack of plates where you can only take or add a plate from/to the top.

```
package main

import "fmt"

// Stack represents a stack data structure
type Stack struct {
    items []int
}

// Push adds an element to the top of the stack
func (s *Stack) Push(item int) {
    s.items = append(s.items, item)
}

// Pop removes and returns the element from the top of the stack
func (s *Stack) Pop() int {
    if len(s.items) == 0 {
        fmt.Println("Error: Stack is empty")
        return 0
    }
    item := s.items[len(s.items)-1]
    s.items = s.items[:len(s.items)-1]
    return item
}

// Peek returns the element from the top of the stack without removing it
func (s *Stack) Peek() int {
    if len(s.items) == 0 {
        fmt.Println("Error: Stack is empty")
        return 0
    }
    return s.items[len(s.items)-1]
}

// IsEmpty returns true if the stack is empty
func (s *Stack) IsEmpty() bool {
    return len(s.items) == 0
}

// Size returns the number of elements in the stack
func (s *Stack) Size() int {
    return len(s.items)
}

func main() {
    // Creating a stack
    stack := Stack{}

    // Pushing elements onto the stack
    stack.Push(1)
    stack.Push(2)
    stack.Push(3)

    // Peeking at the top element
    fmt.Println("Top element:", stack.Peek())

    // Popping elements from the stack
    fmt.Println("Popped element:", stack.Pop())
    fmt.Println("Popped element:", stack.Pop())

    // Checking if the stack is empty
    fmt.Println("Is the stack empty?", stack.IsEmpty())

    // Getting

```

In this example:

- `Stack` is a struct representing the stack. It has a slice (`items`) to store the elements.
- `Push` adds an element to the top of the stack.
- `Pop` removes and returns the element from the top of the stack.
- `Peek` returns the element from the top of the stack without removing it.
- `IsEmpty` checks if the stack is empty.
- `Size` returns the number of elements in the stack.

The `main` function demonstrates creating a stack, pushing elements onto it, peeking at the top element, popping elements, checking if the stack is empty, and getting the size of the stack.

Stacks are commonly used in various applications, including parsing expressions, maintaining function call information in programming languages, and implementing algorithms like depth-first search in graphs.