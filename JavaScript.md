# Table of Contents

* [Week One](#week-one)
* * [What is JavaScript?](#what-is-javascript?)
* * [Objects](#objects)
* * [Classes](#classes)
* [References](#references)

## Week One
###### October 4th to 11th

### What is JavaScript?
I have been doing some light reading on JavaScript before really tring to get much coding done as I haven't used JavaScript before. This is different from the Python assignment where I had taken a course that used Python and had been already faimliar. It helps for me to do a bunch of reading on the syntax and behaviour of a language before coding. If I don't, I end up just throwing lots of poor code against the wall to see what sticks.

JavaScript is a relatively new language, created in '95 mainly for webpages. Apparently it also has nothing to do with Java despite the name. JavaScript seems to be pretty flexible and let you do some things that you wouldn't get away with in Python or Java:

```javascript
let plusOne = Function("n", "return n + 1;");
console.log(plusOne(4));
// → 5
```
Looking at this at face value, I understand what is happening but wonder about how far you could go with this "Function" declaraction. Maybe it will be useful in quick sorting? Or would it just be a bad idea?

### Objects

In JavaSctipt most everything can be an object, even primitives. The five primitive data types are string, number, boolean, null, and undefined, with the values of these primitives being immutable. Objects are declared with the "let" keyword and can contain single values or "name: value" pairs. It is also common practice to define objects with the "const" keyword.
```javascript
let me = "Paul Hayes"
```
OR, with const:
```javascript
const me = {firstName: "Paul", lastName:"Hayes", age:1260921
```
Seems like an easier Python Dictionary to me, which is cool. You can also add properties of an object as you need:
```javascript
const me = new Object();
me.firstName = "Paul";
me.age = 1205912890581209;
```
Objects are mutable. Declaring a new object as a preexisting object will not create a copy.
```javascript
const alsoMe = me
alsoMe.age = 10
console.log(me.age)
// → 10
```
### Classes

Classes are pretty similar to other languages, except in JavaScript each class *must* have a constructor method, or JavaScript will create a blank once. [w3schools](https://www.w3schools.com/js/js_class_intro.asp) gives this example:

```javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
  age(x) {
    return x - this.year;
  }
}

let date = new Date();
let year = date.getFullYear();

let myCar = new Car("Ford", 2014);
document.getElementById("demo").innerHTML=
"My car is " + myCar.age(year) + " years old.";
```

## Week Two to Three
###### October 12th to 24th

### Supported Paradigms
![image](https://user-images.githubusercontent.com/60442665/138610018-64461b55-20be-44f3-a32f-d1ae77fb1c34.png)
```javascript
const paradigms = [
  {name: 'Imperative', support: true, parent: null},
  {name: 'Declarative', support: true, parent: null},
  {name: 'Functional', support: true, parent: 'Declarative'},
  {name: 'Object-Oriented', support: true, parent: 'Imperative'},
  {name: 'Event-Driven', support: true, parent: null},
  {name: 'Quantum', support: false, parent: null},
  {name: 'Symbolic', support: false, parent: null}
]
/* Imperative Pattern */
for (let i = 0; i < paradigms.length; i++) {
  if (paradigms[i].support === true) {
    console.log(paradigms[i])
  }
}
/* Declarative Pattern */
const jsParadigms = paradigms.filter((p) => p.support === true)
console.log(jsParadigms)
```
JavaScript is a good mix of Imperative and Declarative Programming. 

#### Functional Programming
First-Class Functions - functions can be assigned to variables and can be passed into other functions. Functions can also be returned from other functions.
```javascript
function writeHello() {
  return function () {
    console.log("Something")
  }
}
const something = function () {
  console.log("Something")
}
```
Lambda Syntax - as shown above, functions can be passed around as data using the "fat arrow" ```=>```

Closures - functions can be nested inside eachother. Closures have three scopes: local, outer functions, and global.

Being able to use functions in this way creates a lot of oppurtunity for the programmer to be creative and use less code to accomplish more. Although less reusable, it saves a lot of time and can be easier to read.

#### Object-Oriented Programming: Prototype-based
In Object Oriented Programming, programs are written as collections of classes and objects which communicate with eachother. The most basic and smallest entity is the object, which many different kinds of computations are performed on. This is more focused on the data itself, rather than the procedure. 

JavaScript reuses existing objects that serve as prototypes: there is no pure inheritance or extensions.
```javascript
function Student() {
    this.name = 'John';
    this.gender = 'Male';
}
var studObj1 = new Student();
studObj1.age = 15; // add an age property to student
alert(studObj1.age); // 15

var studObj2 = new Student();
alert(studObj2.age); // undefined
```
As we can see, studObj2 has no instance of age property since it is defined only on the studObj1 instance. We can add new properties to be shared across all instances using prototypes:
```javascript
function Student() {
    this.name = 'John';
    this.gender = 'M';
}
Student.prototype.age = 15;

var studObj1 = new Student();
alert(studObj1.age); // 15

var studObj2 = new Student();
alert(studObj2.age); // 15
```

## References
* [What is JavaScript?](https://eloquentjavascript.net/00_intro.html#h_GlF1Kuv0JF)
* [Objects](https://www.w3schools.com/js/js_object_definition.asp)
* [Classes](https://www.w3schools.com/js/js_class_intro.asp)
* [Paradigms](https://javascript.plainenglish.io/what-are-javascript-programming-paradigms-3ef0f576dfdb)
* [More Paradigms](https://ageek.dev/js-paradigms)
* [Prototype Objects](https://www.tutorialsteacher.com/javascript/prototype-in-javascript#:~:text=The%20answer%20is%20Prototype.%20The%20prototype%20is%20an,visible.%20Every%20function%20includes%20prototype%20object%20by%20default.)
