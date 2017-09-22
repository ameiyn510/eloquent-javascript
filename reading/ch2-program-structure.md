# Program Structure

##Intro
This chapter we begin programming in earnest.  Passed nouns and sentence fragments, we will express meaningful prose.

##Objectives
- Obj 1
- Obj 2
- Obj 3

##Expressions and Statements
Creating values is essential for every JavaScript program.  But only part.

A fragment of code producing a value is called an expression.  Every value written literally is an expression.  

>If an expression is a sentence fragment, a statement corresponds to a full sentence in human language.  A program is simply a list of statements. -Eloquent JavaScript

The simplest statements are expressions followed by a semi-colon.

```javascript
42;
!false;
```

Remember:  A JavaScript statement is a line of executable code.  Only amounts to something if it affects the world.

##Variables
Earlier, we produced new values from old.  But these new values had to be used immediately -- or they'd dissipate.

How does a program remember things?  To hold values, JavaScript provides variables.

```javascript
let randomNumber = 5;
```

The reserved keyword 'let' indicates this statement will define a variable.

Once defined, a variable name can be used as an expression.  That expression's value is identical to the value held by the variable.

```javascript
let five = 5
console.log(5*5)
// → 25
console.log(five*5)
// → 25
console.log(five*five)
// → 25
```

Remember: a variable's name and value are not tied together forever.  Use the = operator to connect existing variables to new values.

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
A function is a piece of program wrapped in a value.  To run the wrapped program, apply the value.

>For example, in a browser environment, the variable alert holds a function that shows a little dialog box with a message. -Eloquent JavaScript

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

Check For Understanding.  If variable names cannot contain periods, why is console.log valid syntax?

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

Check For Understanding.  Why was the above result 102?  Why not 106?  Or 94?

##Control Flow
>When your program contains more than one statement, the statements are executed, predictably, from top to bottom. As a basic example, this program has two statements. The first one asks the user for a number, and the second, which is executed afterward, shows the square of that number. -Eloquent JavaScript

```javascript
let theNumber =  Number(prompt("Pick a number", ""));
alert("Your number is the square root of " + theNumber * theNumber);
```
Check For Understanding.  Above, why use the function Number?

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

Check For Understanding.  What happens if you enter "Dwayne The Rock Johnson"?

The value of the Boolean expression determines whether the keyword if executes or skips its code.  The deciding expression is written after keyword if, between parentheses.  Wrapped between following curly brackets is all code pending conditional execution.

Check For Understanding.  What happened to the alert?  What is the isNaN function?

##If-else
Often, a programmer wants both (a) code that executes when a condition holds true AND (b) different code to executes when a condition holds false.  The else keyword can be used with if to create two separate, alternate execution paths.

```javascript
let theNumber = Number(prompt("Pick a number", ""));
if (!isNaN(theNumber)) {
  alert("Your number is the square root of " + theNumber * theNumber);
} else {
  alert("Hey. Why didn't you give me a number?");
}
```

What if we need more than two separate, alternate execution paths??

##Chaining if / else if / else
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

#While and Do Loops
How to print all even numbers from 0 to 12?  Simplest might be:

```javascript
console.log(0)
// → 0
console.log(2)
// → 2
console.log(4)
// → 4
console.log(6)
// → 6
console.log(8)
// → 8
console.log(10)
// → 10
console.log(12)
// → 12
```

But what if we needed all even numbers from 0 to 1000?  The above solution is NOT sustainable.  Instead, we need to repeatedly run some code.  This type of control flow is called a loop.

Looping control flow returns to a previous point in the program, then re-runs code with our current program state.  

Combine the idea above with a variable that counts.

```javascript
let number = 0;
while (number <= 10){
  console.log(number);
  number=number+2;
}
// → 0
// → 2
// ... etcetera
```

