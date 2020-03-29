# Interview Questions

<details>
<summary>1. What is JS?</summary>

> #### Answer:
> JavaScript often abbreviated as JS, is a high-level, interpreted programming language that conforms to the ECMAScript specification. JavaScript has curly-bracket syntax, dynamic typing, prototype-based object-orientation, and first-class functions.
>
> Alongside HTML and CSS, JavaScript is one of the core technologies of the World Wide Web. JavaScript enables interactive web pages and is an essential part of web applications. The vast majority of websites use it, and major web browsers have a dedicated JavaScript engine to execute it.
>
> As a multi-paradigm language, JavaScript supports event-driven, functional, and imperative (including object-oriented and prototype-based) programming styles. It has APIs for working with text, arrays, dates, regular expressions, and the DOM, but the language itself does not include any I/O, such as networking, storage, or graphics facilities. It relies upon the host environment in which it is embedded to provide these features.
</details>

<details>
<summary>2. What data types are available in JS?</summary>

> #### Answer:
> There are 7 basic data types in JavaScript:
> - `number` for numbers of any kind: integer or floating-point
> - `string` for strings. A string may have one or more characters, there’s no separate single-character type
> - `boolean` for true/false
> - `null` for unknown values – a standalone type that has a single value null
> - `undefined` for unassigned values – a standalone type that has a single value undefined
> - `object` for more complex data structures
> - `symbol` for unique identifiers (es6)
</details>

<details>
<summary>3. Scope, functional, global. What is the difference betwee var, let, const?</summary>

> #### Answer:
> JavaScript does not have concept level scope. The variable declared inside the function has scope inside the function.
> Global variables are those that are available throughout the length of the code, that is, these have no scope. The var keyword is used to declare a local variable or object. If the var keyword is omitted, a global variable is declared.
>
> The problems that are faced by using global variables are the clash of variable names of local and global scope. Also, it is difficult to debug and test the code that relies on global variables.
>
> Differences between <code>var</code>, <code>let</code>, <code>const</code>:
> - variables declared using <code>var</code> are always hoisted to the top of their scope.
> - <code>var</code>'s are function-scoped
> - <code>const</code> restricts over-writing variables.
> - <code>const</code> doesn’t even let you declare a variable without assigning its (constant) value
> - <code>const</code> and <code>let</code> are block scoped
> - <code>let</code> and <code>const</code> declarations are not hoisted
</details>

<details>
<summary>4. How to define a function in JS?</summary>

> #### Answer:
> There are a few different ways to define a function in JavaScript:
>
> A Function Declaration defines a named function. To create a function declaration you use the function keyword followed by the name of the function. When using function declarations, the function definition is hoisted, thus allowing the function to be used before it is defined.
>
> ```javascript
> function name(parameters) {
>   // statements
> }
> ```
> A Function Expressions defines a named or anonymous function. An anonymous function is a function that has no name. Function Expressions are not hoisted, and therefore cannot be used before they are defined. In the example below, we are setting the anonymous function object equal to a variable.
>
> ```javascript
> let name = function(parameters) {
>   // statements
> }
> ```
> An Arrow Function Expression is a shorter syntax for writing function expressions. Arrow functions do not create their own this value.
>
> ```javascript
> let name = (parameters) => {
>   // statements
> }
> ```
</details>

<details>
<summary>5. The difference between "==" and "==="</summary>

> #### Answer:
> The identity (===) operator behaves identically to the equality (==) operator except no type conversion is done, and the types must be the same to be considered equal.
>
> The == operator will compare for equality after doing any necessary type conversions. The === operator will not do the conversion, so if two values are not the same type === will simply return false. Both are equally quick.
>
> JavaScript has two sets of equality operators: === and !==, and their evil twins == and !=. The good ones work the way you would expect. If the two operands are of the same type and have the same value, then === produces true and !== produces false. The evil twins do the right thing when the operands are of the same type, but if they are of different types, they attempt to coerce the values. the rules by which they do that are complicated and unmemorable. These are some of the interesting cases:
>
> ```javascript
> '' == '0'           // false
> 0 == ''             // true
> 0 == '0'            // true
>
> false == 'false'    // false
> false == '0'        // true
>
> false == undefined  // false
> false == null       // false
> null == undefined   // true
>
> ' \t\r\n ' == 0     // true
> ```
> The lack of transitivity is alarming. My advice is to never use the evil twins. Instead, always use === and !==. All of the comparisons just shown produce false with the === operator.
</details>

<details>
<summary>6. What is "this" keyword?</summary>

> #### Answer:
> <code>this</code> keyword refers to an object, that object which is executing the current bit of javascript code.
>
> In other words, every javascript function while executing has a reference to its current execution context, called <code>this</code>. Execution context means here is how the function is called.
>
> To understand <code>this</code> keyword, only we need to know how, when and from where the function is called, does not matter how and where function is declared or defined.
> ```javascript
> function bike() {
>   console.log(this.name);
> }
>
> var name = "Ninja";
> var obj1 = { name: "Pulsar", bike: bike };
> var obj2 = { name: "Gixxer", bike: bike };
>
> bike();      // "Ninja"
> obj1.bike(); // "Pulsar"
> obj2.bike(); // "Gixxer"
> ```
</details>

<details>
<summary>7. What is the difference between function declaration and function expression?</summary>

