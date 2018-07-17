---
layout: post
title:      "Javascript's Confusing Scope, Variables, and Functions"
date:       2018-07-17 05:55:53 -0400
permalink:  javascripts_confusing_scope_variables_and_functions
---


One of the more difficult parts of javascript is how scope works. The way variable assignments are handled can sometimes lead to some confusing behavior. Today we're going to aim to clear up some of the confusion.

## What is scope

Scope in Javascript is essentially *where* something is available. For instance, variables are available in the scope in which they are declared.
```
let v1 = 'this is in global scope'
function doSomething() {
  let v2 = "this is inside of doSomething's scope"
}

v2 // <-- ReferenceError: v2 is not defined
```
Here we declare `v1` in the global scope, which basically means it's available anywhere in our program. When we create the function `doSomething`, a scope specific to the function is also created. `v2` is defined inside the scope and is usable there. However, if we try to access it outside of the function, it's undefined.

## var

`var` is the original way to declare variables in javascript. The introduction of `let` and `const` in ES2015 have certainly decreased its usefulness, but it's still important to understand how it works.

Variables declared with `var` are *function-scoped* but they are not *block-scoped*. This can lead to some confusing behavior.

```
function hey() { 
  var myVar = 'hi'
}

myVar; // ReferenceError: myVar is not defined

if (true) {
  var myOtherVar = 'greetings'
}

myOtherVar; // 'greetings'

```
Here we see that `myVar` is not available outside of the `hey()` scope, but `myOtherVar` **is** available outside of the `if` statement scope.  `var` can be used to re-declare a variable in a separate scope as well:
```
var i = 'outside'

function whereIsI() {
  var i = 'inside'
  console.log(i)
}

whereIsI(); // 'inside'
```
`i` is declared and assigned twice here; once in the global scope, where it's assigned 'outside', and once in the function scope, where it's assigned 'inside'. Essentially, inside the function scope, the global `i` is overwritten. When the function is called, it uses the instance from inside of its scope.

## let and const
As we discussed before, these two declarations were added in ES2015. They help alleviate some of the potentially strange behavior `var` can lead to. They both feature *function* scoping, just like `var`. Unlike `var`, they're both also *block-scoped*. This make variables act a little more consistently. Lets revisit the example above.
```
function hey() { 
  let myVar = 'hi'
}

myVar; // still not defined...

if (true) {
  const myOtherVar = 'greetings'
}

myOtherVar; // now I'm undefined, too!
```
When we use `let` and `const` in place of `var`, both variables are only available in the scope where they're defined. 
What differentiates `let` and `const` is the ability to reassign variables. `let` variables can be changed, `const` variables can't, therefore they're *const*ant. If a constant points to an object or array, the values contained can be changed, but not what the variable itself refers to. 

## Hoisting
Another source of confusion in Javascript-land is the term known as "hoisting". To understand this, we need to explore how Javascript runs. The Javascript engine goes through our code from top to bottom in two main phases: compilation and execution. During compilation, the engine reads through the code, and sets up all the functions and variables, but doesn't execute anything yet. Memory is set aside for all the functions and variables, and as such they are *declared*. However, the variables aren't yet *assigned* until the execution phase. 
```
myFunction(); // 'my function!'

function myFunction() {
  console.log('my function!')
}
```
This doesn't look like it should work, how can we invoke a function before we declare it? As we discussed above, functions are declared in the compilation phase, and are invoked during the execution phase. This makes it seem like the functions are *hoisted* to the top of our code...sort of like they're available to us before we've even defined them!

Variables can be victims of hoisting as well, but in a different way. In the compilation phase, memory is set aside for the functions, and they're available when the execution phase. Memory is also set aside for variables, and they're declared before execution begins, but they aren't yet *assigned*. Javascript knows the variable exists, but doesn't know its value until the execution phase.
```
x; // undefined

var x = "variable"
```
`x` does exist, we don't get a reference error, but it doesn't have an assigned value. Its sort of like the Javascript engine splits the declaration and assignment. The code above is interpreted as:
```
var x;
x; // exists, but still undefined
x = "variable" // now it has an assigned value
```
`let` and `const` again add some functionality to help deal with this confusing behavior. Trying to access a variable defined with these will result in an `Uncaught Reference Error`, rather than continuing to execute the code with unassigned variables. At least it lets us know that its breaking.
```
x; // now throws a Reference Error

const x = "variable"
```

## Functions in Javascript

Javascript functions are known as *first-class citizens* in the programming world. As such, there are many different ways to handle them. They can be passed around to other functions as arguments, be placed inside other objects (methods), and assigned to variables, among other things. 
We can have *function declarations*, where we assign the function a name and add code in the block:
```
function doSomething() {
  console.log('i did something')
}```
Nothing is returned or executed here, the function is just stored in memory. Later, we can call the function with `doSomething()`, and 'i did something' will be logged. If the `function` keyword is anywhere but the beginning of the line, it's then known as a *function expression*, and the function itself is returned. We can use this to assign the function to a variable.
```
const doSomethingElse = function {
  console.log('i did something')
}```
The end result is the same as the example above, except that the second example wouldn't be hoisted. Function expressions aren't. In other words, you can call `doSomething()` anywhere in the code, but `doSomethingElse` is only available below the declaration.

Function declarations are required to have a name. It wouldn't make much sense to declare a function without a way to refer back to it later. You'll also get an error if you try. 
```
function() {
  console.log('never gonna get logged')
} //SyntaxError: Unexpected token (1:8)```

Function expressions aren't required to have a name, as they're either invoked right away or sent somewhere else via assignment or callback.
```
$('#myButton').on('click', function() { // no name for this function
  console.log('you clicked me!')
}```
These are known as anonymous functions, as they don't have a name. 

We've covered a lot here, and hopefully this helps to clear up some of the confusion around Javascript!