Beginning a statement with the keyword while creates a loop.  Following while is an expression in parentheses then a statement wrapped in curly brackets.  Much like if.  So long as the parenthetical expression is true, the loop will repeatedly execute its statement.

Check For Understanding.  Why did the above while loop stop?

Notice number tracks the program's progress.  Every time the loop repeats, number is incremented by 2.

For the first time, let's examine useful code.  Below is code to calculate 2 to the 10th power.

```javascript
var result = 1;
var counter = 0;
while (counter < 10) {
  result = result * 2;
  counter = counter + 1;
}
console.log(result);
// → 1024
```

Check For Understanding.  What happens if I change the while loop's expression to read "counter<11"?

A control structure similar to a while loop is the do loop.  Main difference is a do loop always executes its body at least once.  Then starts testing whether to stop only after the first execution.

```javascript
do {
  var yourName = prompt("Who are you?");
} while (!yourName);
console.log(yourName);
```

This program forces users to enter a name.  It will repeatedly ask until given a non-empty string value.

Check For Understanding.  What happens if I enter the ! operator?

##Indenting Code
To maximize your code's readability, indent your code.  Use spaces or tabs to illustrate your code's internal structure.

Below are two examples:

```javascript
let stop=11
for (let i=1;i<stop;i++){if(i%2===0){console.log("i is even!",i)}}
```

In human language, what is the above code doing??  How long did it take to understand?

```javascript
let stop = 15
for ( let i = 1; i < stop; i++ ){
  if ( i % 3 === 0 ) {
    console.log("i is divisible by three!",i)
  }
}
// → 3
// → 6
// ... etcetera
```

The above example is indented well.  Without effort, we see a conditional nested in a for-loop.  Spaces help readability too.

##For Loops
Writing loops follow a similar pattern.  In plain language, first we use the 'for' keyword.  Then we instantiate a variable representing out loop's starting point.  Next comes our ending point.  Finally, our increment.

```javascript
for ( let number = 0; number <= 10; number=number+2 ) {
  console.log(number)
}
// → 0
// → 2
// ... etcetera
```

>This program is exactly equivalent to the earlier even-number-printing example. The only change is that all the statements that are related to the “state” of the loop are now grouped together.
The parentheses after a for keyword must contain two semicolons. The part before the first semicolon initializes the loop, usually by defining a variable. The second part is the expression that checks whether the loop must continue. The final part updates the state of the loop after every iteration. In most cases, this is shorter and clearer than a while construct. -Eloquent JavaScript

Remember the while loop above which calculates 2 to the 10th power??

```javascript
let result = 1;
for (let counter = 0; counter < 10; counter = counter + 1) {
  result = result * 2;
}
console.log(result);
// → 1024
```

Check For Understanding.  What does the code above do?
For the above code to print the 12th power of 2, what to change??

##Breaking Out A Loop
Another way to finish a loop is the break statement.  A break will immediately jump you out the loop.

```javascript
for (var current = 20; ; current++) {
  if (current % 7 == 0) {
    break;
  }
}
console.log(current)
// → 21
```

The remainder (%) operator can test whether a number is divisible by another.  Remember: clean divisions result in a remainder of zero.

The example for-loop above does not have an ending point.  In other words: the loop will never stop unless the break statement inside is executed.  An infinite loop.

A program stuck in an infinite loop will never finish running.  This is almost always bad.

Intentionally or not, you will eventually write your own infinite loop.  After a few seconds of infinite loop, you're usually asked whether to terminate the script.  If that fails, try closing the tab.  If that fails too, try restarting your browser.

##Updating Variables Succinctly
Programs often need to update a variable's value.  

```javascript
let counter = 5;
counter= counter+1
console.log(counter)
// → 6
```

Look at this more succinct syntax.

```javascript
let counter = 5;
counter+=1
console.log(counter)
// → 6
```

Explore these different syntaxes.
```javascript
let counter = 5;
console.log(counter*=2)
console.log(counter-=3)
console.log(counter++)
console.log(counter--)
```

