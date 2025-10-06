#### Binary Operations & Closure
- Binary operations on a set is a rule that combines two elements of the set to produce another element of said set.
- For example, assume S = {0,1} 
	- Multiplication on this set would be a binary operation
		- AKA all ways you could multiply the elements of the set , including with themseles, you end up with an element within the set
	- Addition on this set would not be a binary operation
		- AKA there is at least one way in which you could add elements of this set, including with themselves (1+1) in which you end up with an element not within the set (2)

- If N is a set, assume natural numbers and Z is a set, assume integers. We can do Z+ for all positive integers. From this, N+ = Z+
	- N = {0,1,2,3,...}
	- Z = {..., -1, 0, 1, ...}
	- Z+ = {0,1,...}

- If a binary operation on set S is not defined on all pairs of elements within S - we refer to it as partial binary operations. 
- We say set S is CLOSED under the  binary operation * if, whenever both a and b are elements of S, the result of a\*b is also within S
	- If it is not closed, it may be a partial binary operation

#### Associativity
- Assume we have x,y,z. All of which are elements of set S.
- We say operations * is associative if, for all x,y,z in S it is the case that:
	- (x\*y) \* z = x \* (y\*z)
- A semigroup is a pair (S,\*) where S is a set and \* is a associative binary operation on S. 
- E.G: 
	- (N, +), (Z, +), (N, x), (Z, x) are all semigroups
