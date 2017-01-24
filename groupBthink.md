

Group B

- [Object.assign()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)
    - MARGIE :

    The Object.assign() method is used to copy the values of all
    enumerable owned properties from one or more source objects to a target
    object. It will return the target object.

      Enumerable means: able to be counted by one-to-one correspondence
    		with the set of all positive integers.

    Syntax: Object.assign(target, ...sources)

    	- Source overrides the target if the source, and target have same
        key

		Description: properties in the target object will be overwritten by
      properties in the sources if they have the same key. Later sources'
      properteis will similarily overwrite earlier ones.

    The Object.assign() method only copies enumerable and own properties
    	from a source object to a target object. It uses [[Get]] on the
      source and [[Set]] on the target, so it will invoke getters and setters.

        MEANING it assigns properties vs. just copying or defining new props.

        Object.getOwnPropertyDescription() and Object.defineProperty() should
        be used instead.

    examples:
    		Cloning an object:
            var obj = { a: 1}
            var copy = Object.assign( {}, obj);
            console.log(copy); // { a: 1 }

         Merging an object:
         		var o1 = { a: 1 };
            var o2 = { b: 2 };
            var o3 = { c: 3 };

          	var obj = Object.assign(o1, o2, o3); //{ a:1, b:2, c:3 }

    Properties on the prototype chain and non-enumerable props cannot
        be copied. 'Prototype Chain' means each obj has an 'internal link'
        to another obj called it's prototype.

    Ex:
    	var obj = Object.create({ foo: 1 }, {
      	bar: {
        			value: 2,
              }
        baz: {
        			value: 3,
              enumerable: true
             }
        });

        var copy: Object.assign(), obj);
        console.log(copy); // {baz: 3 }






- [Array.prototype.fill()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)
    - Fills all the elements of an array from a start index to an end index with a static value
    - Mutable method, will change this object itself, and return it, not just return a copy of it

    SYNTAX ====================
    arr.fill(value)
    arr.fill(value, start)
    arr.fill(value, start, end)

    EXAMPLE ===================
    ```javascript
    var numbers = [1, 2, 3]
    numbers.fill(1);

    // results in [1, 1, 1]
    ```



- [template strings](https://github.com/lukehoban/es6features#template-strings)
    - string literals allowing embedded expressions
    - enclosed by back-ticks
    - can be multi-line

    - can contain place holders --> ${javascript expressions}
        - expressions in the place holders and the text between them get passed to a function.
        - The default function just concatenates the parts into a single string

    - tagged template literals
        - Tags allow you to parse template literals with a function.
            - The first argument of a tag function contains an array of string literals
            - The remaining arguments are related to the expressions.
            - functions can return the manipulated string or it can return something completely different

    - String.raw() method can be called on the first argument of tagged template literals or can be called on a string to show the raw string




- [Array.prototype.entries()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries)
    ==> returns new array iterator object that contains idx# and its value in array.
			ex:
      ```javascript
        var a = ['a', 'b', 'c'];
        var iterator = a.entries();

        console.log(iterator.next().value); // [0, 'a']
        console.log(iterator.next().value); // [1, 'b']
        console.log(iterator.next().value); // [2, 'c']
      ```



/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

- [modules](https://github.com/lukehoban/es6features#modules)
    - mimi

      “Good authors divide their books into chapters and sections; good programmers divide their programs into modules….
      Good modules, however, are highly self-contained with distinct functionality, allowing them to be shuffled, removed,
      or added as necessary, without disrupting the system as a whole.”

    Modules -  Small units of independent, reusable code.
    JavaScript modules export a value, rather than define a type.
    Most JavaScript modules export an object literal, a function, or a constructor.

    Benefits of Modules:

    - Maintainability - Updating a single module is much easier when the module is decoupled from other pieces of code.
    - NameSpacing -  modules allow us to avoid namespace pollution by creating a private space for our variables.
    - Reusability

     Two de facto module formats have evolved until ECMA Script 2016 releases module compatability:

       1. Asynchronous Module Definition (AMD) is the most popular for client-side code,
       2. Node.js modules (an extension to CommonJS Modules/1.1) is the leading pattern in server-side environments.


    ECMA SCRIPT 2016 RELEASED THE FOLLOWING FOR MODULES:

    Browsers don’t feature any kind of module system.
    You always need a build step or a loader for your AMD or CommonJS modules.
    Tools to handle this include RequireJS, Browserify and Webpack.

	The ES6 specification includes both a new syntax and a loader mechanism for modules.
	Modules are designed around the `export` and `import` keywords.
  Let’s examine an example with two modules right away:

 The import statement is used to import functions, objects or primitives that have been exported from an external module, another script, etc.
     - to import the module as a whole, the `*` wildcard can be used, combined with the `as` keyword to give the module a local name.
     - import statements are synchronous, but the module code doesn’t execute until all dependencies have loaded.
     Syntax: [import defaultMember from "module-name";]

	If you want a visual representation:
  https://paper.dropbox.com/doc/ECMA-Script-2015-UwI1MGWUeTbVO0glTElE5
