# Clojure-and-Emacs
A Presentation for GA-Con

## Lisp - Quite Briefly
- "LISt Processor"
- Second-oldest (by one year, after Fortran) high-level programming language still in use today (invented at MIT!)
- Became popular language for AI research
- Pioneered many important CS concepts
- Common Lisp and Scheme are the two most widely-used Lisp dialects

## Clojure - Briefly
- Created by Rich Hickey of Cognitect
- Emphasizes "functional programming", i.e., tends away from mutable data, treats program as evaluation of mathematical functions
- Specialized language for dealing with problems of concurrency

#### Problems with Concurrency

- Multi-core processing creates problems with multi-threaded operations... if multiple threads are working with the same data, possible to achieve unexpected and incorrect results 
- Clojure takes advantage of multi-core processing power while maintaining data integrity by leveraging its *data immutability* and its strict rules for data mutations

##Emacs
In order to use a Lisp dialect, you have to be running a self-compiling list text editor... if I had realized this earlier in my preparations for this presentation, I would have presented on something else. But I didn't, and I spent three hours yesterday learning Emacs, so now it's time for a **presentation within a presentation** on Emacs.

#### The Face of Doom: Emacs' Intro Screen
![Emacs](http://www.braveclojure.com/assets/images/cftbat/basic-emacs/emacs-fresh.png "The face of doom")

- I can barely use this POS
- Normal text editor shortcuts do not work here; it's as if you're writing code in your terminal 
- Write your code in *buffers*
- Evaluate lines of code in REPL

#### Demo: Navigating Emacs
Allow me to demonstrate messing up a bunch of times as I try to navigate Emacs. Good times!

## Comparing Clojure and Javascript
#### Literals: pretty familiar
- Clojure integer: ```1```
- ```"A Clojure string"```
- ```["Clojure" "Vectors" "Are" "Like" "Javascript" "Arrays"]```

#### Clojure Operations: Give Your Lisp A List
```clojure
(+ 1 2 3 4)
; => 10

(+ 1 (* 2 3) 4)
; => 11

(def name "Rooster Bock Brewster")
(str "This presentation presentated by: " name)
; => "This presentation presentated by: Rooster Bock Brewster"
```

- Operations happen with the following syntax: *open parens, operator, operands, closing parens*
- Note syntax for nested operations, as well as variable definitions
- **variable definitions are generally immutable** 
 
#### Flow Control and Logic
```clojure
(if (= (+ 1 2) 3)
  "Jeff's beard is great"
  "Kevin's beard is great")
; => "Jeff's beard is great"

(if (= "Yao Wen" "Really cool")
  "Jeff's beard is great"
  "Kevin's beard is great")
; => "Kevin's beard is great"
```
- First position tells Clojure that it's an if statement
- Second position is evaluated as a boolean (only explicitly falsy values are ```nil``` and ```false```)
- Third position is the code which is evaluated if the boolean is true
- Fourth position is the code which is evaluated if the boolean is false
- But what if you want to do multiple things upon the boolean's resolution?

```clojure
(if (= "This presentation" "smooth and flawless")
  (do (println "Jeff's beard is great")
      "And he worships a lizard-octopus elder god")
  (do (println "Kevin's beard is great")
      "And he crushes beer pong"))
; => Kevin's beard is great
; => "And he crushes beer pong"
```
The "do" operator can fit several actions within one "position" of the if statement

```clojure
(def yao-wen "Really cool")
(when (= yao-wen "Really cool")
  (println "Yao Wen claims I am skilled in hip-hop dance")
  "As a cis-male person of pallor I find this highly offensive")
; => Yao Wen claims I am skilled in hip-hop dance
; => "As a cis-male person of pallor I find this highly offensive"
```
![yao-status](http://i.imgur.com/WWSKlQH.png "Ultimate troll")

The "when" operator is similar to "if", but only evaluates if the boolean evaluates to ```true```

#### Other Logical Operators: And and Or

- ```or``` evaluates to the first truthy value in a list, or the last value if none are truthy
- ```and``` evaluates to the first falsy value in a list, or if none are falsy, the last value

#### Other Data Structures
```clojure
; VECTORS
(conj [1 2 3] 4)
; => [1 2 3 4]

; LISTS 
(def ex-list (list 1 "two" {3 4}))
(nth ex-list 2)
; => {3 4}

; SETS
(hash-set 1 1 2 2)
; => #{1 2}

(def not-uniq [1 1 1 1 1 5 5 5 5 5 7 7 7 7])
(def uniq (set not-uniq))
uniq
; => #{7 1 5}

(sort uniq)
; => (1 5 7) -- note that it's a list now
```

#### Function Declarations
Let's look at some example functions in a .clj file loaded in Emacs

## Now You Know Clojure, Go Get PAAIIIDDD

From what I've seen, Clojure engineers do quite well, so we should all be rich by next week

## Resources

- [CLOJURE FOR THE BRAVE AND TRUE](http://www.braveclojure.com/)
- [Cognitect on Clojure](http://cognitect.com/clojure)
- [Get Emacs] (https://emacsformacosx.com/)
- [Help for Installing and Using Emacs](http://www.braveclojure.com/basic-emacs/#Editing_and_Help)
