# Node.js
___
## Promises
- Object that represents the eventual outcome of an *asynchronous operation*
- Outcomes: 
	- **pending** (result: undefined, waiting for result)
	- **fulfilled** (result: return value)
	- **rejected** (result: error object)
### Code
```js
// Promise definition with anonymous function
const test = new Promise((resolve, reject) => {
	resolve(/*return value*/);
	reject(new Error(/*return value*/));
});

// Error handling
test
	.then(handleFulfilled)
	.catch(handleRejected);
```

**Async/Await**
```js
const asyncFunc = async () => {
	const result = await test;
}
```

**setInterval() and setTimeout()**
```js
// Execute code block at specified interval in ms until clearInterval() is called
const interval = setInterval(() => {
	alert('I show every 5 sec')
}, 5000);
clearInterval(interval);

// Execute code block after specified amount of time in ms until clearTimeout() is called
const timeout = setTimeout(() => {
	alert('I show after 5 sec');
}, 5000);
clearTimeout(timeout);
```



## Modules
### Console
- Global
- `console.log()` Prints message to terminal
- `console.assert()` Prints message to terminal if value is falsy
- `console.table()` Prints out table in terminal from object or array
### Process
- Global
- Stores and controls information about the environment in which the process is currently running
- `process.argv` Holds array of command line values provided when process was initiated
### OS
- Not Global
- `os.type()` returns computer's os
- `os.arch()` returns os CPU architecture
- `os.networkInterfaces()` returns info about network interfaces of computer (IP, MAC, etc.)
- `os.homedir()` returns current user's home directory
- `os.hostname()` returns hostname of os
- `os.uptime()` returns system uptime in sec

### Util
- Not Global
- Tools used to maintain code and debug
- `util.types.isType()` Runtime type checking, returns bool
- 