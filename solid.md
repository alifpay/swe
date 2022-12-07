Single Responsibility Principle (SRP)

A module, class or function should be responsible to one, and only one stakeholder.

Only one stakeholder has the right to change a module, class, or function.
The best way to understand this principle is by looking at an infamous example of violating it.
```Go
package main

import (
	"fmt"
	"math"
)

type circle struct {
	radius float64
}

func (c circle) area() {
	// violating Single Responsibility Principle
	fmt.Printf("circle area: %f\n", math.Pi*c.radius*c.radius)
}

func main() {
	c := circle{
		radius: 3,
	}
	c.area()
}
```
As we can see, the function area() goes against the single responsibility principle. 
Because it can change for two reasons. First, the calculation of the area could 
change for some reason. Second, the presentation format of output could also change.
It would be a bad design to couple two things that change for different reasons at different times.
The SRP says that two aspects of a problem are two separate responsibilities. 
They should, therefore, be in separate classes or modules.

More Considerations…
Before fixing the above problem, let’s consider some other questions
What if we want to change the presentation without affecting the area calculation?
What if we also want to output another data format like JSON?
What if we add another square shape?
To handle the above questions, the silver bullet is to separate the changeable parts.
Let’s start to do code refactoring!
How to do Refactor?
Now we organize the new source code dependencies to ensure that changes to one of those 
responsibilities do not cause changes in the other.

The Output has two functions: Text and JSON. 
They are two independent presentation formats.
The Output depends on shape interface, which has two methodsname and area
Circle and Square are two implementations of theshape interface
The following code is self-explanatory, I think.


```Go
package main

import (
	"encoding/json"
	"fmt"
	"log"
	"math"
)

type circle struct {
	radius float64
}

func (c circle) area() float64 {
	return math.Pi * c.radius * c.radius
}

func (c circle) name() string {
	return "circle"
}

type square struct {
	length float64
}

func (c square) area() float64 {
	return c.length * c.length
}

func (c square) name() string {
	return "square"
}

type shape interface {
	name() string
	area() float64
}

type output struct{}

func (o output) Text(sh shape) string {
	return fmt.Sprintf("area of shape %s is %f", sh.name(), sh.area())
}

func (o output) JSON(sh shape) string {
	res := struct {
		Name string  `json:"shape"`
		Area float64 `json:"area"`
	}{
		Name: sh.name(),
		Area: sh.area(),
	}
	bs, err := json.Marshal(res)
	if err != nil {
		log.Fatal(err)
	}
	return string(bs)
}

func main() {
	c := circle{
		radius: 3,
	}
	o := output{}
	fmt.Println(o.Text(c))
	fmt.Println(o.JSON(c))

	s := square{
		length: 3,
	}

	fmt.Println(o.Text(s))
	fmt.Println(o.JSON(s))
}

```
