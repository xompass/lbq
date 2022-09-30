# Introduction 
This project parses a [loopback 3](https://loopback.io/doc/en/lb3/Querying-data.html) like filter.

# Usage
```go
package main

import "github.com/xompass/lbq"

func main() {
	filter, err:= lbq.ParseFilter("<your loopback filter>")
	
	//...
}

```

## Example

### Fields
```go
var filter = lbq.Filter {
	Fields: lbq.Fields{
		"field1": true,
		"field2": true,
		"field3": false,
	},
}
```

### Limit and Skip
```go
var filter = lbq.Filter {
	Limit: 10,
	Skip: 5,
}
```

### Order
```go
var filter = lbq.Filter {
	Order: []lbq.Order{
		{
			Field: "field1",
			Direction: "ASC",
		},
		{
			Field: "field2",
			Direction: "DESC",
		},
	},
}
```

### Where
```go
var filter = lbq.Filter {
	Where: lbq.Where{
	"field1": "value1",
	"field2": lbq.Where {
		"gt": 10,
	},
	"and": []lbq.AndOrCondition{
			{ "field3": "value3" },
			{ "field4": true },
		},
	},
}
```

### Include
```go
var filter = lbq.Filter {
	Include: []lbq.Include{
		{
			Relation: "relation1",
			Scope: &lbq.Filter{
				Fields: lbq.Fields{
					"field1": true,
					"field2": true,
				},
			},
		},
		{
			Relation: "relation2",
			Scope: lbq.Filter{
				Fields: lbq.Where{
					"field3": "value3",
				},
			},
		},
		{
			Relation: "relation3",
		},
	},
}
```