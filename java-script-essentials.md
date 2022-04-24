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

## What is Hoisting ? 
Is a process of taking all local and global variable and function declarations and move them on top.
In the example bellow variable `a`is declared and put in the top by javascript so that the console log could access it.
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
