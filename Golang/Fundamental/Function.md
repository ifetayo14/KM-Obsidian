# Variadic Function
The three dots (**…**) in Golang is termed as Ellipsis in Golang which is used in the [variadic function](https://www.geeksforgeeks.org/variadic-functions-in-go/) The function that called with the varying number of arguments is known as variadic function. Or in other words, a user is allowed to pass zero or more arguments in the variadic function.

Example:
```
package main

import "fmt"

func main() {
	sayHello()
	sayHello("Rahul")
	sayHello("Mohit", "Rahul", "Rohit", "Johny")
}

// using Ellipsis
func sayHello(names ...string) {
	for _, n := range names {
		fmt.Printf("Hello %s\n", n)
	}
}
```

Output:
```
Hello Rahul
Hello Mohit
Hello Rahul
Hello Rohit
Hello Johny
```
