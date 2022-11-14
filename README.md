# questions
Golang questions

1. What do you understand by byte and rune data types? How are they represented?
2. What is a goroutine? what is difference between thread?
3. Deadlocks and race conditions?
4. What is an interface?  
 - What is the empty interface?

What are the three uses of "..." in Go?  
What's the difference between a type definition and a type alias?  
What does the keyword "make" do?  

What is the output of the below code?

```Go
package main  

import "fmt"  

type Aa uint

const (
	x    Aa = 1 << iota 
	y                      
	z                                    
)
func main() {  
 fmt.Println(x, y, z)  
}
```
4. What is slice? Explain array and slice types and the differences between them.  
5. What is the value of slice1 of the below code?  
```Go
nums := [6]int{2, 3, 5, 7, 11, 13}
slice1 := nums[1:4]
```

6. Is it possible to change a specific character in a string?

7. What is the output of the below code?
```Go
arr1 := [2]int{2,3}
arr2 := [...]int{2,3}
fmt.Println(arr1==arr2)
```

Explain bellow code
```Go
r := [...]int{99: -1}
```

what is the output?
```Go
s := []int{5, 6, 7, 8, 9}
s[3] = s[len(s)-1]
s = s[:len(s)-1]
fmt.Println(s)
 ```

8. What is the channel? 
- What operations are available on the channel type?
- What's the difference between unbuffered and buffered channels? 

9. What is CGo in Golang?

10. Explain the Golang map type and its advantages.
- What is the zero value for a map type?

11. Explain the defer statement in Golang. Give an example of a deferred function’s call.
 - In what order are multiple defer statements called?

Review below code
```Go

func main() {
  count := 5
  if count > 5 {
    message := "Greater than 5"
  } else {
    message := "Not greater than 5"
  }
  fmt.Println(message)
}
```

Explain struct in Go


what is the Reflection (reflect) in Go ?

what is the unsafe package in Go ?
