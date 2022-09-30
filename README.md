# Introduction 
This project parses a [loopback 3](https://loopback.io/doc/en/lb3/Querying-data.html) like filter.

# Usage
```go
package main

import "github.com/xompass/lbq"

func main() {
	filter, err:= lbq.ParseFilter("{\"where\": {\"name\": \"some_name\"}}")
	
	//...
}

```