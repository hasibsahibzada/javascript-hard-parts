 # Javascript Essentials.
 
 
## What is javascript ?
- Definition 
  - Scripting language. (language for a runtime system) Scripting languages are usually interpreted at runtime rather than compiled).Eg: Bash, python, lisp etc.
  - object-oriented computer programming language
  - Bring intereactivity to web pages.
  - Access document object model (DOM) to manipulate/change/remove values.
  - Access to browser object model (BOM).
  
- Primitive data types. It can store only a single value. To check the type of a variable simply `typeof [VAR_NAME]`
  - Undefined: When a variable is declared but not assigned.
  - Null: It represents a non-existent or a invalid value.
  - Boolean: It represents a logical entity (TRUE, FALSE)
  - String: It represents a series of characters and is written with quotes. Can be represented using a single or a double quote.
  - Symbol: in the ES6 version of javascript. It is used to store an anonymous and unique value. `var symbol1 = Symbol('symbol');`
  - Number: It represents a number and can be written with or without decimals.
  - BigInt: BigInt: store numbers which are above the limitation of the Number data type. 

- Non-primitive datatypes. Store multiple and complex values. The data type is called Object
  - Object: Key pair values. `a = {test: '123', b: 'hi'} `
  - Array: ordered list of elements. `a = [1, 2, 3]`

## What happens in Javascript compilation phase ?
This is where all variables and functions get declared.
Lets look at this example bellow.

```javascript
1 var foo = "bar";
2
3 function bar() {
4
5    var foo = "baz";
6
7    function baz(foo) {
8        foo = "bam";
9        bam = "yay";
10    }
11
12    baz();
13 }
14
15 bar();
16 foo; // bar
17 bam; // yay
18 baz();  // error
```
The compiler will start from line `1`and 
- ask > Hey `Global scope` I have a declaration for variable named `foo` could you please declared it for me.
- move to line `3` hey `Global scope` I have a declaration for function `bar` could you please declared it for me.
- Move inside the `bar` function, move to line 5 and ask hey `Local scope of bar` I have a declaration for variable `foo` could you please declared it for me.
- move to line 7, declare the function of baz, move in it declare variable foo locally if it context of `baz scope`.
- skip line 8, 9 and 12 because they are not declarations.
## What is the difference between `var` and `let`?
var and let are both used for variable declaration in javascript but the difference between them is that var is function scoped and let is block scoped. It can be said that a variable declared with var is defined throughout the program as compared to let.

## What happens in Javascript execution phase ?
This phase happens after the compilation phase where it declares the variables. This is where the assignments of values happens from `RHS`(Right hand side) to `LHS`(Left hand side).
- On line one, Hey `Global scope` I need the `LHS` reference of variable named `foo` ever heared of it, answer yes here it is and the assignments happens. 
## What is Hoisting ? 
Is a process of taking all local and global variable and function declarations and move them on top.
In the example bellow variable `a`is declared and put in the top by javascript so that the console log could access it.
Only variable declarations are hoisted not initialization of it.
```javascript
console.log(a);  // this will still show undefined value (Meaning the variable a is declared but has no value in it)
const a = 'test';
```

```javascript
somevariable = 'test';
console.log(somevariable); // outputs test even when the variable is declared after it is initialized	
var somevariable;
```

```javascript
testFunction();  // Outputs " Hello world! " even when the function is declared after calling

function testFunction(){ 
  console.log(" Hello world! ");
}
```
### How to get rid of Hoisting ?
Hoisting process makes the performance slower if there are too many declarations happening, and is a bad practice because it is unpredictable.
- Best way is to avoid `var` and instead use `const or let` and for functions best to use un-named functions and assigne it to a variable and then call it.
- Run the javascript in strict mode `"use strict"` on top of the code.

