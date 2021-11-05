# Table of Contents

* [Week One](#week-one)
* [What is Racket?](#what-is-racket?)
* [Syntax Stuff](#syntax-stuff)
* [Recursion!](#recursion)

## Week One
###### October 25th to November 5th
### What is Racket?

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
