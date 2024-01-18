<p align='center'>
    <img src='https://media-exp1.licdn.com/dms/image/C511BAQG_UWHeDkmt9A/company-background_10000/0/1586588533445?e=2147483647&v=beta&t=VN26LwWLjk9jVef_1W4_24nlY5bWbqg_Yl5vQIg9BYM'>
</p>

## Installation:
```
go get github.com/Terminal1337/GoCycle
```

## Usage:
```go
package main

import (
	"time"
	"github.com/Terminal1337/GoCycle"
)

func main() {
	cycle, err := GoCycle.NewFromFile("proxies.txt") // Load from list: GoCycle.New(List *[]string)

	if err != nil {
		panic("Can't open proxy file")
	}

	// Remove all duplicate items
	cycle.ClearDuplicates()

	// Lock the element "a" while 5 seconds
	go cycle.LockByTimeout("a", 5*time.Second)

	// Lock element
	cycle.Lock("a")

	// Unlock element
	cycle.Unlock("a")

	// Check if element is locked
	cycle.IsLocked("a")

	// Check if element is in list
	cycle.IsInList("a")

	// Get the next element from the list
	cycle.Next()

	// Remove element from cycle
	cycle.Remove("a")

        // Combine Cycles
        cycle.CombineCycles(cycle1,cycle2,cycle33)
}

```

I didn't make this you fuck
