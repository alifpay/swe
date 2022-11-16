# questions
Golang questions

- How many bytes of memory does a single precision float32 use?
- Is it possible to change a specific character in a string?
- What is the output of the below code?
```Go
var n uint8 = 255
n += 1
fmt.Println(n)
```
- Explain the code below
```Go
str:="dushanbe"
str[0] = 'D' 
```

- What is the output of the below code?
```Go
sum := 0
for {
  sum++ 
}
fmt.Println(sum) 
```

- What does the built-in len function do when passed a string?
- What is a := "10" - 1 in Go?

- What do you understand by byte and rune data types? How are they represented?
- What are the three uses of "..." in Go?  
- What's the difference between a type definition and a type alias?  
- What does the keyword "make" do?  

- What is the output of the below code?

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
- What is slice? Explain array and slice types and the differences between them.  
- What is the value of slice1 of the below code?  
```Go
nums := [6]int{2, 3, 5, 7, 11, 13}
slice1 := nums[1:4]
```
- What mistakes can be avoided by using the range keyword to iterate over an array?

- What is the output of the below code?
```Go
arr1 := [2]int{2,3}
arr2 := [...]int{2,3}
fmt.Println(arr1==arr2)
```

- Explain the code below
```Go
r := [...]int{99: -1}
```

- What is the output of the below code?
```Go
s := []int{5, 6, 7, 8, 9}
s[3] = s[len(s)-1]
s = s[:len(s)-1]
fmt.Println(s)
 ```
 
 - What is the output of the below code?
 ```Go
s := []int{1, 2, 3}
func(l []int) {
   l[0] = 42
}(s)
fmt.Println(s[0]) 
```

- What is CGo in Golang?

- Explain the Golang map type and its advantages.
- What is the zero value for a map type?

- Explain the defer statement in Golang. Give an example of a deferred function’s call.
- In what order are multiple defer statements called?

- Review the code below
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

- Explain struct in Go (exported, embedding and anonymous fields)

- What does "Arguments are passed by value" mean in functions?  
a) if arguments are pointer, slice, map, function, or channel?  
b) explain about function return

- Explain the code below?
```Go
var f func(int) int
f(3)
```

- What is the Anonymous Functions in Go ?

- What is the output of the below code?
```Go
func sum(vals ...int) int {
    total := 0
    for _, val := range vals {
        total += val
    }
    return total
}
func main(){
  fmt.Println(sum())
}
```
- Explain the Panic and Recover in Go.

- What is the method and method’s receiver in Go?
- What is difference between pointer and value receiver in methods?

- What is an interface? 
- What is the empty interface and type Assertion?

- What is the channel? 
- What operations are available on the channel type?
- What's the difference between unbuffered and buffered channels? 

What does the following code print?
```Go
c := make(chan int, 1)
for done := false; !done; {
  select {
  default:
    fmt.Print(1)
    done = true
  case <-c:
    fmt.Print(2)
    c = nil
  case c <- 1:
    fmt.Print(3)
  }
}
```


- What happens if you send or receive on a nil channel?
- What value do you see when you read from a closed channel?
- How do you check whether a channel has been closed?

```Go
r := <-c
```
- What is a goroutine? what is difference between thread?
- What would you use in Go if you wanted to do more than one thing at the same time?
- What keyword is used to start a new independently running task?
- What order do different goroutines run in?
- Deadlocks and race conditions?

- What is the Reflection (reflect) in Go ?

- What is the unsafe package in Go ?
