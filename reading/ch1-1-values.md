# Values

##Objectives
- Explain JavaScript values
- List all six basic types in JavaScript
- Explain each type.  Give examples.

##Intro
>Inside the computer’s world, there is only data. You can read data, modify data, create new data—but anything that isn’t data simply does not exist. All this data is stored as long sequences of bits and is thus fundamentally alike. -Eloquent JavaScript

##What is a Value?
>A typical modern computer has more than 30 billion bits in its volatile data storage. Nonvolatile storage (the hard disk or equivalent) tends to have yet a few orders of magnitude more.

>To work with such quantities of bits without getting lost, separate them into chunks that represent pieces of information. In a JavaScript environment, those chunks are called values.-Eloquent JavaScript

#Types
>Every value has a type that determines its role. There are six basic types of values in JavaScript: numbers, strings, Booleans, objects, functions, and undefined values -Eloquent JavaScript

##Numbers
The most simple type is Number.  Below is an example of a value with the type 'number'.

```javascript
42
```

Here's a fraction

```javascript
42.42
```

This is an example of scientific notation for 42 billion.

```javascript
4.2e10
```

##Arithmetic
Numbers are mainly used for arithmetic.  

```javascript
100 + 20
```

JavaScript follows order of operations.

```javascript
100 + 20 * 3 is NOT equal to (100+20)*3
```

##Strings

Strings represent text.  Strings must be enclosed with quotes.  Single or double.

```javascript
"Eloquent JavaScript"
'JavaScript Basic Training'
```

##console.log
Outputs a message to the developer console. - MDN

```javascript
console.log("hello class!")
// → "hello class!"
console.log(5);
// → 5
```

Note: Above the two backslashes before 'hello class!' represent the console's output.

In JavaScript, double-slashes denote code comments.  Any code and/or text beyond the '//' will NOT be read by the JavaScript interpreter.

##Booleans

The Boolean type has only two values --> true and false.  Observe this simple example.

```javascript
console.log(3 > 2)
// → true
console.log(3 < 2)
// → false
```

##Undefined Values
>There are two special values, written null and undefined, that are used to denote the absence of a meaningful value. They are themselves values, but they carry no information.
Many operations in the language that don’t produce a meaningful value (you’ll see some later) yield undefined simply because they have to yield some value.
The difference in meaning between undefined and null is an accident of JavaScript’s design, and it doesn’t matter most of the time. In the cases where you actually have to concern yourself with these values, I recommend treating them as interchangeable (more on that in a moment). - Eloquent JavaScript

```javascript
console.log(null)
// → null
console.log(undefined)
// → undefined
```

#Operators
JavaScript operators are used to assign values, compare values, perform arithmetic operations, and more. -W3Schools

##Unary Operators

A unary operator is an operation with only one operand.  A simple example is 'typeof'.

>The typeof operator returns a string indicating the type of the unevaluated operand. - MDN

```javascript
console.log(typeof 4);
// → 'number'
console.log(typeof 'x');
// → 'string'
```

##Comparison

Be careful with comparisons.  In JavaScript, strings can be compared like numbers.

```javascript
console.log("Aardvark" < "Zoroaster")
// → true
```

>The way strings are ordered is more or less alphabetic: uppercase letters are always “less” than lowercase ones, so "Z" < "a" is true, and non-alphabetic characters (!, -, and so on) are also included in the ordering. The actual comparison is based on the Unicode standard. -Eloquent JavaScript

Only one value JavaScript is not equal to itself.

NaN - The global NaN property is a value representing Not-A-Number. - MDN

```javascript
console.log(NaN == NaN)
// → false
```

Other common operators are >= (greater than or equal to), <= (less than or equal to), == (equal to), and != (not equal to).

```javascript
console.log(3>3)
// → false
console.log(3>=3)
// → true
console.log(4<4)
// → false
console.log(4<=4)
// → true
console.log(5==5)
// → true
console.log(5!=5)
// → false
```

##Logical Operators

JavaScript supports three logical operators.

###And
>The && operator represents logical and. It is a binary operator, and its result is true only if both the values given to it are true. -Eloquent JavaScript

```javascript
console.log(true && true)
// → true
console.log(true && false)
// → false
```

###Or
>The || operator denotes logical or. It produces true if either of the values given to it is true. -Eloquent JavaScript

```javascript
console.log(true || true)
// → true
console.log(true || false)
// → true
```

###Not
>Not is written as an exclamation mark (!). It is a unary operator that flips the value given to it—!true produces false and !false gives true. -Eloquent JavaScript

```javascript
console.log(!true)
// → false
console.log(!false)
// → true
```

##Automatic Type Conversion

JavaScript will go out of its way to evaluate a given expression.  This can result in odd behavior.

```javascript
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("five" * 2)
// → NaN
console.log(false == 0)
// → true
```

>When an operator is applied to the “wrong” type of value, JavaScript will quietly convert that value to the type it wants, using a set of rules that often aren’t what you want or expect. This is called type coercion. -Eloquent JavaScript

