#java #java_static-methods
[Official Documentation](https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html)
___
# General
- **Static** methods can be called by appending the method to the class (E.g. `Class.method`)
	-> **Non-static** methods require an object of the class to be created before calling a method
___
# Methods
- `int abs(int x)`: Returns *absolute value*, which states how many numbers a value is away from `0`
	- `double abs(double x)`: ... returns double type value
___
- `double pow(double base, double exponent)`: Returns value of first parameter raised to power of second parameter
___
- `double sqrt(double x)`: Returns positive square root of double value
___
- `double random()`: Returns double value $\ge 0.0$ and $\lt 1.0$
**Predefine range**:
```java
// Random double value between 0 and 10(exclusive)
double a = Math.random() * 10;
```
```java
// Random int value between 0 and 10(exclusive)
int b = (int)(Math.random() * 10);
```
```java
// Random int value between 1 and 10
int c = (int)(Math.random() * 10) + 1;
```
```java
// Random int value between 10 and 20
int d = (int)(Math.random() * 11 ) + 10;
```
> We multiply `Math.random()` by 11 because 20 (our max value) minus 10 (our minimum value) plus 1 is 11. We add + 10 outside the parentheses so that our smallest value is guaranteed to be 10.
> `(Math.random() * (maxValue - minValue + 1)) + minValue`
