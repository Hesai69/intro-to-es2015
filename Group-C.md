


Array.prototype.keys()
The keys() method returns a new Array Iterator that contains the keys for each index in the array. Objects in the array iterator accessed by .next();

Ex:
var arr = ["a", , "c"];
var sparseKeys = Object.keys(arr);
var denseKeys = [...arr.keys()]; //what is ...arr syntax
var iterator = arr.keys();
console.log(sparseKeys); // ['0', '2']
console.log(denseKeys);  // [0, 1, 2]
console.log(iterator.next()) // {value: 0, done: false}
console.log(iterator.next()) // {value: 1, done: false}
console.log(iterator.next()) // {value: 2, done: false}
console.log(iterator.next()) // {value: undefined, done: true}



String.prototype.endsWith()
Determines whether a string ends with the characters passed into the function, returning true or false accordingly. 
Ex:

var str = 'Hello this is a test string!'
console.log(str.endsWith('string!')) //true

consoe.log(str.endsWith('g!')) //true

console.log(str.endsWith('Hello', 5)) //true

console.log(str.endsWith('Hello ', 6)) //true [because of the space after the o]

console.log(str.endsWith('Hello ', 5)) //false [ because of the space after the o]




Array.prototype.copyWithin()
- The copyWithin() method shallow copies part of an array to another location in the same array and returns it,
    without modifying its size. (elements get poppped)

  Ex:
  ["alpha", "bravo", "charlie", "delta"].copyWithin(2, 0);

  // results in ["alpha", "bravo", "alpha", "bravo"]

    [1, 2, 3, 4, 5].copyWithin(-2); 
    // [1, 2, 3, 1, 2]
  
  Syntax
  arr.copyWithin(target)
  arr.copyWithin(target, start)
  arr.copyWithin(target, start, end)

More ex:
["alpha", "bravo", "charlie", "delta", "echo", "foxtrot"].copyWithin(1)
// ["alpha", "alpha", "bravo", "charlie", "delta", "echo"]

["alpha", "bravo", "charlie", "delta", "echo", "foxtrot"].copyWithin(2)
// ["alpha", "bravo", "alpha", "bravo", "charlie", "delta"]

["alpha", "bravo", "charlie", "delta", "echo", "foxtrot"].copyWithin(2, 1);
["alpha", "bravo", "bravo", "charlie", "delta", "echo"]



target: zero based index at which to start copying elements to
start: zero based index which specifies where to start copying elements from

promises
- reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise
- The Promise object is used for asynchronous computations. A Promise represents a value which may be available now, or in the future, or never.
- Syntax: new Promise( /* executor */ function(resolve, reject) { ... } );

- reference: https://spring.io/understanding/javascript-promises
    Why use Promise?
- Promises provide a simpler alternative for executing, composing, and managing asynchronous operations when compared
    to traditional callback-based approaches.

Promise States:
- A Promise can be in one of 3 states:
    Pending - the promise's outcome hasn't yet been determined, becuase the asynch operation that will produce the result hasn't completed yet 
    Fulfilled - the asynch operation has completed, and the promise has a value.
    Rejected - the asynch operation failed, and the promise will never be fulfilled. In the rejected state, a promise has a reason that indicates why the operation failed.


Example:
var greetingPromise = sayHello();
greetingPromise.then(function (greeting) {
    console.log(greeting);    // 'hello world’
});

Allows asynchronous operations to be chained together, so that they are guaranteed to happen in the correct order.
For example, if addExclamation is asynchronous (possibly needing to access another web service) and returns a promise for the new greeting
Example: 
var greetingPromise = sayHello();
greetingPromise
    .then(addExclamation)
    .then(function (greeting) {
        console.log(greeting);    // 'hello world!!!!’
    });






Destructuring
- Destructuring allows binding using pattern matching, with support for matching arrays and objects. 
    Destructuring is fail-soft, similar to standard object lookup foo["bar"], producing undefined values when not found.
- The destructuring assignment syntax is a JavaScript expression 
    that makes it possible to extract data from arrays or objects into distinct variables.  
  
  Ex:
  
  var x = [1, 2, 3, 4, 5];
    var [y, z] = x;
    console.log(y); // 1
    console.log(z); // 2
  
  
  Syntax
  var a, b, rest;
  [a, b] = [10, 20];
  console.log(a); // 10
  console.log(b); // 20

  [a, b, ...rest] = [10, 20, 30, 40, 50];
  console.log(a); // 10
  console.log(b); // 20
  console.log(rest); // [30, 40, 50]

  ({a, b} = {a:10, b:20});
  console.log(a); // 10
  console.log(b); // 20

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  // 