Beware type coercion!

>When comparing values of the same type using ==, the outcome is easy to predict: you should get true when both values are the same, except in the case of NaN. But when the types differ, JavaScript uses a complicated and confusing set of rules to determine what to do -Eloquent JavaScript

Best, as a general rule, avoid this problem by using ===.  

```javascript
console.log('3' == 3)
// → true
console.log(3 == 3)
// → true
console.log('3' === 3)
// → false
console.log(3 === 3)
// → true
```

#Summary

>We looked at four types of JavaScript values in this chapter: numbers, strings, Booleans, and undefined values.
<!-- Such values are created by typing in their name (true, null) or value (13, "abc"). You can combine and transform values with operators. We saw binary operators for arithmetic (+, -, *, /, and %), string concatenation (+), comparison (==, !=, ===, !==, <, >, <=, >=), and logic (&&, ||), as well as several unary operators (- to negate a number, ! to negate logically, and typeof to find a value’s type). -->
This gives you enough information to use JavaScript as a pocket calculator, but not much more. The next chapter will start tying these expressions together into basic programs. -Eloquent JavaScript

=============EDITING LINE=============
=============EDITING LINE=============
=============EDITING LINE=============

To create a value, first enter the keyword "let".
Then enter the value's name.
Enter an equals sign.
Finally, enter

```javascript
let name = "Dwayne The Rock Johnson";
```

In JavaScript, a variable stores a value of any type so that it can be used later in a program, potentially many different times. Variables can store values that are the result of sophisticated operations, also allowing programmers a way to indicate what a particular value ought to represent.

## Objectives

By the time you complete this section you should be able to:

- Declare variables
- Assign values to variables
- Assign values returned from functions to variables
- Reassign new values to variables
- Assign values already stored in variables to other variables

## Declaring Variables

**In JavaScript, a variable stores a value of any type so that we can use it later in our program. In order to use a variable we must ffirst _declare_ it, after which we can _assign_ a value to it.**

In order to **declare** a variable in JavaScript, we use the `let` keyword, followed by the name we would like to give to the variable. In this example we declare a new variable called `name`:

```javascript
let name;
```

You can think of a variable as a box with a label on it. The box can contain any kind of thing, and the label (hopefully, though not necessarily) will help us understand what is inside the box.

When we first **declare** a variable it is automatically **assigned** the value `undefined`:

```javascript
let name;

console.log(name); // logs `undefined` to the console
```

Note that when we pass the **variable** `name` into `console.log` above, we do **not** surround it with quotes of any kind. Remember that values surrounded by quotes refer to **strings**. Variables, on the other hand, might "contain" a value of any type.

```javascript
let name;
console.log(typeof(name));    // logs `'undefined'` to the console
console.log(typeof('name'));  // logs `'string'` to the console
console.log(name === 'name'); // logs `false` to the console
```

> In addition to **declaring** a variable with the `let` keyword, we can also use the `const` or `var` keywords. We will avoid a detailed discussion of the implications for declaring variables with each of these 3 different keywords here, but for now:

