> [!info]- Info
> - **String Concatenation** - Join `strings` together
> - **Shallow Copy** - References elements instead of copying
> - **Zero Indexing** - Start counting from 0
> <br>
> - `var` only for old browsers/codebases
> - use `let` and `const` 
> - print to console with variables:
>```js
>// String Concatenation
>console.log("Hello, my name is" + name + "and I'm" + age + "years old.");
>// String Interpolation
>console.log(`Hello, my name is ${name} and I'm ${age} years old.`);
>```
> - `%` modulo:
>```js
>// Calculate remainder of division
>const remainder = 10 % 3;
>console.log(remainder);
>// Output: 1
>```
>- Check if variable exists:
>```js
>if (myVariable)
>```
> - Falsy value/evaluetes to false:
>```js
>0
>'' or ""
>null
>undefined (declared variable without value)
>NaN (Not a Number)
>```
> - `\n` - *Line break*

> [!example]- Operators
> - `\'` to print `'` without interference
> - `===` equal
> - `!==` not equal
> - `typeof` - Returns operand's value as string
>```js
>// Syntax
>typeof opperand
>
>// Example:
>console.log(typeof 42);
>// Output: "number"
>
>// Possible returns:
>"undefined"
>"object"
>"boolean"
>"number"
>"bigint"
>"string"
>"symbol"
>"function"
>```

> [!example]- Control Flow Statements
> - **Short-Circuit Evaluation**
> 	- If `value1` is falsy, assign `value2` 
>```js
>let myVariable = value1 || 'value2';
>```
> - **Ternary Operator**
> 	- Condition before `?`
> 	- `conditionTrue : conditionFalse` 
>```js
>// Example
>isNightTime ? console.log('Turn on the lights!') : console.log('Turn off the lights!');
>```
> - **Switch Statement**
> 	- `switch`-keyword initiates statement
> 	- `(expression)` is compared with value of each case
> 	- `break` signals program to exit the block
> 	- `default` is executed if cases return false
>```js
>switch (expression) {
>	case value1:
>		command1;
>		break;
>	case value2:
>		command2;
>		break;
>	default:
>		command3;
>		break;
>}
>```

> [!example]- Functions
> - **Helper Functions** - Return function in another function
> - **Function Expression**
> 	- Cannot be called before definition
> 	- Encapsulated function in `const`
> 	![[Pasted image 20230816210611.png]]
> - **Arrow Functions**
> ![[Pasted image 20230816212341.png]]
> ![[Pasted image 20230816212904.png]]
> - **Function as Data** - Functions can be assigned to variables:
>```js
>let functionName = () => {
>	console.log('Message');
>}
>let variableName = functionName;
>variableName; // Call function
>```
>**Function as Parameter** 
>```js
>function executeFunction(func) {
>	console.log("Executing the provided function...");
>	func();
>}
>```
>**Callback Function** - Call function that is passed in as parameter
>```js
>// Higher-order function that takes a function as a parameter
>const higherOrderFunc = callback => {
>	// Call the provided function (callback)
>	callback();,
>};
>
>// Callback function to be passed as a parameter
>const myCallback = () => {
>	console.log("This is the callback function.");
>};
>
>// Using the higher-order function with the callback
>const result = higherOrderFunc(myCallback);
>console.log(result);
>```

> [!example]- Arrays
> - **Nested Array** - Array in another array
>```js
>const nestedArr = [[1], [2], [3]];
>
>console.log(nestedArr[1]); // Output: [2, 3]
>console.log(nestedArr[1][0]); // Output: 2
>```

> [!example] Methods - [List](https://www.codecademy.com/resources/docs/javascript/methods)

> [!example]- Array Methods - [List](https://www.codecademy.com/resources/docs/javascript/arrays#:~:text=the%20provided%20function.-,.find(),-Returns%20the%20first)
> - `.push()` - Add items to end of array
>```js
>const itemTracker = ['item 0', 'item 1', 'item 3'];
>
>itemTracker.push('item 3', 'item 4');
>
>console.log(itemTracker);
>// Output: ['item 0', 'item 1', 'item 2', 'item 3', 'item 4'];
>```
> - `.pop()` - Removes last element of array
> - `.shift()` - Removes first element of array
> - `.unshift()` - Adds elements to beginning of array and returns new length
> - [`.slice()`](https://www.codecademy.com/resources/docs/javascript/arrays/slice) - Returns Shallow Copy of part of array without modifying original array
> - `.indexof()` - Returns first index at which element can be found. Else: Output -1
> - `.join()` - Returns string representation of array elements concentrated teogether
>```js
>array.join(seperator);
>```
> - `.concat()` - Returns merged arrays
> - `.forEach()` - Array Method: Loops over given array and passes each item into provided callback function
>![[Pasted image 20230818113617.png]]
>`.map()` - Creates new array by applying provided function for each element
>```js
>// Syntax
>array.map((element, index, array)) => {...};
>
>// Example
>const numbers = [1, 2, 3, 4, 5];
>
>const doubled = numbers.map((value)) => value * 2);
>
>console.log(doubled);
>
>// Output: [2, 4, 6, 8, 10]
>```
> - `.filter()` - Creates new array with all elements that pass condition from provided function
> 	- `emptyArray[]` - If none pass
>```js
>array.filter(element => {...})
>array.filter((element, index) => {...})
>array.filter((element, index, array) => {...})
>
>// `element`: The current element being processed in the array
>// `index` (optional): The index of the current element being processed in the array.
>// `array` (optional): The array _filter_ was called upon
>```
> - `.findIndex()` - Returns first index that passes callback function's condition
> 	- Return -1 - If none pass
>```js
>array.filter(element => {...})
>array.filter((element, index) => {...})
>array.filter((element, index, array) => {...})
>
>// `element`: The current element being processed in the array
>// `index`: (optional): The index of the current element being processed in the array
>// `array`: (optional): The array _filter_ was called upon
>```
> - `.findIndex()` - Returns first index that passes callback function's condition
> - Return -1 - If none pass
>```js
>array.findIndex((element, index, array) => {...});
>```
> - `.reduce()` - Combines elements of array with reducer function to single value
>```js
>// Syntax
>array.reduce((accumulator, currentValue, index, array) => {...}, initialValue)
>// acc: Result from previous iteration or initialValue
>// curr: Current element being processed in array
>// currIndex: Index of current element
>// array: Original array
>```
> - `.some()` - Returns `bool` for function's condition
>```js
>const array = [1, 2, 3, 4, 5];
>
>// Checks whether an element is even
>const even = (element) => element % 2 === 0;
>
>console.log(array.some(even));
>// Expected output: true
>```

> [!example]- Math Methods - [List](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
> - `Math.random()` - Return random number
>```js
>console.log(Math.random());
>// Output: 0 - 0.9999999999999999
>```
> - `Math.floor()` - Return largest `int` ≤ given number
>```js
>console.log(Math.floor(5.95));
>// Output: 5
>```

> [!example]- Object Methods
> - When data stored on an object is a function: Method
> - Object executes methods
>```js
>// Syntax
>// Declare method
>methodName() {
>	...
>}
>// Call method
>objectName.methodName();
>// Call method as property - returns definition
>objectName.methodName;
>
>// Examples
>console.log();
>Math.floor();
>```
> - `Object.keys()` - Returns array of given object's key
>```js
>const object1 = {
>	a: 'somestring',
>	b: '42',
>	c: false
>};
>
>console.log(Object.keys(object1));
>// Expected output: Array ["a", "b", "c"]
>```
> - `Object.entries()` - Returns array of given object's key-value pairs
>```js
>const object1 = {
>	a: 'somestring',
>	b: 42
>};
>
>for (const [key, value] of Object.entries(object1)) {
>	console.log(`${key}: ${value}`);
>};
>
>// Expected output:
>// "a: somestring"
>// "b: 42"
>```
> - `Object.assign()` - Copies all properties(key-value pairs) from one or more source object to a target object
> - Returns modified target object
> - `target` can be object properties in `{}`
>```js
>// Syntax
>Object.assign(taget, ...sources)
>
>// Example
>const target = {  a: 1, b: 2 };
>const source = { b: 4, c: 5};
>
>const returnedTarget = Object.assign(target, source);
>
>console.log(target);
>// Output: Object { a: 1, b: 4, c: 5 }
>
>console.log(returnedTarget === target);
>// Output: true
>```
> - **Property Conflict/Collision** - Properties with same name from different lists cause the target to be overwritten by the source

> [!example]- Loops
> - `for` loop
>```js
>for (i = 0; i < 100; i++) {
>	console.log(i);
>}
>```
> - `for...in` loop - Iterates over values of properties in object
>```js
>for (var in obj) {
>	statement
>}
>
>// variable: Declare with `let/const` or use predefined - Recieves string property name for each iteration
>// variable assigned to subclass of following object
>// object: Object of properties to be iterated over
>// statement: Statement to be executed on every iteration - Can use block statement
>
>// Example
>let spaceship + {
>	crew: {
>		captain: {
>			name: 'name1'
>		}
>		medic: {
>			name: 'name2'
>		}
>	}
>}
>
>for (let crewMember in spaceship.crew) {
>	console.log(`${crewMember}: ${spaceship.crew[crewMember].name}`);
>}
>// Steps: captain, medic
>// crewMember: captain, medic
>```
> - `while` loop
>```js
>while (i < 5) {
>	console.log(i);
>	i++;
>}
>```
> - `do...while` loop
>```js
>let x = 0;
>let i = 0;
>
>do {
>	x = x + i;
>	console.log(x);
>	i++;
>} while (i < 5);
>```
> - `break` - Signals program to exit the block
>```js
>for (let i = 0; i < 99; i += 1) {
>	if (i > 5) {
>		break;
>	}
>	console.log(i);
>}
>```

> [!example]- Objects
> - Properties `===` Keys
> - Variable with properties
> - Variables and methods must be divided with `,` 
>```js
>let spaceship = {
>	'Fuel Type': 'diesel',
>	color: 'silver'
>};
>```
>![[Pasted image 20230818193544.png]]
> - **Accessing Properties**
>![[Pasted image 20230818193632.png]]
> - **Bracket Notation**
>![[Pasted image 20230818193905.png]]
> - **Property Assignment**
> - `const` object can be mutated: Add new / change existing properties
>![[Pasted image 20230818194557.png]]
> - `delete` Operator - Deletes property from object
> - Nested Objects - Objects in another object as property
>```js
>let objectName = {
>	nestedObject: {
>		property1: 1,
>		property2: 2,
>		...
>		'nestedObjectAsString': {
>			property3: 3,
>			'property4': ['4, '5'],
>			...
>		}
>	}
>}
>
>// Call nested object
>objectName.nestedObject['nestedObjectAsString'].property3;
>// Call element from nested object's property value as array
>objectName.nestedObject['nestedObjectAsString']['property4'][0];
>```
> - Object array as value
>```js
>let objectName = {
>	property1: [{arrayObject: 'value'}, {arrayObject1: 'value'}],
>	...
>}
>```
> - `this` Keyword - Used in method to access and reference object's values
> - Doesn't work with `=>` functions
>```js
>function getThis() {
>  return this;
>}
>
>const obj1 = { name: "obj1" };
>const obj2 = { name: "obj2" };
>
>obj1.getThis = getThis;
>obj2.getThis = getThis;
>// (function without parameter) returns function definition
>
>console.log(obj1.getThis()); // { name: 'obj1', getThis: [Function: getThis] }
>console.log(obj2.getThis()); // { name: 'obj2', getThis: [Function: getThis] }
>```
> - `_property` - Used to signal developer not to alter property - Naming convention
> - `get` Keyword - Getter methods are used to `get` and `return` internal properties of an object
> - No need for `()` when called
> - `set` Keyword - Setter methods are used to reassign values of existing properties in an object
> - No need for `()` when called
> - **Factory Functions** - Function that returns an object and can be used to make multiple object instances
> - Returned object can be customized in parameters
>```js
>// Declaration
>let factoryFunction = (property1, property2, property3) => {
>	return {
>		property1: var1,
>		property2: var2,
>		prop3() {
>			 console.log(var3);
>		}
>	}
>}
>
>// Definition
>let objectName = factoryFunction('value1', 'value2', 'value3');
>objectName.prop3();
>```
> - **Destructuring** - Shortcut for assigning variables to properties
>```js
>// Before
>const monsterFactory = (name, age) => {
>	return {
>		name: name,
>		age: age
>	}
>};
>
>// After
>const monsterFactory = (name, age) => {
>	return {
>		name,
>		age
>	}
>};
>```
> - **Destructured Assignment** - Shortcut for assigning object and key to a variable
>```js
>// Before
>const residence = vampite.residence;
>
>// After
>const { residence } = vampire;
>```
