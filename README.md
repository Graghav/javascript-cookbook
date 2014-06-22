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

```javacript
var bar = 'Hello World';

// concat() method 
var foo = bar.concat(' Foo');
console.log(foo); // Displays 'Hello World Foo'

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
