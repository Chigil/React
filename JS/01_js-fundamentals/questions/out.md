# Exam Questions

<details>
<summary>1. How to add JS on the page? (deferred, async)</summary>

>#### Answer:
> JS is referenced using <code>\<script\></code> tag.
> When the browser processes an HTML document, it does so from top to bottom.
> Upon encountering a <code>\<script\></code> tag, it halts (“blocks”) further processing in order to download the referenced script file.
> Only after that download has completed and the respective JavaScript code has been processed, HTML processing continues.
> ```html
> <html>
>     <head>
>         <meta charset="utf-8">
>         <meta name="viewport" content="width=device-width, initial-scale=1">
>         <title>Hello World</title>
>         <link rel="stylesheet" href="main.css">
>         <script src="foo.js"></script>
>     </head>
>     <body>
>         <h1>Hello World</h1>
>         <script src="bar.js"></script>
>         <p>lorem ipsum dolor sit amet</p>
>         <script src="baz.js"></script>
>     </body>
> </html>
> ```
> Once we arrive at <code>\<script src="foo.js"\></code>, processing halts as described.
> Afterwards, we continue to <code>\<script src="bar.js"\></code>, repeat the same procedure, and then move on to <code>\<script src="baz.js"\></code> for the final piece.
> That leaves us with the following sequence:
> ```
> |
> | |-foo.js-|
> |          |-bar.js-|
> |                   |-baz.js-|
> |
> +------------------------------> t
> ```
> To change this sequence to be parallel <code>async</code> and <code>defer</code> keywords can be used.
> - The <code>async</code> attribute is used to indicate to the browser that the script file can be executed asynchronously. The HTML parser does not need to pause at the point it reaches the script tag to fetch and execute, the execution can happen whenever the script becomes ready after being fetched in parallel with the document parsing.
> - The <code>defer</code> attribute tells the browser to only execute the script file once the HTML document has been fully parsed.

</details>

<details>
<summary>2. How is JS code processed in a browser?</summary>

>#### Answer:
> JavaScript has no compilation step.
> Instead, an interpreter in the browser reads over the JavaScript code, interprets each line, and runs it.
> Modern browsers use a technology known as Just-In-Time (JIT) compilation, which compiles JavaScript to executable bytecode just as it is about to run.
</details>

<details>
<summary>3. What is hoisting?</summary>

>#### Answer:
>When Javascript compiles all of your code, all variable declarations using var are hoisted/lifted to the top of their functional/local scope (if declared inside a function) or to the top of their global scope (if declared outside of a function) regardless of where the actual declaration has been made. This is what we mean by “hoisting”.
> ```javascript
> console.log(message); // output : undefined
> var message = 'The variable Has been hoisted';
> ```
> The above code looks like as below to the interpreter,
> ```javascript
> var message;
> console.log(message);
> message = 'The variable Has been hoisted';
> ```
> Functions declarations are also hoisted, but these go to the very top, so will sit above all of the variable declarations.

</details>

<details>
<summary>4. Params, arguments, rest and default params</summary>

>#### Answer:
> Function parameters are the names listed in the function definition.
>
> Function arguments are the real values passed to (and received by) the function.
>
> JavaScript function definitions do not specify data types for parameters.
>
> JavaScript functions do not perform type checking on the passed arguments.
>
> JavaScript functions do not check the number of arguments received.
>
> Rest parameters are used for variable count of parameters:
> ```javascript
> function containsAll(haystack, ...needles) {
>   for (var needle of needles) {
>     if (haystack.indexOf(needle) === -1) {
>       return false;
>     }
>   }
>   return true;
> }
> 
> console.log(containsAll([1,2], 1,2)); // true
> ```
>
> Default parameters used to set default value if argument is not provided:
> ```javascript
> function test(a, b = 2) {
>   return a + b;
> }
> 
> console.log(test(2)); // 4
> ```

</details>

<details>
<summary>5. Undefined & undeclared & null.</summary>

>#### Answer:
> ##### Undefined
> It means a variable has been declared but has not yet been assigned a value.
>
> ```javascript
> var a;
> console.log(a); // undefined
> console.log(typeof a); // undefined
> // You can see type is also undefined.
> ```
>
> ##### Null
> It can be assigned to a variable to represent no value. It is an assignment value.
>
> ```javascript
> var b = null;
> console.log(b); // null
> console.log(typeof b); // object
> // Here the type is object.
> ```
>
> ##### Undeclared
> If a variable is not declared then the browser throws error.
>
> ```javascript
> console.log(nonDeclaredVariable);
>
> // Uncaught ReferenceError: nonDeclaredVariable is not defined
> //    at <anonymous>:1:13
>
> console.log(typeof nonDeclaredVariable); // undefined
> ```
>
> Here the type is undefined. So you can check undeclared variable by checking its type:
> ```javascript
> if(typeof nonDeclaredVariable !== 'undefined') {
>     // Do something here
> }
> ```
> Note: If you use var when you’re declaring a variable inside a function, then that variable becomes a local variable. However, if you don’t use var, then the variable becomes a global variable no matter where you declare it.
>
> If any property is not declared then NO error is thrown, it returns undefined.
>
> ```javascript
> var myVar = {};
> console.log(myVar.myProp); // undefined
> ```
</details>

