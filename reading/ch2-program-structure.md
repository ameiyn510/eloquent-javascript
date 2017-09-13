# Program Structure

##Intro
>In this chapter, we will start to do things that can actually be called programming. We will expand our command of the JavaScript language beyond the nouns and sentence fragments we’ve seen so far, to the point where we can express some meaningful prose. -Eloquent JavaScript

##Objectives
- Obj 1
- Obj 2
- Obj 3

##Expressions and Statements
>In Chapter 1, we made some values and then applied operators to them to get new values. Creating values like this is an essential part of every JavaScript program, but it is only a part.
A fragment of code that produces a value is called an expression. Every value that is written literally (such as 22 or "psychoanalysis") is an expression.
If an expression is a sentence fragment, a statement corresponds to a full sentence in human language.  A program is simply a list of statements.

The simplest statements are expressions followed by a semi-colon.

```javascript
42;
!false;
```

Remember:  A JavaScript statement is a line of executable code.  Only amounts to something if it affects the world.

##Variables

>How does a program keep an internal state? How does it remember things? We have seen how to produce new values from old values, but this does not change the old values, and the new value has to be immediately used or it will dissipate again. To catch and hold values, JavaScript provides a thing called a variable. -Eloquent JavaScript

```javascript
let randomNumber = 5;
```

The reserved keyword 'let' indicates this statement will define a variable.

>After a variable has been defined, its name can be used as an expression. The value of such an expression is the value the variable currently holds. Here’s an example: -Eloquent JavaScript

```javascript
let five = 5
console.log(5*5)
//25
console.log(five*5)
//25
console.log(five*five)
//25
```

A variable's name and value are not tied together forever.  Use the = operator to connect existing variables to new values.

```javascript
let mood = "happy";
console.log(mood);
//"happy"

mood = "hangry";
console.log(mood)
//"hangry"

```

Here's another simple example:

```javascript
let debtToMom = 1000
debtToMom = debtToMom - 120;
console.log(debtToMom);
//880
```

##Keywords and Reserved Words


#Types
##Numbers
##Arithmetic
##Strings
##console.log
##Booleans
##Undefined Values
#Operators
##Unary Operators
##Comparison
##Logical Operators
###And
###Or
###Not
##Automatic Type Conversion
#Summary
