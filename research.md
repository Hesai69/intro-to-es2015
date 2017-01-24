[-------------------------------------------]
[               Default + Rest + Spread                         ]
[-------------------------------------------]

(Works in Chrome)
 
Default function parameters allow formal parameters to be initialized with default values if no value or undefined is passed.
``` 
  function defaultFunc(x, y="a") {
    // y is 12 if not passed (or passed as undefined)
    return x + y;
  }
  defaultFunc(5) // displays "5a"
```

The rest parameter syntax allows us to represent an indefinite number of arguments as an array.
```
  function restFunc(x, ...y) {
  // y is an Array
  return x * y.length;
    }

    restFunc(1, "hello", "hello", 1) //3
```

The spread syntax allows an expression to be expanded in places where multiple arguments (for function calls)
or multiple elements (for array literals) or multiple variables  (for destructuring assignment) are expected.  
```
  function spreadFunc(x, y, z) {
    return x + y + z;
  }
  // Pass each elem of array as argument
  spreadFunc(...[11,11,11]) // 33
```

[-------------------------------------------]
[   Difference between for...of and for...in    ]
[-------------------------------------------]

The for...in loop will iterate over all enumerable properties of an object.

The for...of syntax is specific to collections, rather than all objects. It will iterate in this manner over the elements of any collection that has a [Symbol.iterator] property.

The following example shows the difference between a for...of loop and a for...in loop.

Object.prototype.objCustom = function () {}; 
Array.prototype.arrCustom = function () {};

let iterable = [3, 5, 7];
iterable.foo = "hello";

for (let i in iterable) {
  console.log(i); // logs 0, 1, 2, "foo", "arrCustom", "objCustom"
}

for (let i of iterable) {
  console.log(i); // logs 3, 5, 7
}

[-------------------------------------------]
[                   Array.prototype.find()                      ]
[-------------------------------------------]

Syntax
arr.find(callback[, thisArg])

Return value

A value in the array if an element passes the test; otherwise, undefined.

[-------------------------------------------]
[           String.prototype.startsWith()                   ]
[-------------------------------------------]

The startsWith() method determines whether a string begins with the characters of another string, returning true or false as appropriate.

Syntax
str.startsWith(searchString[, position])

var str = 'To be, or not to be, that is the question.';

console.log(str.startsWith('To be'));         // true
console.log(str.startsWith('not to be'));     // false
console.log(str.startsWith('not to be', 10)); // true because optional position = 10, so starts searching at 'not to be'

[-------------------------------------------]
[                               Array.of()                                  ]
[-------------------------------------------]

The Array.of() method creates a new Array instance with a variable number of arguments, regardless of number or type of the arguments.

Syntax
Array.of(element0[, element1[, ...[, elementN]]])

Parameters

elementN
Elements of which to create the array.

Return value
A new Array instance.

Array.of(7);       // [7] 
Array.of(1, 2, 3); // [1, 2, 3]

COMPARED TO USING ARRAY METHOD

Array(7);          // [ , , , , , , ]
Array(1, 2, 3);    // [1, 2, 3]