Check For Understanding.  What should log to the console?


##Dispatching On A Value With Switch
Common is the style of code below.

```javascript
if (variable == "value1"){
  action1();
} else if (variable == "value2") {
  action2();
} else if (variable == "value3") {
  action3();
} else {
  defaultAction();
}
```

A switch statement helps solve "dispatch" directly.  But the syntax is a little awkward.

```javascript
switch (prompt("What is the weather like?")) {
  case "rainy":
    console.log("Remember to bring an umbrella.");
    break;
  case "sunny":
    console.log("Dress lightly.");
  case "cloudy":
    console.log("Go outside.");
    break;
  default:
    console.log("Unknown weather type!");
    break;
}
```

Inside the switch's code block can go any number of case labels.  The program will automatically jump to the label's code if the switch finds a matching value.  No match will invoke the default.

Check For Understand.  Run the code above.  What happens when you enter "sunny"?

##Capitalization
Variable names may not contains paces.  Using multiple words for a variable name is often helpful.  Observe these examples

```javascript
namingconventionsvary
naming_conventions_vary
NamingConventionsVary
namingConventionsVary
```

The standard JavaScript naming convention is camelCase.  The last example has each word capitalized except the first.

##Comments

>Often, raw code does not convey all the information you want a program to convey to human readers, or it conveys it in such a cryptic way that people might not understand it. At other times, you might just feel poetic or want to include some thoughts as part of your program. This is what comments are for.
A comment is a piece of text that is part of a program but is completely ignored by the computer. JavaScript has two ways of writing comments. To write a single-line comment, you can use two slash characters (//) and then the comment text after it. -Eloquent JavaScript

=============EDITING LINE=============
=============EDITING LINE=============
=============EDITING LINE=============  

```javascript
var accountBalance = calculateBalance(account);
// It's a green hollow where a river sings
accountBalance.adjust();
// Madly catching white tatters in the grass.
var report = new Report();
// Where the sun on the proud mountain rings:
addToReport(accountBalance, report);
// It's a little valley, foaming like light in a glass.
```

<!-- A // comment goes only to the end of the line. A section of text between /* and */ will be ignored, regardless of whether it contains line breaks. This is often useful for adding blocks of information about a file or a chunk of program. -->

```javascript
/*
 I first found this number scrawled on the back of one of
 my notebooks a few years ago. Since then, it has often
 dropped by, showing up in phone numbers and the serial
 numbers of products that I've bought. It obviously likes
 me, so I've decided to keep it.
*/
var myNumber = 11213;
```

>You now know that a program is built out of statements, which themselves sometimes contain more statements. Statements tend to contain expressions, which themselves can be built out of smaller expressions.
Putting statements after one another gives you a program that is executed from top to bottom. You can introduce disturbances in the flow of control by using conditional (if, else, and switch) and looping (while, do, and for) statements.
Variables can be used to file pieces of data under a name, and they are useful for tracking state in your program. The environment is the set of variables that are defined. JavaScript systems always put a number of useful standard variables into your environment.
Functions are special values that encapsulate a piece of program. You can invoke them by writing functionName(argument1, argument2). Such a function call is an expression, and may produce a value. -Eloquent JavaScript

#Summary
>You now know that a program is built out of statements, which themselves sometimes contain more statements. Statements tend to contain expressions, which themselves can be built out of smaller expressions.
Putting statements after one another gives you a program that is executed from top to bottom. You can introduce disturbances in the flow of control by using conditional (if, else, and switch) and looping (while, do, and for) statements.
Variables can be used to file pieces of data under a name, and they are useful for tracking state in your program. The environment is the set of variables that are defined. JavaScript systems always put a number of useful standard variables into your environment.
Functions are special values that encapsulate a piece of program. You can invoke them by writing functionName(argument1, argument2). Such a function call is an expression, and may produce a value. -Eloquent JavaScript
