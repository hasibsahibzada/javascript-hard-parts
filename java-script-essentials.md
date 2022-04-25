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

```
var foo = "bar";

function bar() {

    var foo = "baz";

    function baz(foo) {
        foo = "bam";
        bam = "yay";
    }

    baz();
}

bar();
foo; // bar
bam; // yay
baz();  // error
```
The compiler will start from line `30`and ask > Hey `Global scope` I have a declaration for variable named `foo` could you please declared it for me. 
## What is the difference between `var` and `let`?
var and let are both used for variable declaration in javascript but the difference between them is that var is function scoped and let is block scoped. It can be said that a variable declared with var is defined throughout the program as compared to let.
## What is Hoisting ? 
Is a process of taking all local and global variable and function declarations and move them on top.
In the example bellow variable `a`is declared and put in the top by javascript so that the console log could access it.
Only variable declarations are hoisted not initialization of it.
```
console.log(a);  // this will still show undefined value (Meaning the variable a is declared but has no value in it)
const a = 'test';
```

```
somevariable = 'test';
console.log(somevariable); // outputs test even when the variable is declared after it is initialized	
var somevariable;
```

```
testFunction();  // Outputs " Hello world! " even when the function is declared after calling

function testFunction(){ 
  console.log(" Hello world! ");
}
```
### How to get rid of Hoisting ?
Hoisting process makes the performance slower if there are too many declarations happening, and is a bad practice because it is unpredictable.
- Best way is to avoid `var` and instead use `const or let` and for functions best to use un-named functions and assigne it to a variable and then call it.
- Run the javascript in strict mode `"use strict"` on top of the code.

