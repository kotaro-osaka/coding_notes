> [!info]+ Info
> - Java is a compiled programming language
> 	- Compiling identifies mistakes in code
> 	- Compilers transform code into executable class
> - Integrated Developing Environment (IDE)
> 	- Editing source code, building executables & debugging
> 	- Syntax highlighting & Autocomplete
> 	- Helps with compiling & executing
> 	- Debugging assistant & Hints while coding to prevent errors before compilation
> - Java is a case-sensitive language
> 	- Syntax must match case, otherwise compiler cannot identify intention correctly
>```java
>// ✔
>System.out.println();
>// ❌
>system.Out.Println();
>```
> - [Java Datatypes](https://www.codecademy.com/resources/docs/java/data-types?page_ref=catalog)
> - Code written in `.java` file is transformed into byte code by compiler
> 	- Executed by Java Virtual Machine(JVM) on computer after
> 	![[Java M1L1- Compilation Process A.png]]
> - `.java` file - Java Syntax
> - `.class` file - Compiled file with Java bytecode (executable by JVM)
> - Java programs have at least one `class` and `main()` method
> 	- `main()` - Runs tasks of the problem
> - Class name **must** match file name
> - Method is a sequence of tasks for computer to execute
> 	- `main()` - Contains all instructions for computer to execute // program
> - *Pascal Case* is used for Classes
>![Pascal Case | 400x120](pascal-case.png)
> - *Camel Case* is used for variables and methods
>![Camel Case | 400x115](camel-case.png)
> - Objects are packages of state and behavior
> - Variables are named memory locations
> - Constructors - Methods in class, used to initialize object of class
> 	- Every time `new` keyword is used to create an object the constructor is called
> 	- Sets initial state of instance
> 	- Always have same name as their class
> 	- Cannot be `abstract`/`static`/`final`/`synchronized`
> 	- No explicit return type
> 	- Default: No parameters
> - *Instance Variable/Fields* - Add data to an object
> 	- "has-a" relationship with object
> 	- Declaration is within the class
> 	- Instance variable is available for assignment in constructor
> 	- Type of state each instance possesses
> - Constructor Parameters - Used to assign a value to an instance variable
>```java
>public ConstructorName(datatype variableName) {
>	instanceVariable = variableName;
>}
>```
> - If constructor is not defined, compiler generates default constructor
> 	- Contains no args
> 	- Assigns object default values
> - Default Values - Assign values to instance fields on declaration instead of leaving empty
> - *Constructor Overloading* - Class can have multiple constructors
> 	- **⚠**Only as long as they have different parameter values
> 	- Appropriate constructor is called based on arguments provided on instantiation
> - *Formal Parameter* - Parameter
> - *Actual Parameter* - Argument
> - *Signature* - Method name and parameter list
> - Accessing a field
>```java
>objectName.fieldName;
>```
>```java
>public void myMethod(int x, String y)
>// Signature
>myMethod(int, String)
>```
> - *Reference Data Type* - Value of variable is reference to an instance's memory address
> - *Dot Notation* - Used to access parts of an object
>```java
>// Access object1
>Object.object.object1
>```
> - Non-static method - Available to use on an object of class
> 	- Create object to call method on it
> 	- Can only access variables in method's scope and field variables
>```java
>Car Ferrari = new Car();
>Ferrari.exampleMethod();
>```
> - *Static Typing* - Variable must contain value of correct type
> 	- Incorrect type leads to *declaration bug*
> - *Statements* - Perform single task
> - *Whitespaces* - `tabs, spaces, newlines`
> 	- Increase readability for humans
> - `{ }` - Mark scope of class or method
> - `;` - Mark end of statement
> - `//` - Compiler ignores everything after, to the end of the line
>
>> [!example]+ Terminal // Command Line
>> - Compile `.java` file:
>>```
>>javac fileName.java
>>```
>> - Successful compilation produces `.class` file
>> - Execute `.class` file:
>>```
>>java className
>>```
>> - Unsuccessful compilation produces list of errors and doesn't create `.class` file
>> - `ls` - List all available files
>
>> [!example]+ Syntax
>> - Print // Output text to screen
>> 	- Prints to terminal as output
>> 	- `print()` / `println()` - Methods
>> 	- `out` - Object, responsable for various types of output
>> 	- `System` - Object, responsable for representing computer within program
>>```java
>>// Print without ↵
>>System.out.print();
>>
>>// Print with ↵
>>System.out.println();
>>```
>> - Class definition
>>```java
>>public class ClassName {
>>	// class code
>>}
>>```
>> - Method definition
>>```java
>>public static void main(String[] args) {
>>	// Statements
>>}
>>```
>> - Create Instance
>>```java
>>ClassName instanceName = new ClassName();
>>
>>System.out.println(instanceName); // Returns memory location
>>```
>>
>>**Methods**
>> - `.equals()` - Used to compare objects
>>```java
>>object1.equals(object2);
>>```
>> - `toString()` - Used to return String when object is printed (=memory address)
>>```java
>>public String toString() {
>>	return "Text to be returned instead of memory address of object";
>>}
>>```
>>
>>**Keywords**
>> - `final` - Used to make variable unchangeable
>> - `new` - Used to indicate creation of instance
>> - `return` - Used to return a value *of the type declared in method signature's return type*
>> 	- Method exits after *return*
>> 	- Can return Object, but must be declared as field variable with type car and method's return type must be modified to object - **Returns reference to object's memory address**
>>```java
>>class ExampleClass {
>>ObjectAsDatatype variableName; // Field Variable
>>
>>public ObjectAsDatatype methodName() {
>>	return variableName; // Return Object assigned to `variableName`
>>	// Output example: Obj@2f333739
>>	}
>>}
>>```
>> - When returning an array, reference to array's memory address is returned
>>```
>>// Example
>>`[Ljava.lang.String;@2aae9190`
>>```
>> - `break` - Exit loop before all iterations are finished
>> - `continue` - Skip iteration
>>```java
>>// Example
>>int[] numbers = {1, 2, 3, 4, 5};
>>
>>for (int i = 0; i < numbers.length; i++) {
>>	if (numbers[i] % 2 == 0) {
>>		continue;
>>	}
>>	System.out.println(numbers[i]);
>>}
>>```
>> - `public`/`private` - Grant/Revoke access
>> - `this` - Used to refer to current object and placeholder for object to call methods on
>
>> [!example]+ ArrayList - Resizable array
>>  - Store object references as elements
>>  - Store elements of the same type (just like arrays)
>>  - Access elements by index (just like arrays)
>>  - Add elements
>>  - Remove elements
>>
>> - `import java.util.ArrayList;`: Import ArrayList methods from Java's util package
>> - `ArrayList<dataType> name;`: Declaring
>> - `name = new ArrayList<dataType>();`: Initializing
>> - `ArrayList<dataType> name = new ArrayList<dataType>();`: Declaring & Initializing
>> - `.add()` Method: Insert element into structure
>> 	- `arrayListName.add(element);`: Add element to end of list
>> 	- `arrayListName.add(index, element);`: Add element to specific index location
>> - `dataType` can be empty to hold elements of different data types 
>> - `.size()` Method: Display number of elements in ArrayList
>> - `.get()` Method: Access index in ArrayList
>> - `.set(index, newValue)` Method: Rewrite value
>> - `.remove(index)` Method: Remove element by index **or** value
>> - `.indexOf(value)` Method: Get index of value
>
>> [!example]+ Loops
>> - `for-each` - "enhanced loop"
>>```java
>>// Syntax
>>for (dataType enhancedForLoopVar : listToTraverseThrough) {
>>	...
>>}
>>// Read as "For each item of type (datatype) in list, do ..."
>>```
>
>> [!example]+ String Methods
>> - `String` - Class that is part of `java.lang` package , which is integrated by default
>> - `.length()` - Returns number of chars
>> - `.concat()` - Returns combination of original string and provided string
>> - `.equals()` - Returns true if equal, false if not
>> - `.indexOf()` - Returns index of first occurrence of String, `-1` if not found
>> - `.charAt()` - Returns char at specified index
>> - `.substring()` - Returns part of String
>>```java
>>// Syntax
>>substring(int beginIndex, int endIndex)
>>// beginIndex is inclusive
>>// endIndex is exclusive
>>
>>// Example
>>String text = "Hello, World!";
>>String sub1 = text.substring(7);        // sub1 will be "World!"
>>String sub2 = text.substring(0, 5);     // sub2 will be "Hello"
>>```
>> - `.toUpperCase()` - Converts String to upper case
>> - `.toLowerCase()` - Converts String to lower case
