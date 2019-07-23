<style>
  html body {
    background-color:rgb(40,44,52);
    color: white;
    font-size: 30px;
  }
  .section-title {
    font-size: 40px;
    color: rgb(103, 218, 249);
  }
  .section-container {
    display:flex;
    justify-content:center;
    align-items:center;
  }
  .error-text {
    color: red;
  }
  .tip {
    color: green;
  }
  .markdown-preview {
    padding: 100px !important;
  }
</style>

<div class="section-container">
  <img src="img/javascript-illustration.png"/>
</div>

<h2 class="section-title" align="center">What is JavaScript?</h2>

* A language for the web browser _and_ the server ([node.js](https://nodejs.org/en/))
* High level (very abstracted), interpretted programming language (not pre-compiled, more or less true)
* Implements the [ECMAScript® Language Specification](https://www.ecma-international.org/ecma-262/10.0/index.html#Title)
* Is multi-paradigm (you can write your code in many different ways)

<div class="section-container">
  <h2 class="section-title" align="center">Why learn JavaScript?</h2>
  <img src="img/why.png" width="100" height="100"/>
</div>

* You can build lots of things with it!
* Iteractive user interfaces using awesome frameworks
  * [angular](https://angular.io/)
  * [vue](https://vuejs.org/)
  * [react](https://reactjs.org/)
* Very fast server side applications
  * [express](https://expressjs.com/)
* Mobile apps
  * [react native](https://facebook.github.io/react-native/)
  * [NativeScript](https://www.nativescript.org/)
* Even desktop applications
  * [electron](https://electronjs.org/)

<h2 class="section-title" align="center">What will we learn?</h2>

* This is a crash course.
* Just the basics, no frameworks (yet)
* `variables` and `data types`
* `conditionals`
* `arrays`
* `objects`
* `loops`
* `functions`
* Keep on learning! 
  * [mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
  * [codecademy](https://www.codecademy.com/learn/introduction-to-javascript)
  * [udemy](https://www.udemy.com/)
  * many more

<h2 class="section-title" align="center">How do we use JavaScript?</h2>

`index.html`
```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>How do we use JavaScript?</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <!--we want our HTML and CSS to load first-->
    <script src="script.js"></script>
  </body>
</html>
```

`script.js`
```javascript
console.log('hello world!');
```

<h2 class="section-title" align="center">Variables</h2>

```javascript
let age = 30; // can be reassigned
age = 31; // yes
const name = 'Radu'; // can NOT be reassigned
name = 'Tudor'; // nope 
```
<code class="error-text">TypeError: Assignment to constant variable.</code>
<br/>

```javascript
const name; // MUST be initialized
```
<code class="error-text">SyntaxError: Missing initializer in const declaration.</code>

<br/>

> <p class="tip">Always use <code>const</code> unless you're sure you want to reassign that value.</p>

<h2 class="section-title" align="center">Data types</h2>

* `numbers` 
```javascript 
10
-50
3.14159
```
* `strings` 
```javascript 
'hello world'
"double quotes are also cool"
```
* `booleans`
```javascript 
true
false
```
* `undefined` and `null`
```javascript 
undefined
null
```
<img src="img/null_vs_undefined.png"/>

* `object`
```javascript 
{
  name: 'Claudia',
  age: 29
  isLoggedIn: true
}

// arrays are also objects
typeof [1, 2, 3] // object
typeof null // object 🤦‍ 
/*
Because the spec says so. 
This is generally regarded as a mistake.
*/
```

<br/>

`autoboxing`
```javascript 
const name = 'Radu';
typeof name; // string
name.length; // 4
```
> <p class="tip">This a process called autoboxing. When you call a property on a primitive types, JavaScript will first convert it into a temporary wrapper object, and access the property / method on it, without affecting the original.</p>


<h2 class="section-title" align="center">String concatenation</h2>

`normal addition`
```javascript 
const name = 'Radu';
const age = 30;
const message = 'My name is ' + name + ' and I am ' + age;
// My name is Radu and I am 30;
```

<br/>

`template strings`
```javascript 
const name = 'Radu';
const age = 30;
const message = `My name is ${name} and I am ${age}`;
// My name is Radu and I am 30;
// We MUST use backticks!
```
<br/>

<h2 class="section-title" align="center">Conditionals</h2>

`if`
```javascript 
const myAge = 30;
const yourAge = 30;

if (myAge > yourAge) {
  console.log('I am older than you.');
}
```

`else`

```javascript 
const myAge = 30;
const yourAge = 30;

if (myAge > yourAge) {
  console.log('I am older than you.');
}
else {
  console.log('I am younger than you.');
}
```

`else if`
```javascript 
const myAge = 30;
const yourAge = 25;

if (myAge > yourAge) {
  console.log('I am older than you.');
}
else if (myAge === yourAge) {
  console.log('We are the same age.');
}
else {
  console.log('I am younger than you.');
}
```

<h2 class="section-title" align="center">Checking for equality</h2>

`==` 
* Will compare for equality after doing any necessary type conversions
```javascript 
const myAge = 30;
const yourAge = '30'

myAge == yourAge; // true
```

`===`
* Will _not_ do the conversion
```javascript 
const myAge = 30;
const yourAge = '30'

myAge === yourAge; // false
```

> <p class="tip">There are many things to say here but most importantly, always use <code>===</code>.</p>

<br/>

<h2 class="section-title" align="center">Arrays</h2>

* Lists that hold multiple values
* Are homogeneous (can store mixed data types)
* We can access individual elements or add new ones.


```javascript 
const names = ['Silvia', 'Victor', 'Robert'];
const values = ['test', 10, true, null, [1, 2]];
```
<br/>

`declaration`
> <p class="tip">Remember that arrays are zero based. The first element has index <code>0</code>.</p>

```javascript 
const name = names[0]; // Silvia 
```
<br/>

`index`
```javascript 
const name = names[0]; // Silvia 
```
`length`
```javascript
console.log(names.length); // 3
```
<br/>

`.push()`
```javascript 
names.push('Radu');
console.log(names); // 'Silvia', 'Victor', 'Robert', 'Radu'
console.log(names.length); // 4
```
> <p class="tip">There are more array methods, read about them <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array">here</a>.</p>

> <p class="tip">While an array is of type <code>object</code>, you can check if a value is an array using <code>Array.isArray()</code>.</p>

<br/>

<h2 class="section-title" align="center">The for loop</h2>

* Loops offer a quick and easy way to do something repeatedly.
* There are many different kinds of loops, but they all essentially do the same thing.
* They repeat an action some number of times.

`structure`
```javascript 
for ([initialExpression]; [condition]; [incrementExpression])
  statement
```
`implementation`
```javascript 
for (let i = 0; i < 3; i++) {
	console.log(i)
}
// 0
// 1
// 2
```
`arrays`
```javascript 
const names = ['Silvia', 'Victor', 'Robert'];

for (let i = 0; i < names.length; i++) {
	console.log(names[i])
}
// 'Silvia'
// 'Victor'
// 'Robert'
```

> <p class="tip">Always be careful to not write an infinite loop.</p>
```javascript 
for (let i = 0; i < 3; i--) {
	console.log(names[i])
}
// 0
// -1
// -2
// Infinity...
```
<br/>

<h2 class="section-title" align="center">Object literals</h2>

* a collection of related data
* key : value pairs
* used when storing information
* makes stuff easier to read
* useful sending / receiving a request to / from the server 

`declaring properties`
```javascript 
const person = {
  name: 'Silvia',
  age: 21,
  isLoggedIn: true
};

person.name; // Silvia
person.age; // 21
```

`reading properties`
```javascript 
person.name; // Silvia
person.age; // 21
person.height; // undefined
```
`writing properties`
```javascript 
person.address = 'Park Street no. 11';
```
<br/>

<h2 class="section-title" align="center">Functions</h2>

* One of the fundamental building blocks in JavaScript
* A function is a JavaScript procedure—a set of statements that performs a task or calculates a value.
* To use a function, you must define it somewhere in the scope from which you wish to call it.

`declaration`
 
 * name
 * list of parameters (optional)
 * statements enclosed in curly brackets `{}`
```javascript 
function sayHello() {
  console.log('hello world');
}
```
`invocation`
```javascript 
sayHello();
// hello world
```
`one parameter`
```javascript 
function square(number) {
  return number * number;
}
const number = square(4); // 16
```
`multiple parameters`
```javascript 
function add(a, b) {
  return a + b;
}
const sum = add(100, 300); // 400
```

<br/>
<br/>
<br/>
<br/>

<h2 class="section-title" align="center">Thanks!</h2>