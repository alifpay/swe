The Liskov Substitution Principle states that a derived class should be substitutable for 
its base class. In other words, if a program is using a base class, it should be able to use a derived 
class without knowing it. In Go, this can be achieved by defining clear contracts between types using interfaces, 
and ensuring that derived types fulfill those contracts.

```Go
type ImmutableCollection interface {
   Get(index int) interface{}
}

type MutableCollection interface {
   ImmutableCollection
   Add(item interface{})
}

type ReadOnlyCollectionV2 struct {
   items []interface{}
}

func (ro *ReadOnlyCollectionV2) Get(index int) interface{} {
   return ro.items[index]
}

type CollectionImplV2 struct {
   ReadOnlyCollectionV2
}

func (c *CollectionImplV2) Add(item interface{}) {
   c.items = append(c.items, item)
}

```

https://medium.com/backticks-tildes/the-s-o-l-i-d-principles-in-pictures-b34ce2f1e898