<details>
<summary>6. What is 'use strict'?</summary>

>#### Answer:
> The statement <code>'use strict';</code> instructs the browser to use the Strict mode, which is a reduced and safer feature set of JavaScript.
>
> Strict Mode is a new feature in ECMAScript 5 that allows you to place a program, or a function, in a “strict” operating context. This strict context prevents certain actions from being taken and throws more exceptions.
>
> Benifits of using <code>‘use strict’</code>
> Strict mode makes several changes to normal JavaScript semantics.
>
> - Strict mode eliminates some JavaScript silent errors by changing them to throw errors.
> - Strict mode fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run faster than identical code that’s not strict mode.
> - Strict mode prohibits some syntax likely to be defined in future versions of ECMAScript.
> - It prevents, or throws errors, when relatively “unsafe” actions are taken (such as gaining access to the global object).
> - It disables features that are confusing or poorly thought out.
> - Strict mode makes it easier to write “secure” JavaScript.
> Strict mode can be used in two ways – used in global scope for the entire script and can be applied to individual functions. Strict mode doesn’t work with block statements enclosed in <code>{}</code> braces.
> 
> If declare at the beginning of a script, it has global scope.
> ```javascript
> "use strict";
> x = 3.14; // This will cause an error because x is not declared
> ```
> and if you declare inside a function, it has local scope
> ```javascript
> x = 3.14;       // This will not cause an error.
> myFunction();
> 
> function myFunction() {
>   "use strict";
>    y = 3.14;   // This will cause an error
> }
> ```

</details>

<details>
<summary>7. What is closure?</summary>

>#### Answer:
> A closure is a feature in JavaScript where an inner function has access to the outer (enclosing) function’s variables — a scope chain.
>
> The closure has three scope chains:
>
> - it has access to its own scope — variables defined between its curly brackets
> - it has access to the outer function’s variables
> - it has access to the global variables
> - To the uninitiated, this definition might seem like just a whole lot of jargon!
>
> This allows the function to save it's state.
>
> Example:
> ```javascript
> function outer() {
>   var b = 10;
>   var c = 100;
> 
>   function inner() {
>       var a = 20;
>       console.log("a=" + a + " b=" + b);
>       a++;
>       b++;
>   }
> 
>   return inner;
> }
> 
> var X = outer();  // outer() invoked the first time
> X() // a=20 b=10
> X() // a=20 b=11
> X() // a=20 b=12
> ```

</details>

<details>
<summary>8. What is an IIFE (Immediately Invoked Function Expression)
pattern?</summary>

> #### Answer:
> An Immediately-invoked Function Expression is a way to execute functions immediately, as soon as they are created. IIFEs are very useful because they don't pollute the global object, and they are a simple way to isolate variables declarations
>
> This is the syntax that defines an IIFE:
> ```javascript
> (function() {
>   /* */
> })()
> ```
> IIFEs can be defined with arrow functions as well:
> ```javascript
> (() => {
>   /* */
> })()
> ```
</details>

<details>
<summary>9. What is a higher order function?</summary>

> #### Answer:
> Higher-order function is a function that accepts other function as an argument or returns a function as a return value.
> ```javascript
> const firstOrderFunc = () => console.log ('Hello I\'am a First order function');
> const higherOrder = ReturnFirstOrderFunc => ReturnFirstOrderFunc ();
> higherOrder (firstOrderFunc);
> ```
</details>

<details>
<summary>10. What is "this" keyword?</summary>

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
<summary>11. How to change the context of the calling function?</summary>

