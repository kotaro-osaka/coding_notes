> [!info]- Info
> - **Separation of Concerns (SoC)** - Separate code into different files to prevent messy code
> - **HTML Parser** - Used by browser to analyze and process HTML code
> - **Document Object Model (DOM)** - Used by browser
> - The DOM is a logical tree-like Model that organizes a web page’s HTML Document as an Object
> - Implemented to allow JS to access, modify and update structure of HTML in an organized way
> - Link between HTML web page and scripting language
> ![[dom_revision_1 1.png]]
> ![[Pasted image 20230821093733.png]]
> - **Events** - Are fired to notify code of "interesting changes" that may affect code
> 	- User interactions
> 	- Changes in state of underlying environment (low battery, media events, etc.)
> - Hyphen-Style (HTML) --> camelCase (JS)

> [!example]- HTML
> - `<script>` - Add JS code
> - Can delay loading times - `script` element blocks following elements from loading
> - Scripts are loaded subsequently in order
> - `src` - Used to specify script file location
>```html
><script src="./exampleScript.js"></script>
>```
> - `defer` Attribute - Specifies scripts should be executed after HTML file is completely parsed
> - Parser loads script but defers execution
> - Used when script doesn't have to be executed immediately when script is encountered
>```html
><script src="example.js" defer></script>
>```
> - `async` Attribute - Loads and executes script asynchronously with rest of the webpage
> 	- Parsing continues and script is downloaded in the background
> 	- Will not wait until entire page is parsed

> [!example]- JavaScript
>> [!info]- Info
>> - `document` - Root node
> 
>> [!example]- Properties
>> - `.innerHTML` - Set the contents of an element
>>```js
>>// Example - Reassign contents of `<body>` element to the text `'The cat loves the dog'`
>>document.body.innerHTML = 'The cat loves the dog.';
>>
>>// With HTML elements
>>document.body.innerHTML = '<h2>This is a heading</h2>';
>>```
>> - `.style` - Access CSS style - [CSS List](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Properties_Reference)
>>```js
>>// Syntax
>>element.style.property
>>```
>> - `.parentNode` - Returns parent of specified node
>>```js
>>// Example
>>let blueElement = document.querySelector('blue');
>>blueElement.style.backgroundColor = 'blue';
>>```
>> - `.children` - Returns array of children from specified node // null
>> - `.id` Property - Used to assign value as ID
>>```js
>>let paragraph;
>>paragraph.id = 'info';
>>paragraph.innerHTML = 'The text inside the paragraph';
>>```
>> - `.hidden` - Hides element, by setting property as `true` or `false`
>>```js
>>document.getElementById('sign').hidden = true;
>>```
>> - `.onclick` - Assign function to run when click event happens to an element
>>```js
>>// Example
>>let element = document.querySelector('button');
>>
>>element.onclick = function() {
>>	element.style.backgroundColor = 'blue';
>>};
>>
>>// Assign `.onlick` to function by name
>>element.onclick = functionName;
>>```
>> - `.target` - References element that event is registered to
>> - `.type` - Returns event type as string
>> - `.timeStamp` - Get number of milliseconds since event
>> - `.key` - Stores values of the pressed key
>
>> [!example]- Methods
>> - `.querySelector()` - Specify CSS selector as string and return first element that matches selector
>>```js
>>// Example - Return first paragraph in document
>>document.querySelector('p');
>>```
>> - `.getElementById()` - Access element directly by its `id`
>>```js
>>// Example
>>document.getElementById('bio').innerHTML = 'The description';
>>```
>> - `.getElementsByClassName()` - Returns array of elements
>> 	- Use `[]` Bracket Notation to access individual elements of an array
>>```js
>>// Set first element of .student class as 'Not yet registered'
>>document.getElementsByClassName('student')
>>[0].innerHTML = 'Not yet registered';
>>```
>> - `.getElementsByTagName()` - Returns array of elements
>> 	- Use `[]` Bracket Notation to access individual elements of an array
>>```js
>>// Set second `<li>` tag as 'Cedric Diggory'
>>document.getElementByTagName('li')[1].innerHTML = 'Cedric Diggory';
>>```
>> - `.createElement()` - Creates new element based on argument
>> 	- Creates empty element with no `innerHTML`
>>```js
>>let paragraph = document.createElement('p');
>>```
>> - `appendChild()` - Adds child element as parent's last child node
>>```js
>>let paragraph = document.createElement('p');
>>document.body.appendChild(paragraph);
>>
>>// Add variable `newAttraction` to list of values with ID of `italy-attractions`
>>document.getElementById('italy-attractions').appendChild(newAttraction);
>>```
>> - `.removeChild()` - Removes specified child from parent
>>```js
>>let paragraph = document.querySelector('p'); // Select first `p` element and assign to var
>>document.body.removeChild(paragraph); // Remove `paragraph` from body
>>```
>
>> [!example]- Event Interface
>> - `eventTarget` - DOM Element
>> - `.addEventListener(arg, arg)` Method - Listen for event and execute code block  when detected
>> 	- Event Target - Listens for an event
>> 	- Event Handler - Block of code that runs when event happens
>>```js
>>eventTarget.addEventListener('click', eventHandlerFunction() {
>>// This block of code will run when click event happens on eventTarget element
>>});
>>```
>>> [!example]- Events
>>> - `click`: Triggered on a mouse click.
>>> - `keydown`: Triggered when a key is pressed down.
>>> - `keyup`: Triggered when a key is released.
>>> - `keypress`: Triggered when key is pressed and released
>>> - `mouseenter`/`mouseover`: Triggered when the mouse enters an element.
>>> - `mouseleave`/`mouseout`: Triggered when the mouse leaves an element.
>>> - `mousedown`: Triggered when mouse button is pressed down
>>> - `mouseup`: Triggered when mouse button is released
>>> - `submit`: Triggered when a form is submitted.
>>> - `load`: Triggered when a page or resource finishes loading.
>>> - `DOMContentLoaded`: Triggered when the initial HTML document has been completely loaded.
>>> - `resize`: Triggered when the browser window is resized.
>>> - `scroll`: Triggered when the user scrolls through an element.
>>> - `input`: Triggered when the value of an input element changes.
>>> - `change`: Triggered when the value of a form element changes and loses focus.
>>> - `focus`: Triggered when an element gains focus.
>>> - `blur`: Triggered when an element loses focus.

> [!example]- Handlebars.js Library
> - `{{ }}` - Content in braces serve as placeholder
> - Create context object
>```js
>let contextObjectVariable = {
>	key: value
>}
>```
> [More](obsidian://open?vault=Coding%20Notes&file=Cheatsheet_Handlebars.pdf)
