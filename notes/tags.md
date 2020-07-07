7/7/20======================

The current idea for tagged blocks is that we can annotate what would otherwise be [future] comment syntax with tags that can be handled by the compiler.

For example, comment syntax:

```
#: this is a line comment

#"
	this
		is
		  a
		   multiline
		   			comment
#"
```

Tag syntax:

```
#foo: this line is the content of the "foo" tagged block

#bar{
	these lines are the
	content of the "bar"
	tagged block
#bar}
```

Multiline tagged blocks could use any of the following paren-likes:
```
()
[]
{}
<>
""
''
```

I'm not sure which of these should be allowed and which ones shouldn't. I'm also not sure if they should have specific functions for each paren-like, or if their specific function should be left entirely up to the programmer.



Because Bzo's syntax is perhaps not friendly to complex math, we could use this to create a "math" DSL.

```
#math{
	~x = even(~x)? x / 2 : (3 * x) + 1;
#math}
```

Current thinking for the math DSL is:
* automatically pulls identifiers from local scope, saves results to local scope
* implicit typing (optional annotations)
* optional precision annotations
* arithmetic, ordering, bitwise, if/else, array stuff, trig, exp. maybe simple loops like map, sum, avg, etc.

```
#: this generates an inverse square root function, but tells the superoptimizer
#: that it only needs 2 digits of precision on all variables with a _n suffix
#math{
	@fast n : 2 most sig digits
	q_n = 1 / sqrt(x)
#math}
```