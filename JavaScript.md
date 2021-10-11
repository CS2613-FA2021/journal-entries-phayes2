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

## References
* [What is JavaScript?](https://eloquentjavascript.net/00_intro.html#h_GlF1Kuv0JF)
* [Objects](https://www.w3schools.com/js/js_object_definition.asp)
* [Classes](https://www.w3schools.com/js/js_class_intro.asp)
