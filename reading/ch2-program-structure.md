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

>A statement starting with the keyword while creates a loop. The word while is followed by an expression in parentheses and then a statement, much like if. The loop executes that statement as long as the expression produces a value that is true when converted to Boolean type.
In this loop, we want to both print the current number and add two to our variable. Whenever we need to execute multiple statements inside a loop, we wrap them in curly braces ({ and }). Braces do for statements what parentheses do for expressions: they group them together, making them count as a single statement. A sequence of statements wrapped in braces is called a block. -Eloquent JavaScript

>The variable number demonstrates the way a variable can track the progress of a program. Every time the loop repeats, number is incremented by 2. Then, at the beginning of every repetition, it is compared with the number 12 to decide whether the program has done all the work it intended to do.
As an example that actually does something useful, we can now write a program that calculates and shows the value of 210 (2 to the 10th power). We use two variables: one to keep track of our result and one to count how often we have multiplied this result by 2. The loop tests whether the second variable has reached 10 yet and then updates both variables. -Eloquent JavaScript

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

A control structure similar to a while loop is the do loop.  Main difference is a do loop always executes its body at least once.  Then starts testing whether to stop only after the first execution.

```javascript
do {
  var yourName = prompt("Who are you?");
} while (!yourName);
console.log(yourName);
```

>This program will force you to enter a name. It will ask again and again until it gets something that is not an empty string. Applying the ! operator will convert a value to Boolean type before negating it, and all strings except "" convert to true. This means the loop continues going round until you provide a name that is not the empty string. -Eloquent JavaScript

##Indenting Code
To maximize your code's readability, indent your code.  Use spaces or tabs to illustrate your code's internal structure.

Below are two examples:

```javascript
let stop=11
for (let i=1;i<stop;i++){
if(i%2===0){console.log("i is even!",i)}
}
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
>Many loops follow the pattern seen in the previous while examples. First, a “counter” variable is created to track the progress of the loop. Then comes a while loop, whose test expression usually checks whether the counter has reached some boundary yet. At the end of the loop body, the counter is updated to track progress.
Because this pattern is so common, JavaScript and similar languages provide a slightly shorter and more comprehensive form, the for loop. -Eloquent JavaScript

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

##Breaking Out A Loop
>Having the loop’s condition produce false is not the only way a loop can finish. There is a special statement called break that has the effect of immediately jumping out of the enclosing loop.
This program illustrates the break statement. It finds the first number that is both greater than or equal to 20 and divisible by 7. -Eloquent JavaScript

```javascript
for (var current = 20; ; current++) {
  if (current % 7 == 0) {
    break;
  }
}
console.log(current)
// → 21
```

>Using the remainder (%) operator is an easy way to test whether a number is divisible by another number. If it is, the remainder of their division is zero.
The for construct in the example does not have a part that checks for the end of the loop. This means that the loop will never stop unless the break statement inside is executed.
If you were to leave out that break statement or accidentally write a condition that always produces true, your program would get stuck in an infinite loop. A program stuck in an infinite loop will never finish running, which is usually a bad thing.
If you create an infinite loop in one of the examples on these pages, you’ll usually be asked whether you want to stop the script after a few seconds. If that fails, you will have to close the tab that you’re working in, or on some browsers close your whole browser, in order to recover. -Eloquent JavaScript

##Updating Variables Succinctly
>Especially when looping, a program often needs to “update” a variable to hold a value based on that variable’s previous value. -Eloquent JavaScript

##Dispatching On A Value With Switch
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

>There is a construct called switch that is intended to solve such a “dispatch” in a more direct way. Unfortunately, the syntax JavaScript uses for this (which it inherited from the C/Java line of programming languages) is somewhat awkward—a chain of if statements often looks better. Here is an example: -Eloquent JavaScript

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

>You may put any number of case labels inside the block opened by switch. The program will jump to the label that corresponds to the value that switch was given or to default if no matching value is found. It starts executing statements there, even if they’re under another label, until it reaches a break statement. In some cases, such as the "sunny" case in the example, this can be used to share some code between cases (it recommends going outside for both sunny and cloudy weather). But beware: it is easy to forget such a break, which will cause the program to execute code you do not want executed. -Eloquent JavaScript

##Capitalization
>Variable names may not contain spaces, yet it is often helpful to use multiple words to clearly describe what the variable represents. These are pretty much your choices for writing a variable name with several words in it:

```javascript
namingconventionsvary
naming_conventions_vary
NamingConventionsVary
namingConventionsVary
```

>The first style can be hard to read. Personally, I like the look of the underscores, though that style is a little painful to type. The standard JavaScript functions, and most JavaScript programmers, follow the bottom style—they capitalize every word except the first. It is not hard to get used to little things like that, and code with mixed naming styles can be jarring to read, so we will just follow this convention. -Eloquent JavaScript

##Comments
>Often, raw code does not convey all the information you want a program to convey to human readers, or it conveys it in such a cryptic way that people might not understand it. At other times, you might just feel poetic or want to include some thoughts as part of your program. This is what comments are for.
A comment is a piece of text that is part of a program but is completely ignored by the computer. JavaScript has two ways of writing comments. To write a single-line comment, you can use two slash characters (//) and then the comment text after it. -Eloquent JavaScript

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
