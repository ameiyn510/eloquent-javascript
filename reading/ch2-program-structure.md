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
// → 25
console.log(five*5)
// → 25
console.log(five*five)
// → 25
```

A variable's name and value are not tied together forever.  Use the = operator to connect existing variables to new values.

```javascript
let mood = "happy";
console.log(mood);
// → "happy"

mood = "hangry";
console.log(mood)
// → "hangry"

```

Here's another simple example:

```javascript
let debtToMom = 1000
debtToMom = debtToMom - 120;
console.log(debtToMom);
// → 880
```

##Keywords and Reserved Words

Words with special meanings in JavaScript may not be used as variable names.  The full list of words is long.

```
break case catch class const continue debugger
default delete do else enum export extends false
finally for function if implements import in
instanceof interface let new null package private
protected public return static super switch this
throw true try typeof var void while with yield
```

Don't memorize the list above.  Just remember -- the above words may not be used in variable names.

##The Environment

>The collection of variables and their values that exist at a given time is called the environment. When a program starts up, this environment is not empty. It always contains variables that are part of the language standard, and most of the time, it has variables that provide ways to interact with the surrounding system. For example, in a browser, there are variables and functions to inspect and influence the currently loaded website and to read mouse and keyboard input. -Eloquent JavaScript

##Functions
>A lot of the values provided in the default environment have the type function. A function is a piece of program wrapped in a value. Such values can be applied in order to run the wrapped program.  For example, in a browser environment, the variable alert holds a function that shows a little dialog box with a message. -Eloquent JavaScript

```javascript
alert('Good morning friends!');
```

Executing a function is called invoking, calling, or applying.  

The most common way to call a function is to write parentheses after its name.  In-between parentheses, put the function's input.  Also known as an argument.  Re-examine the alert function above.

##The console.log function

>In past examples, we’ve used console.log to output values. Most JavaScript systems (including all modern web browsers and Node.js) provide a console.log function that writes out its arguments to some text output device. In browsers, the output lands in the JavaScript console. This part of the browser interface is hidden by default, but most browsers open it when you press F12 or, on Mac, when you press Command-Option-I. If that does not work, search through the menus for an item named “web console” or “developer tools”. -Eloquent JavaScript

```javascript
let x = 15;
console.log("this is x:",x)
// → this is x: 15
```

Question.  If variable names cannot contain periods, why is console.log valid syntax?

##Side Effects
>Showing a dialog box or writing text to the screen is a side effect. A lot of functions are useful because of their side effects.
Functions may also produce values.  For example, the function Math.max takes any number of number values and gives back the greatest. -Eloquent JavaScript

```javascript
console.log(Math.max(2, 4));
// → 4
```

##Return Values
>When a function produces a value, it is said to return that value. Anything that produces a value is an expression in JavaScript, which means function calls can be used within larger expressions. Here a call to Math.min.

```javascript
console.log(Math.min(2, 4) + 100);
// → 102
```

Question.  Why was the above result 102?  Why not 106?  Or 94?

##Control Flow
>When your program contains more than one statement, the statements are executed, predictably, from top to bottom. As a basic example, this program has two statements. The first one asks the user for a number, and the second, which is executed afterward, shows the square of that number. -Eloquent JavaScript

```javascript
let theNumber =  Number(prompt("Pick a number", ""));
alert("Your number is the square root of " + theNumber * theNumber);
```

>The function Number converts a value to a number. We need that conversion because the result of prompt is a string value, and we want a number. There are similar functions called String and Boolean that convert values to those types. -Eloquent JavaScript

##Conditional Execution
Executing statements in straight-line order is not our only option.  With conditional execution, we choose between two different routes based on a Boolean value.

Conditional execution is written with the if keyword in JavaScript. In the simple case, we just want some code to be executed if, and only if, a certain condition holds.

For example in the previous program.  Suppose we only show the square of the input only if input is of type number.

```javascript
let theNumber = Number(prompt("Pick a number", ""));
if (!isNaN(theNumber)) {
  alert("Your number is the square root of " + theNumber * theNumber);
}
```

What happens if you enter "Dwayne The Rock Johnson"?  No output is shown.

>The keyword if executes or skips a statement depending on the value of a Boolean expression. The deciding expression is written after the keyword, between parentheses, followed by the statement to execute.
>The isNaN function is a standard JavaScript function that returns true only if the argument it is given is NaN. The Number function happens to return NaN when you give it a string that doesn’t represent a valid number. Thus, the condition translates to “unless theNumber is not-a-number, do this”. -Eloquent JavaScript

Check For Understanding.  What happened to the alert?

##If-else

Often, a programmer wants both (a) code that executes when a condition holds true AND (b) different code that executes when a condition holds false.  The else keyword can be used with if to create two separate, alternate execution paths.

```javascript
let theNumber = Number(prompt("Pick a number", ""));
if (!isNaN(theNumber)) {
  alert("Your number is the square root of " + theNumber * theNumber);
} else {
  alert("Hey. Why didn't you give me a number?");
}
```

What if we need more than two separate, alternate execution paths??

##Chaining If/elseIf/else

```javascript
let num = Number(prompt("Pick a number", "0"));

if (num < 10) {
  alert("Small");
} else if (num < 100) {
  alert("Medium");
} else {
  alert("Large");
}
```

Check for Understanding.  How does the above code work?

```javascript

```



#Summary
