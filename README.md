javascript-cookbook
===================

*Get kickstarted with JavaScript*

## Contents

1. [Overview] (#overview)
2. [Types & Objects] (#types--objects)
3. [Arrays] (#arrays)
4. [Operators] (#operators)
4. [Condition Expression & Loops] (#condition-expression-loops)
5. [Functions] (#functions)
6. [Namespaces] (#namespaces)
8. [Regular Expressions] (#regular-expression)
7. [Prototyping] (#prototyping)
9. [Further Study and resources] (#further-study)

## Overview

**JavaScript** (often called as JS) is a dynamic, prototype-based, lightweight scripting language and features first-class functions. It is commonly used as a scripting language for Web pages and is supported by all modern browsers. JavaScript was formalized in the ECMAScript language standard and supports Object-Oriented, functional and imperative programming styles. 

JS can be used on Client-side, as a part of the web browser which allows DOM manipulation, asynchronous communication and user interaction. On the Server-side, JavaScript applications can perform file operations, communication with database and many other server-side tasks.

The syntax of JS was hugely influenced by C and Java, although it has different semantics and is greatly unrelated to the two. JavaScript contradicts with Java in its runtime system and is not statically typed.

## Types & Objects

The ECMAScript specification defines six standard data types as follows,

+ `String`
+ `Number`
+ `Boolean`
+ `null`
+ `undefined`
+ `Object`


**String**: Alike Java, Strings in JavaScript are immutable. Strings once created cannot be modified, however we can create a new string based on an operation to modify the original string. 

Strings can be created by assigning the string to a variable enclosed within single quotes.

```javascript
var a = 'Hello World';
console.log(a); // Displays 'Hello World'
``` 

We can also create Strings by using the String() constructor.

```javacript
var a = new String('Hello World');
console.log(a); // Displays 'Hello World'
```

JS provides a handful of methods to work with Strings.

+ `charAt(index)` - Returns the character at the position specified by the `index`

+ `indexOf(String, Number)` - Returns the index/location of the leftmost occurence of the `String` after `Number`. Returns `-1` if no occurence of the `String` is found

+ `concat(String)` - Returns the concatenated `this` String with the `String` argument

+ `replace(String, String)` - Returns a String by replacing the first argument `String` with the second argument `String`

+ `slice(Number, Number)` - Returns a substring of `this` String starting from index specified by first argument `Number` to one character before the second argument `Number`
 
+ `match(regex)` - Returns an array of Strings or a String that matches against the `regex`

+ `search(regex)` - Returns the index/location of the leftmost occurence of `this` string with the `regex`. Returns `-1` if no occurence of the `regex` is found

+ `trim()` - Returns a string with Whitespace removed from both the ends of `this` String

+ `split(String/regex)` - Returns an array of Strings by splitting `this` string into substrings separated by the `String/regex`

+ `toLowerCase()` - Returns a string by converting `this` string to Lowercase

+ `toUpperCase()` - Returns a string by converting `this` string to Uppercase

+ `toString()` - Returns the string representation of `this` Object

```javascript
var bar = 'Hello World';

// concat() method 
var foo = bar.concat(' Foo');
console.log(foo); // Displays 'Hello World Foo'
console.log(foo + 'bar'); // We can also use + operator for concatenation.


// charAt() method
console.log(bar.charAt(1)); // Displays 'e'
console.log(bar.charAt(7)); // Displays 'o'

// indexOf() method
console.log(bar.indexOf('Wor',1)); // Displays 6

// replace() method
console.log(bar.replace('Wor','Go')); // Displays 'Hello Gold'

// split() method
console.log(bar.split('o')); // Displays the array ["Hell", " W", "rld"]

// toLowerCase() method
console.log(bar.toLowerCase()); // Displays 'hello world'

// toUpperCase() method
console.log(bar.toUpperCase()); // Displays 'HELLO WORLD'


```

**Note**: String Object has a property called `length` which can be used to return the length of `this` string.

**Number**: Numbers in JavaScript can be created by simply assigning the number to the variable or by using the Number constructor. The Number instance inherits the `Number.prototype` property which provides the following methods,

+ `toExponential()` - Returns a string representation of `this` Number in Exponential form
+ `toFixed(len)` - Returns a string representation of `this` Number in Fixed Point notation upto the `len` (automatically rounds off)
+ `toPrecision(precision)` - Returns a string representation of `this` Number upto the specified `precision`
+ `toString()` - Returns a string representation of `this` Number

```javascript

var num = 2.489;

// toExponential() method
console.log(num.toExponential()); // Displays '2.489e+0'

// toFixed() method
console.log(num.toFixed()); // Displays '2'
console.log(num.toFixed(2)); // Displays '2.49'

// toPrecision() method
console.log(num.toPrecision(2)); // Displays '2.5'

// toString() method
console.log(num.toString()); // Displays '2.489'


```

**Boolean**: Booleans like in any other languages are used for evaluation of conditional expressions. Booleans in JS can be used by using the boolean values `true` and `false`. We can also use the `Boolean` constructor to convert a non-Boolean value to true or false.

```javascript

var bar = true; // bar contains the boolean true

var foo = new Boolean(false); // foo contains the boolean false

```

**Note**: You must be careful while converting a non boolean value to boolean. Strings and Numbers (except 0 and -0) are converted to true, whereas 0, -0, null, false, NaN, undefined, or an empty string are treated as false.

```javascript

var bar = new Boolean('false'); // bar contains true since 'false' is a String

var foo = new Boolean(0); // foo contains false since the argument of the Boolean constructor is 0

if(some String or true) { 
  
    // Block is evaluated

}

if(0 or -0 or null or false or undefined) {
    
    // Block is not evaluated
    
}

```

Since the major purpose of Boolean is for evaluation for conditional expression, it doesn't contain any native methods. However Boolean inherits two methods from `Object` prototype.

+ `toString()` - Returns a string representation of the Boolean ('true' or 'false')
+  `valueOf()` - Returns the value of the Boolean (true or false)

**null & undefined**: The JS literal `null` is used to represent an empty value whereas `undefined` represents the value undefined i.e., an unassigned value. It must be noted that the equality operator `==` type converts `null` to `undefined` and hence strict equality operator `===` must be used when null and undefined are needed to be distinguished. This is discussed in detail in *Operators* section.

**Objects**: Objects in Javascript are simply variables with properties. Each property can be viewed as a name-value pair. Objects can be created by using the `Object` constructor or by using the Object Initializer literal `{}`.

```javascript
var Person = new Object();

Person.firstName = "John";
Person.lastName = "Doe";
Person.age = 20;
```

The above JS code creates an Object named `Person` which has the properties `firstName`,`lastName`,`age`. We can also create the above Object using the Object Initializer literal as follows,

```javascript
var Person = {
                firstName : "John",
                lastName : "Doe",
                age : 20
};
```

**Accessing Object Properties**: We can access the properties of an Object in two ways. One is to use `dot-notation` in the format `ObjectName.propertyName` and the other way is to use `Array notation` in the format `ObjectName['propertyName']`.

```javascript
console.log(Person.firstName); // Displays 'John'
console.log(Person['lastName']); // Displays 'Doe'
```

The `dot-notation` is the commonly used in practice.

Javascript provides a few native methods to work with Objects. 

+ `Object.keys(objName)` - Returns an array containing the enumerable properties of the Object
+ `Object.getOwnProperyNames(objName)` - Returns an array containing the enumerable and non-enumerable properties of the Object
+ `for..in` - Used to iterate through the properties of the Object.

```javascript
console.log(Object.keys(Person)); // Displays ["firstName", "lastName"]
console.log(Object.getOwnPropertyNames(Person)); // Displays ["firstName", "lastName"]

for(prop in Person) {
    console.log(Person[obj]); // Displays "John" , "Doe"
}
```

**Using Constructors**: We can also create our own constructors to instantiate an Object. Object Constructors can be created as follows,

```javascript

function Person(firstName, lastName) {
    
    this.firstName = firstName;
    this.lastName  = lastName;
}

// Lets create our Objects for Person
var John = new Person("John","Doe");
var Foo  = new Person("Foo","Bar");

// Accessing the Object Properties
console.log(John.firstName); // Displays "John"
console.log(Foo.lastName); // Displays "Bar"

```
##Arrays

Arrays in Javascript can be created by using the Array Constructor or simply by using the Array initializer `[]`. The arguments to the Array constructor are the elements of the array and passing a single integer defines the size of the array. 

One of the notable features in Javascript Arrays is that We can dynamically change the size of the Array, similar to that of `ArrayList` in Java and also the elements in array can be of different type. The property `length` can be used at any time to access the length of the Array.

```javascript

var myArray = new Array("Hello","World"); // Creates a new Array with elemets "Hello" and "World"

console.log(myArray.length); // Displays 2

console.log(myArray[0]); // Displays "Hello" 

```
**Note**: Array index starts with 0.

```javascript

var myArray = ["Javascript","Hello","World"]; // Using Array Initializer

console.log(myArray.length); // Displays 3

```

##Array Methods

+ `push(element)` - Pushes the `element` to the end of array and returns the new length of the array
+ `pop()` - Pops / Removes the last element from the array and returns that element
+ `shift()` - Removes the first element from the array and returns that element
+ `toString()` - Returns a String representation of the array with the elements separated by comma
+ `join(separator)` - Combines all the elements of the array into a String separated by `separator`
+ `sort()` - Returns an array sorted in order of string Unicode
+ `reverse()` - Reverse the order of elements in the array 
+ `slice(start,end)` - Returns an array with the elements beginning from `start` index to `end` index (without including the last element)
+ `splice(index,num,elements)` - Removes the `num` of elements from `index` and adds the `elements` to the array
+ `indexOf(element,start)` - Searches the array for the `element` starting from `start` and returns the index of the element if found, or `-1` if not found.
+ `concat(arrays)` - Concatenates the elements from two / more arrays specified by `arrays`


##Examples

```javascript
var a = [1,2,3];

a.push(4); // Inserts 4 to the end of the array

console.log(a);  // Displays [1, 2, 3, 4]

console.log( a.pop() ); // Removes the last element `4` from the array   

console.log( a.reverse() ); // Displays [3, 2, 1]

console.log( a.toString() ); // Displays "3,2,1"

var ascending = a.sort(function(a,b) { return a - b; });
var descending = a.sort(function(a,b) { return b - a; });

// Here we make use of Closure to the sort() method to perform sorting in ascending / descending order
console.log(ascending); // Displays [1, 2, 3]
console.log(descending); // Displays [3, 2, 1]

console.log( a.indexOf(1) ); // Displays 2, the position of element `1` in the array

console.log( a.slice(1,2) ); // Displays [2]

var b = [1,2,3];
var c = [4,5,6];

console.log( b.concat(c) ); // Displays [1, 2, 3, 4, 5, 6]

``` 
**Note**: We can also use chaining of methods in Javascript

```javascript

var a = [1,2,3];

console.log( a.reverse().toString() ); // Displays "3,2,1"

```
