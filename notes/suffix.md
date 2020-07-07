7/7/20======================

Suffixes are extra annotations that can be added to the end of literals.

```
	341u64			#: 341      with suffix u64
	3.7f32      	#: 3.7      with suffix f32
	"[a-z]+"REGEX 	#: "[a-z]+" with suffix REGEX
```

Whenever the compiler finds one of these, it would be passed into a function that corresponds to the suffix and returns either an AST that will replace the literal, or an error that will be returned to the user.

This would be useful for allowing the programmer to create custom literal types for specific things, such as regular expressions. Generating an AST from this would provide custom compile-time checking of the literals, as well as access to the full power of the optimization engine. It would also likely drive human error down substantially in these cases. Hopefully.