> - Use `let` as your default for declaring variables
> - If you know for certain that your variable will never be changed (more on this below) then use `const`
> - Use `var` after you understand what **Global Scope** means, and in the meantime (although this isn't totally accurate) consider it as equivalent to `let`

:star: In the text editor, declare 4 different variables, giving them any name you wish.

:question: What happens if you try to declare a variable that has a name like `4` or `16`?

:question: What happens if you try to declare a variable that has a name that looks like some of the other built in words like `let`, `true`, `undefined`?

## Assigning Values to Variables

After **declaring** a variable, we can **assign** a value of any type to it. When **assigning** values to a variable we use the **assignment operator** which is a single equal sign (`=`), placing the variable on the left hand side and the value we wish to "store" in the variable on the right. In the following example, we declare the variable `name` and then assign a value of type `string` to it:

```javascript
let name;
name = 'Rowan';

console.log(name);         // logs `'Rowan'` to the console
console.log(typeof(name)); // logs `'string'` to the console
```

As a matter of convenience, JavaScript allows us to both **declare** and **assign** a variable on the same line, thus:

```javascript
let name = 'Rowan';
let age = 1;
```

:star: Declare two variables, one called `aNumber`, and another called `anotherNumber`, and assign some value of type `number` to each of them. Then, log the result of adding the 2 number-containing variables in the console.

## Assigning Values Returned From Functions to Variables

Values returned from calling functions can be assigned to variables, just like any other value.

```javascript
let largestNumber = Math.max(5, 7, 2);
console.log(largestNumber); // logs `7` to the console
```

Storing returned values can be helpful in making our code easy to read and reason about, for example, compare the following two blocks of code:

```javascript
console.log(typeof(String(Math.max(0, 3, 1))) === typeof('number'));
```

Here's a refactor that makes some variable assignments to make the code easier to read and reason about:

```javascript
let largestNumber = Math.max(0, 3, 1);
let largestNumberString = String(largestNumber);

console.log(typeof(largestNumberString) === typeof('number')); // logs `true` to the console
```

We *could* make a choice to use even more variables:

```javascript
let largestNumber = Math.max(0, 3, 1);
let largestNumberString = String(largestNumber);
let typeofLargestNumberString = typeof(largestNumberString);

let someString = 'number';
let typeofSomeString = typeof(someString);

let typeofSomeStringIsEqualTotypeofLargestNumberString = typofSomeString === typeofLargestNumberString;
console.log(typeofSomeStringIsEqualTotypeofLargestNumberString); // logs `true` to the console
```

But probably you will agree this last section of code is not so nice. Over time you will develop a keen sense for when to use variables and when not to based on personal experience. In the meantime, this author recommends you aim to write code that reads like English, which means, using descriptive variable names more often than not.

> Don't make the mistake of thinking that short variable names saves you time or makes your code run faster, it doesn't. Cryptic code will cost everyone dearly who has to come back and figure out what your code is doing later. While it is fun at times to write the most dense and elegant solution, **legible is better than clever.**

:star: In the code below, 3 variables have been declared. Assign values to each of them so that they contain values akin to their names and cause the final `console.log` to log `true`.

```javascript
let two;
let three;
let twoIsGreaterThanThree;

console.log(twoIsGreaterThanThree); // should log `true` to the console
```

## Reassigning Values to Variables

**Variables that have already been assigned values can be assigned new values.** You can think of this as analogous to taking something out of a labeled box and putting something different in it.

```javascript
let name = 'Rowan';
console.log(name); // logs 'Rowan' to the console

name = 'Ro';       // <--- Assigning a new value to the variable
console.log(name); // logs 'Ro' to the console
```

An exception to this rule is if you declare your variable with the `const` keyword, which will make the variable **read only**.

```
const name = 'Rowan';
name = 'Ro' // This will cause your code to throw an error
```

**Variable names are chosen by programmers and we can only hope that they accurately describe the value assigned to the variable. Watch out.**

```javascript
let name = 8;
let food = 'staircase';
let theTruth = false;
let big = 0;
big = 'small';
big = null;
big = food;
```

## Assigning Variable Values to Other Variables

**We can assign values stored in one variable to another variable.**

The results of doing this vary depending on which type the value is. For the purposes of this section, we will speak about values of the types `string`, `number`, `boolean`, `undefined` and `null` (that is, values that are not of the `object` type).

Assigning a variable value to another value is like saying "Give me something identical to whatever is in that box so I can put that identical copy in this new box." This means that after assigning a variable value to another variable, reassigning one of the variables does not affect the other, in the same way that opening up one of our two boxes doesn't affect the other box at all. Thus:

```javascript
let aNumber = 3;
let anotherNumber = aNumber;

console.log(aNumber);                   // logs `3` to the console
console.log(anotherNumber);             // logs `3` to the console
console.log(aNumber === anotherNumber); // logs `true` to the console

aNumber = 5;

console.log(aNumber);                   // logs `5` to the console
console.log(anotherNumber);             // logs `3` to the console
console.log(aNumber === anotherNumber); // logs `false` to the console
```

## Conclusion

A value of any type can be assigned to a variable, which acts like a labeled box, containing that value. This included values that are returned from functions, values that are created from operations like, and values that are already stored in other variables.

Before continuing, be sure that you can:

- Declare variables
- Assign values to variables
- Assign values returned from functions to variables
- Reassign new values to variables
- Assign values already stored in variables to other values

## Self Assessment

:question: What will happen on each line when you try to run the following code? Why?

```javascript
const biggest = Math.max(1, 3, 4);
let newBiggest = 12;

biggest = newBiggest;

console.log(biggest);
```

## Next Steps

Now that we know how to store values in variables, including values that functions return, we can return to our discussion of calling functions. Next we will focus on more sets of built in functions so as to increase our fluency in the tools JavaScript provides. These next functions are a of a special kind that can operate "directly" on values (as you'll see), that are called **methods**.

## Table of Contents

### Basic Training Materials

- [Introduction](../README.md)
- [JavaScript and Modern Web Development](modern_web_development.md)
- [Dev Environment Setup](setup.md)
- [Introduction to Functions](intro_to_javascript_functions.md)
- [Basic Use of Functions](basic_use_of_functions.md)
- [JavaScript Types Crash Course](type_crash_course.md)
- [Functions that Make Values](functions_that_make_values.md)
- *Variables*
- [String Methods](string_methods.md)
- [Introduction to Arrays](intro_to_arrays.md)
- [Defining Functions](defining_functions.md)
- [Leveraging Multiple Functions](leveraging_multiple_functions.md)
- [Next Steps](next_steps.md)

### Advanced Content

- [Passing Functions as Arguments](passing_functions_as_arguments.md)
- [Higher Order Array Methods](higher_order_array_methods.md)

### Appendix

- [Reference and Further Study](reference.md)