> #### Answer:
> <code>call</code>, <code>apply</code> and <code>bind()</code> functions can be used to change the function context.
>
> The <code>call</code> function requires the arguments to be listed explicitly while the <code>apply</code> function allows you to provide the arguments as an array:
> ```javascript
> function user(firstName, lastName, age) {
>     // do something
> }
>
> user.call(window, 'John', 'Doe', 30);
> user.apply(window, ['John', 'Doe', 30]);
> ```
> ECMAScript 5 (ES5) introduced the <code>Function.prototype.bind</code> method that is used for manipulating context. It returns a new function which is permanently bound to the first argument of <code>bind</code> regardless of how the function is being used. It works by using a closure that is responsible for redirecting the call in the appropriate context.
> 
> ```javascript
> var module = {
>   x: 42,
>   getX: function() {
>     return this.x;
>   }
> }
>
> var unboundGetX = module.getX;
> // The function gets invoked at the global scope
> console.log(unboundGetX()); // undefined
>
> var boundGetX = unboundGetX.bind(module);
> console.log(boundGetX()); // 42
> ```
</details>

<details>
<summary>12. What is prototypal inheritance?</summary>

> #### Answer:
>In JavaScript, objects have a special hidden property <code>[[Prototype]]</code> (as named in the specification), that is either null or references another object.
> That object is called “a prototype”: That <code>[[Prototype]]</code> has a “magical” meaning.
> When we want to read a property from object, and it’s missing, JavaScript automatically takes it from the prototype.
> In programming, such thing is called “prototypal inheritance”. Many cool language features and programming techniques are based on it.
>
> The property <code>[[Prototype]]</code> is internal and hidden, but there are many ways to set it. One of them is to use <code>\__proto__</code>.
> ```javascript
> let animal = {
>   eats: true
> };
> let rabbit = {
>   jumps: true
> };
>
> rabbit.__proto__ = animal;
> // If we look for a property in rabbit, and it’s missing, JavaScript
> // automatically takes it from animal.
> console.log(rabbit.eats); // true
> console.log(rabbit.jumps); // true
> ```
> <code>\__proto__</code> is not the same as <code>[[Prototype]]</code>. That’s a getter/setter for it.
>
> It exists for historical reasons, in modern language it is replaced with functions <code>Object.getPrototypeOf</code>/<code>Object.setPrototypeOf</code> that also get/set the prototype.
> - If we want to read a property of obj or call a method, and it doesn’t exist, then JavaScript tries to find it in the prototype. Write/delete operations work directly on the object, they don’t use the prototype (unless the property is actually a setter).
> - If we call <code>obj.method()</code>, and the method is taken from the prototype, this still references obj. So methods always work with the current object even if they are inherited.
</details>

<details>
<summary>13. What do setTimeout and setInterval functions do? What do they
return?</summary>

> #### Answer:
> <code>setTimeout</code> allows to run a function once after the interval of time.
>
> <code>setInterval</code> allows to run a function regularly with the interval between the runs.
>
> These methods are not a part of JavaScript specification.
> But most environments have the internal scheduler and provide these methods.
> In particular, they are supported in all browsers and Node.JS.
> ```javascript
> function sayHi() {
>   alert('Hello');
> }
>
> setTimeout(sayHi, 1000); // executed after a second
> setInterval(sayHi, 1000); // executed every second
> ```
> - Methods <code>setInterval(func, delay, ...args)</code> and <code>setTimeout(func, delay, ...args)</code> allow to run the func regularly/once after delay milliseconds.
> - To cancel the execution, we should call <code>clearInterval</code>/<code>clearTimeout</code> with the value returned by <code>setInterval</code>/<code>setTimeout</code>.
> - Nested <code>setTimeout</code> calls is a more flexible alternative to <code>setInterval</code>. Also they can guarantee the minimal time between the executions.
> - Zero-timeout scheduling <code>setTimeout(..., 0)</code> is used to schedule the call “as soon as possible, but after the current code is complete”.
</details>

<details>
<summary>14. How can we get and array of number from array of their string representations? Describe the array.map method.</summary>

> #### Answer:
> ```javascript
> var test = ['144','24','33']
> test.map(x => parseInt(x))
> ```
> - The <code>map</code> method creates a new array with the results of calling a function for every array element.
> - The <code>map</code> method calls the provided function once for each element in an array, in order.
> - Note: <code>map</code> does not execute the function for array elements without values.
> - Note: <code>map</code> does not change the original array.
</details>

<details>
<summary>15. What is the difference between arrow functions and regular functions?</summary>

> #### Answer:
> An arrow function expression is a syntactically compact alternative to a regular function expression, although without its own bindings to the <code>this</code>, <code>arguments</code>, <code>super</code> or <code>new.target</code> keywords. Arrow function expressions are ill suited as methods, and they cannot be used as constructors.
>#### Answer:
> ```javascript
> var materials = [
>   'Hydrogen',
>   'Helium',
>   'Lithium',
>   'Beryllium'
> ];
>
> console.log(materials.map(material => material.length));
> ```
</details>