> #### Answer:
> A Function Declaration defines a named function variable without requiring variable assignment.
> Function Declarations occur as standalone constructs and cannot be nested within non-function blocks.
> It’s helpful to think of them as siblings of Variable Declarations.
> Just as Variable Declarations must start with <code>var</code>, Function Declarations must begin with <code>function</code>.
> ```javascript
> function bar() {
>     return 3;
> }
> ```
> A Function Expression defines a function as a part of a larger expression syntax (typically a variable assignment ).
> Functions defined via Functions Expressions can be named or anonymous.
> Function Expressions must not start with <code>function</code> (hence the parentheses around the self invoking example below)
> ```javascript
> // anonymous function expression
> var a = function() {
>     return 3;
> }
>
> // named function expression
> var a = function bar() {
>     return 3;
> }
>
> // self invoking function expression
> (function sayHello() {
>     alert("hello!");
> })();
> ```
> Function declarations get hoisted whereas when function expression is used,
> only variable declarations get hoisted but their assignment expressions don’t
</details>

<details>
<summary>8. What is the difference between null and undefined?</summary>

> #### Answer:
> Below are the main differences between null and undefined,
>    | Null | Undefined |
>    |---- | -----------|
>    | It is an assignment value which indicates that variable points to no object.  | It is not an assignment value where a variable has been declared but has not yet been assigned a value. |
>    | Type of null is object | Type of undefined is undefined  |
>    | The null value is a primitive value that represents the null, empty, or non-existent reference. | The undefined value is a primitive value used when a variable has not been assigned a value.|
>    | Indicates the absence of a value for a variable | Indicates absence of variable itself |
>    | Converted to zero (0) while performing primitive operations | Converted to NaN while performing primitive operations |

</details>

<details>
<summary>9. What are the possible ways to create objects in JavaScript?</summary>

> #### Answer:
> There are many ways to create objects in javascript as below,
> 1. **Object constructor:**
> The simplest way to create an empty object is using Object constructor. Currently this approach is not recommended.
> ```javascript
> var object = new Object();
> ```
> 2. **Object's create method:**
> The create method of Object creates a new object by passing the prototype object as a parameter
> ```javascript
> var object = Object.create(null);
> ```
> 3. **Object literal syntax:**
> The object literal syntax is equivalent to create method when it passes null as parameter
> ```javascript
> var object = {};
> ```
> 4. **Function constructor:**
> Create any function and apply the new operator to create object instances,
> ```javascript
> function Person(name) {
>   var object = {};
>   object.name = name;
>   object.age = 21;
> 
>   return object;
> }
>
> var object = new Person("Max");
> ```
>
> 5. **Function constructor with prototype:**
> This is similar to function constructor but it uses prototype for their properties and methods,
> ```javascript
> function Person() {}
> Person.prototype.name = "Max";
> var object = new Person();
> ```
> This is equivalent to an instance created with an object create method with a function prototype and then  call that function with an instance and parameters as arguments.
> ```javascript
> function func {};
>
> new func(x, y, z);
>
> // **(OR)**
> // Create a new instance using function prototype.
> var newInstance = Object.create(func.prototype)
> // Call the function
> var result = func.call(newInstance, x, y, z),
>
> // If the result is a non-null object then use it otherwise just use the new instance.
> console.log(result && typeof result === 'object' ? result : newInstance);
> ```
>
> 6. **ES6 Class syntax:**
> ES6 introduces class feature to create the objects
> ```javascript
> class Person {
>   constructor(name) {
>       this.name = name;
>   }
> }
>
> var object = new Person("Max");
> ```
> 7. **Singleton pattern:**
> A Singleton is an object which can only be instantiated one time. Repeated calls to its constructor return the same instance and this way one can ensure that they don't accidentally create multiple instances.
> ```javascript
> var object = new function() {
>   this.name = "Max";
> }
> ```
</details>

<details>
<summary>10. What are lambda or arrow functions?</summary>

> #### Answer:
> An arrow function is a shorter syntax for a function expression and does not have its own **this, arguments, super, or new.target**. These function are best suited for non-method functions, and they cannot be used as constructors.
>
> In other words, every javascript function while executing has a reference to its current execution context, called <code>this</code>. Execution context means here is how the function is called.
>
> To understand <code>this</code> keyword, only we need to know how, when and from where the function is called, does not matter how and where function is declared or defined.
> ```javascript
> let hello = (val) => "Hello " + val;
>
> let squares = [1, 2, 3].map(x => x * x);
> ```
</details>

<details>
<summary>11. What is a pure function?</summary>

> #### Answer:
> A **Pure function** is a function where the return value is only determined by its arguments without any side effects. i.e, If you call a function with the same arguments 'n' number of times and 'n' number of places in the application then it will always return the same value. Let's take an example to see the difference between pure and impure functions,
> ```javascript
> // Impure
> let numberArray = [];
> const impureAddNumber = number => numberArray.push(number);
> // Pure
> const pureAddNumber = number => argNumberArray => argNumberArray.concat([number]);
>
> // Display the results
> console.log (impureAddNumber(6)); // returns 6
> console.log (numberArray); // returns [6]
> console.log (pureAddNumber(7) (numberArray)); // returns [6, 7]
> console.log (numberArray); // returns [6]
> ```
> As per above code snippets, Push function is impure itself by altering the array and returning an push number index which is independent of parameter value. Whereas Concat on the other hand takes the array and concatenates it with the other array producing a whole new array without side effects. Also, the return value is a concatenation of previous array.
> Remember that Pure functions are important as they simplify unit testing without any side effects and no need for dependency injection. They also avoid tight coupling and makes harder to break your application by not having any side effects. These principles are coming together with **Immutability** concept of ES6 by giving preference to **const** over **let** usage.

</details>