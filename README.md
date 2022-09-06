# Introduction 
This project parses a [loopback 3](https://loopback.io/doc/en/lb3/Querying-data.html) like filter.

# Usage
```go
package main

import "dev.azure.com/xompass/xompass-cloud/_git/lbq"

func main() {
	filter, err:= lbq.ParseFilter("{\"where\": {\"name\": \"some_name\"}}")
	
	//...
}

```