<details>
<summary>16. What is rest/spread operator?</summary>

> #### Answer:
> The rest parameters can be mentioned in a function definition with three dots <code>...</code>.
> They literally mean “gather the remaining parameters into an array”.
> For instance, to gather all arguments into array args:
> ```javascript
> function sumAll(...args) { // args is the name for the array
>   let sum = 0;
>   for (let arg of args) sum += arg;
>   return sum;
> }
>
> alert(sumAll(1)); // 1
> alert(sumAll(1, 2)); // 3
> alert(sumAll(1, 2, 3)); // 6
> ```
> Spread operator looks similar to rest parameters, also using <code>...</code>, but does quite the opposite. When <code>...arr</code> is used in the function call, it “expands” an iterable object arr into the list of arguments.
>```javascript
> let arr = [3, 5, 1];
>
> console.log(Math.max(...arr) ); // 5 (spread turns array into a list of arguments)
>```
</details>

<details>
<summary>17. What is destructured assignment?</summary>

> #### Answer:
> The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.
> ```javascript
> var a, b, rest;
> [a, b] = [10, 20];
>
> console.log(a); // 10
>
> console.log(b); // 20
>
> [a, b, ...rest] = [10, 20, 30, 40, 50];
>
> console.log(rest); [30,40,50]
> ```
</details>

<details>
<summary>18. What is Promise? What for methods resolve, reject, all and race are used?</summary>

> #### Answer:
> The Promise object represents the eventual completion (or failure) of an asynchronous operation, and its resulting value.
>
> A Promise is in one of these states:
> - pending: initial state, neither fulfilled nor rejected.
> - fulfilled: meaning that the operation completed successfully.
> - rejected: meaning that the operation failed.
>
> Promise methods:
> - <code>Promise.resolve()</code> returns a Promise object that is resolved with the given value. If the value is a thenable (i.e. has a then method), the returned promise will "follow" that thenable, adopting its eventual state; otherwise the returned promise will be fulfilled with the value. Generally, if you don't know if a value is a promise or not, Promise.resolve(value) it instead and work with the return value as a promise.
> - <code>Promise.reject()</code> returns a Promise object that is rejected with the given reason.
> - <code>Promise.all(iterable)</code> returns a promise that either fulfills when all of the promises in the iterable argument have fulfilled or rejects as soon as one of the promises in the iterable argument rejects. If the returned promise fulfills, it is fulfilled with an array of the values from the fulfilled promises in the same order as defined in the iterable. If the returned promise rejects, it is rejected with the reason from the first promise in the iterable that rejected. This method can be useful for aggregating results of multiple promises.
> - <code>Promise.race(iterable)</code> returns a promise that fulfills or rejects as soon as one of the promises in the iterable fulfills or rejects, with the value or reason from that promise.
</details>

<details>
<summary>19. What is promise chaining?</summary>

> #### Answer:
>  The process of executing a sequence of asynchronous tasks one after another using promises is known as Promise chaining.
> ```javascript
>  new Promise(function(resolve, reject) {
>
>      setTimeout(() => resolve(1), 1000);
>
>    }).then(function(result) {
>
>      console.log(result); // 1
>      return result * 2;
>
>    }).then(function(result) {
>
>      console.log(result); // 2
>      return result * 3;
>
>    }).then(function(result) {
>
>      console.log(result); // 6
>      return result * 4;
>
>   });
> ```
> In the above handlers, the result is passed to the chain of `.then()` handlers with the below work flow,
> 1. The initial promise resolves in 1 second,
> 2. After that `.then` handler is called by logging the result(1) and then return a promise with the value of result * 2.
> 3. After that the value passed to the next `.then` handler by logging the result(2) and return a promise with result * 3.
> 4. Finally the value passed to the last `.then` handler by logging the result(6) and return a promise with result * 4.
</details>

<details>
<summary>20. What for async/await keywords are used?</summary>

> #### Answer:
> The word <code>async</code> before a function means one simple thing: a function always returns a promise. Even If a function actually returns a non-promise value, prepending the function definition with the <code>async</code> keyword directs Javascript to automatically wrap that value in a resolved promise.
> ```javascript
> async function f() {
>   return 1;
> }
>
> f().then(alert); // 1
> ```
> The keyword <code>await</code>makes JavaScript wait until that promise settles and returns its result.
> ```javascript
> async function f() {
>   let promise = new Promise((resolve, reject) => {
>     setTimeout(() => resolve("done!"), 1000)
>   });
>   // works only inside async functions
>   let result = await promise; // wait till the promise resolves (*)
>   alert(result); // "done!"
> }
>
> f();
> ```
> The function execution “pauses” at the line (*) and resumes when the promise settles, with result becoming its result.
> So the code above shows “done!” in one second.


