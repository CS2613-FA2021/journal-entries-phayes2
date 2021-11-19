# Table of Contents

* [Week One](#week-one)
* [Intro to Racket](#intro-to-racket)
* [Syntax Stuff](#syntax-stuff)
* [Recursion!](#recursion)
* [Final Weeks](#final-weeks)
* [More Syntax](#more-syntax)
* [Data Structures & Libraries](#data-structures&libraries)
* [Supported Paradigms](#supported-paradigms)
* [Under the Hood](#under-the-hood)

## Week One
###### October 25th to November 5th
### Intro to Racket

Racket seems to be pretty strange to me (and I'm sure strange for everyone else in this class). Apparently Racket was first developed as a tool to help beginner programmers learn how to code in the mid-90s. I guess we will see how easy it is to pick up if it is supposed to be geared more towards those who don't have a great grasp on programming concepts. 

I like to start with basic syntax stuff because it is probably the easiest thing to get used to.

### Syntax Stuff

There's a lot to go into here, as Racket is pretty different from all the other stuff I've coded in.

Right away I notice you can do some cool stuff in relatively short lines of code (which seems to be a recurring theme in our classes). From the Racket website, we have this:

```racket
#lang racket
(require 2htdp/image)

(let sierpinski ([n 8])
  (if (zero? n)
    (triangle 2 'solid 'red)
    (let ([t (sierpinski (- n 1))])
      (freeze (above t (beside t t))))))
```
Which produces a Sierpinski triangle to a depth of 8:

![image](https://user-images.githubusercontent.com/60442665/140438125-7e29672e-27bc-4e0c-842c-ece96c60c622.png)

Pretty cool stuff. We notice that Racket requires including 
```racket
#lang racket
```
at the start of every program. 

Numbers are "normal," we have stuff like 1024, 3.14, 1/5 but you binary, octal, and hexadecimal have different formats:
```racket
#b001
#o001
#x001
```

Arithmetic operations look kind of weird too:
```racket
(+ 1 1) ; produces 2
(- 10 5) ; 10-5 = 5
(expt 2 2) ; 2^2 = 4
```
and so on. Lists look similar but we use a character to stop it from being evaluated
```racket
`(+ 1 1) ; creates list containing (+ 1 1)
```

I'd like to look at recursion stuff as that is what we will have to do for Q1 on the assignment, and possibly the following questions.

### Recursion!

Taken from the Racket website is an example of a factorial function. First is the non-recursive example:

```racket
(define (factorial n)
  (define product 1)
  (for ([i (in-naturals 1)]
        #:final (= i n))
       (set! product (* product i)))
  product)

(factorial 20) ; 2432902008176640000
```

Whats interesting there is the set! declration and the #:final. Here is the recursive way of doing this:

```racket
(define (factorial n)
  (if (= n 1)
      1
      (* n (factorial (- n 1)))))

(factorial 20) ; 2432902008176640000
```

Slightly easier and is starting to make more sense syntax wise for me. I feel the arithmetic operations will take some getting used to.

## Final Weeks
###### November 5th to 19th
### More Syntax

The things that really tripped me up for Q2 for this assignment are function vs. variable declarations. They look really similar and caused me some trouble:

```racket
(define (factorial n) ; defines a function named factorial with a parameter of n
(define factorial n) ; defines a variable named function that is set to the value of n
```

Also, conditional statements were useful but kind of tricky:

```racket
(if (and (> n number)(divisible n number)) ; checks if both (n > number) and that the function divisible is true
        (set! lst (remove n lst)) ; set variable lst to what is returned from removing n from lst. You need to use set! to override lst
        (void)))  ; the above statement is called if the if statement is true. The void statement is the else
```

I used the above code in Q2. I could probably find a way to do this without the if statement so I can get rid of the useless void statement, but it works so I can be happy with it.

### Data Structures & Libraries

Structs are pretty simple but I didn't use them for the assignment:

```racket
(struct car(Make Model Year Color Mileage))
(define MyCar
  (car "Buick" "Car-Model" "Black" 123456)
)
```

Racket also have tons of libraries available, we used some in Q1 and A3 for the assignment.

### Supported Paradigms

Racket is imperative, procedural, structured

### Under the Hood

