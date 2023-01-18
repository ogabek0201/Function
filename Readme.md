# <center>JavaScript lesson#3</center>

<p align="center">

<img src="https://img.shields.io/badge/Made%20by-Ogabek-yellow" >

<img src="https://img.shields.io/badge/Function-Declaration-brown">

<img src="https://img.shields.io/badge/Function-Expression-brown">

<img src="https://img.shields.io/badge/Learn-Javascript-black">

</p>

---

#### __<center>A function is a block of code that performs a specific task.</center>__

---

# _<center>Function</center>_

### Declaring a Function

* __The syntax to declare a function is:__

    ```js
    function nameOfFunction (argument) {
    // function body
    }
    ```

  * __A function is declared using the function keyword.__
  * __The basic rules of naming a function are similar to naming a variable. It is better to write a descriptive name for your function.__
  * __The body of function is written within {}.__

    ```js
    function hello(){
        //body
        console.log("Hello world!");
    }
    ```

### Calling a function

`In the above program, we have declared a function named hello(). To use that function, we need to call it.`

_Here's how you can call the above greet() function._

```js
//call
hello();//Hello world!
```

### Function Parameters

_A function can also be declared with parameters. A parameter is a value that is passed when declaring a function._

```js
function helloToTheUser(name){
    console.log(`Hello ${name}!`);
}

helloToTheUser('ogabek');//Hello ogabek!
```

`In the above program, the helloToTheUser function is declared with a name parameter. The user is prompted to enter a name. Then when the function is called, an argument is passed into the function.`

```go
Note: When a value is passed when declaring a function, it is called parameter. And when the function is called, the value passed is called argument.
```

__Notice that you can call a function as many times as you want. You can write one function and then call it multiple times with different arguments.__

### Function Return

_The return statement can be used to return the value to a function call._

_The return statement denotes that the function has ended. Any code after return is not executed._

_If nothing is returned, the function returns an undefined value_

```js
function add(a, b) {
    return a + b;
}
console.log(`The sum is ${add(5,6)}`);//The sum is 11

```

### Function Expressions

`In Javascript, functions can also be defined as expressions. For example,`

```js
let a= function (num){return num+5}
console.log(a(5));//10
```

__In the above program, variable a is used to store the function. Here the function is treated as an expression. And the function is called using the variable name.__

_The function above is called an anonymous function._

---

# _<center>Scope</center>_

```
Scope refers to the availability of variables and functions in certain parts of the code.
```

* __In JavaScript, a variable has two types of scope:__
  * _Global Scope_
  * _Local Scope_

### Global Scope

```
A variable declared at the top of a program or outside of a function is considered a global scope variable.
```

### __global scope variable.__

```js
let a=salom
function hello(){
    console.log(a);
}
hello();//salom
```

_Variable a is declared at the top of a program and is a global variable. It means the variable a can be used anywhere in the program._

__The value of a global variable can be changed inside a function.__

```js
let a=salom
function hello(){
    a=5

}
console.log(a);//salom
hello();
console.log();//5
```

_Variable a is a global variable. The value of a is salom. Then the variable a is accessed inside a function and the value changes to 5._

__Hence, the value of a changes after changing it inside the function.__

```
In JavaScript, a variable can also be used without declaring it. If a variable is used without declaring it, that variable automatically becomes a global variable.
```

~~var~~=10

```js
a=10
console.log(a);//10

```

### ↑ variable a is a global variable

_If the variable was declared using let a = 10, the program would throw an error._

### Local Scope

```
A variable can also have a local scope, i.e it can only be accessed within a function.
```

```js
let a=10
function addTwoNum() {
    let b=5
    console.log(a+b);
}
addTwoNum();//15
console.log(a+b);//error b is not defined
```

__a__ is a global variable and variable __b__ is a local variable. The variable b can be accessed only inside the function __addTwoNum__. Hence, when we try to access variable b outside of the function, an error occurs

---

# _<center>Hoisting</center>_

 __Hoisting__ in JavaScript is a behavior in which a function or a variable can be used before declaration.

### Variable Hoisting

```
In terms of variables and constants, keyword var is hoisted and let and const does not allow hoisting.
```

```js
a = 5;
console.log(a);//5
```

_variable __a__ is used before declaring it. And the program works and displays the output __5__ Since it automatically assigns the variable __var__._

#### However in JavaScript, initializations are not hoisted

```js
console.log(a);//undefined
var a=5
```

_Only the declaration is moved to the memory in the compile phase. Hence, the value of variable a is undefined because a is printed without initializing it._

~~~
In hoisting, the variable declaration is only accessible to the immediate scope.
~~~

#### If a variable is used with the let keyword, that variable is not hoisted

```js
a = 5;
console.log(a);
let a; // error
```

`Uncaught ReferenceError: Cannot access 'a' before initialization`

_While using __let__, the variable must be declared first._

#### Function Hoisting

```A function can be called before declaring it```

```js
hello();//hello world!

function hello() {
    console.log('hello world!');
}
```

_function_ __hello__ is called before declaring it and the program shows the output. This is due to __hoisting__.

### However, when a function is used as an expression, an error occurs because only declarations are hoisted

```js
hello();//hello is not defined

let hello = function () {
    console.log('hello world!');
}
```

`Uncaught ReferenceError: greet is not defined`

---