</details>

<details>
<summary>21. What's in the console? What if it's strict mode?

```javascript
(function() {
    var x = y = 10;
})();

console.log(y);
console.log(x);
```
</summary>

> #### Answer:
> ```javascript
> 10
> Uncaught ReferenceError: x is not defined
>
> ```
> Using strict mode:
>
> ```javascript
> Uncaught ReferenceError: y is not defined
> ```

</details>

<details>
<summary>22. What's in the console?

```javascript
function fun() {
    console.log(a);
    console.log(inner());

    var a = 5;
    function inner() {
        return a + 5;
    }
    console.log(inner());
}

fun()
```
</summary>

> #### Answer:
> ```javascript
> undefined
> NaN
> 10
> ```

</details>

<details>
<summary>23. What's in the console? Change the function context to get the different thing in console.

```javascript
var secretNumber = 10;
var obj = {
    secretNumber: 100,
    inner: {
        secretNumber: 1000,
        printNumber: function() {
            console.log(this.secretNumber);
        }
    }
}

obj.inner.printNumber();

var printNumber = obj.inner.printNumber;
printNumber();
```
</summary>

> #### Answer:
> ```javascript
> 1000
> 10
>```
> Change the context:
> ```javascript
> var newPrintNumber = obj.inner.printNumber.bind(obj);
> newPrintNumber();
> 100
> ```

</details>

<details>
<summary>24. What's in the console?

```javascript
function print1234() {
    console.log(1);
    setTimeout(() => console.log(2), 100);
    setTimeout(() => console.log(3), 0);
    console.log(4);
}

print1234();
```
</summary>

> #### Answer:
> ```javascript
> 1
> 4
> 3
> 2
>```

</details>

<details>
<summary>25. What's in the console? Change it to be the way we need.

```javascript
for (var i = 1; i <= 5; i++) {
    setTimeout(() => {
        console.log(i);
    }, 0);
}
```

</summary>

> #### Answer:
> ```javascript
> 6
> 6
> 6
> 6
> 6
> ```
> Fix:
> ```javascript
> for (var i = 1; i <= 5; i++) {
> (function(i){
>   setTimeout(() => {
>     console.log(i);
>   }, 0)
>  })(i);
> }
> 1
> 2
> 3
> 4
> 5
> ```

</details>

<details>
<summary>26. What's in the console?

``` javascript
var obj = {
    a: 200
};

(function(obj) {
    obj = {
        a: 400
    };

})(obj);

console.log(obj.a);
```
</summary>

> #### Answer:
> ```javascript
> 200
> ```

</details>

<details>
<summary>27. What's in the console?

``` javascript
var i = 10;
var array = [];

while (i--) {
    (function (i) {
        var i = i;
        array.push(function() {
            return i + i;
        });
    })(i);
}

console.log([
    array[0](),
    array[1](),
])
```
</summary>

> #### Answer:
> ```javascript
> 18
> 16
> ```

</details>

<details>
<summary>28. What's in the console?

``` javascript
(function () {
    test();

    test = function () {
        console.log('a')
    };
})();

function test() {
    console.log('b')
}

test();
```
</summary>

> #### Answer:
> ```javascript
> b
> a
> ```

</details>

<details>
<summary>29. What's in the console?

``` javascript
var a = -1;

function someFunc() {
    if (false) {
        var a = 1;
    } else {
        var b = 2;
    }

    console.log(b);
    console.log(a);
}

someFunc();
```
</summary>

> #### Answer:
> ```javascript
>2
>undefined
> ```

</details>

<details>
<summary>30. What's in the console?

``` javascript
var a = 1;

function getFunc() {
    var a = 2;
    var func = new Function('', 'alert(a)');
    return func;
}

getFunc()();
```
</summary>

> #### Answer:
> ```javascript
>1
> ```

</details>

<details>
<summary>31. What's in the console?

``` javascript
var counter = 5;

var add = (function () {
    var counter = 0;
    return function () {
        return counter += 1;
    }
})();

add();
add();

console.log(add());
```
</summary>

>#### Answer:
> ```javascript
>3
> ```

</details>

<details>
<summary>32. What's in the console?

``` javascript
function shooterBuilder() {
    let shooters = [];

    for (let i = 0; i < 10; i++) {
        shooters.push(function () {
            console.log(i);
        });
    }

    return shooters;
}

var x = shooterBuilder();
x[0]();
x[5]();
```
</summary>

>#### Answer:
> ```javascript
>0
>5
> ```

</details>