# Coding semantics
___
*Things to try out and adopt*

> [!info] Naming Constants and Variables
> If you need to give a constant or variable the same name as a reserved Swift keyword, surround the keyword with backticks (\`) when using it as a name. However, avoid using keywords as names unless you have absolutely no choice.

> [!info] Floating-Point Numbers
> `Double` has a precision of at least 15 decimal digits, whereas the precision of `Float` can be as little as 6 decimal digits. The appropriate floating-point type to use depends on the nature and range of values you need to work with in your code. In situations where either type would be appropriate, `Double` is preferred.
## Niche Use cases
___
1. [Integers](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/thebasics/#Integers)
	- `.min`/`.max` properties
	- 32 vs 64-bit platforms
	- Unsigned integers
	- Double is preferred over float
2. [Numeric Literals](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/thebasics/#Numeric-Literals)
	- Binary `0b`
	- Octal `0o`
	- Hexadecimal `0x`
	- Decimal exponent `1.25e2`
	- Hexadecimal exponent `0xFp2`
	- 