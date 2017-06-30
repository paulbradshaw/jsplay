# JavaScript basics

First, let's outline some basic jargon which will come in useful:

* A **statement** is a line of code that does something
* A statement might contain one or more **expressions**. There are various types of expressions, from a *literal value* expression (simply a number or string, which is also itself called a "**literal value**"); a *variable* expression (the name of variable); an *assignment* expression which assigns a value to a variable; an expression which performs *arithmetic* of some sort with either; and a *call* expression which calls a function.
* An **operator** is a character which has a special meaning. The best known operators are *arithmetic* operators like `+`, `-`, `/` and `*`, and *comparison* operators like `>` (greater than), `<` (less than) and `==` (note two 'equals' operators are used in coding to express 'equal to', and a single equals operator is used as as *assignment* operator to assign a value to a variable - you can also use `===` and other variations for more or less strict comparisons). The `.` (dot, or period) operator is particularly useful in accessing object properties.
* **Coercion** is the process of converting one data type into another: for example, converting a number into a string so that it can be printed, or used with another string (to form a URL for example). If coercion is needed for a statement to work, but it hasn't been explicitly done in the code, *implicit coercion* may happe. For example `console.log()` (see below) uses this (it doesn't ask permission) to coerce numbers to strings for printing. Likewise the numbers 0 and 1 may be coerced into FALSE and TRUE if it allows code to work.
* A **variable** typically stores information for your code. If that information is not designed to change, it is called a *constant* and conventionally named in capitals with underscores (e.g. `MY_VAR`). But most variables are designed to change (e.g. scores, usernames etc).
* A **block** is a group of statements, contained within curly brackets. Normally they are grouped because they are part of a function, `while`, `do`, `for` loop, or `if`/`else` statement: a block is then only run if the condition is met (or not met) - called a *conditional* - or a function called into action.

## Using the Console

A simple way to test out JavaScript is to write it directly in [the Developer Console in Firefox or Chrome](http://blog.teamtreehouse.com/mastering-developer-tools-console). A quick way to open this is by right-clicking on a webpage and selecting *Inspect* or *Inspect element*, then switching to the *Console* view tab in the window that appears.

In any JavaScript you can print useful information in the console too by using the `console.log()` function: whatever is in the parentheses (normally the name of a variable) is shown in the console when you view the webpage you have written with that JavaScript.

Strictly speaking, the function is `log()`. The `console` bit specifies that it sends the results of that function to the console.

## Adding comments

Add comments at the end of a line, or on their own line, with `//`

Add comments that run over multiple lines with `/*` at the start and `*/` at the end.

## Declaring (creating) variables

Whereas some other languages (such as R and Python) simply name the variable before assigning a value, JavaScript traditionally *declares* a variable the first time by using the statement `var` like so:

`var myname = "Paul";`

You can use `const` instead of `var` if it is a constant: this prevents it being changed later.

JavaScript also typically ends each expression with a semi-colon.

If the variable is *changed* later it does not need to be declared again, only the first time it is created.

## Defining (creating) functions

Functions are created with `function`, followed by the name of the function, parentheses (which name any variables it needs to use), and a *block* with the code that it executes when called. For example:

`function doubleNumber(numtodouble){
  console.log(numtodouble * 2);
  }`

This function is now ready to be used. A function is called by its name, with ingredients (**arguments**) passed in parentheses like so:

`doubleNumber(2);`

In the example above, the function just triggers an event. Sometimes, however, you need to store the result of a function. In this case the function needs to `return` a value to whatever called it. For example:

`function doubleNumber(numtodouble){
  console.log(numtodouble * 2);
  return numtodouble * 2;
  }`

`var storingNumber = doubleNumber(2);`

Here the function `doubleNumber` *returns* the result of something being doubled. This is stored in the variable `storingNumber` which called the function.

### Scoped variables

A variable created *within* a function - like `numtodouble` in the function above - only exists within that function. It cannot be accessed outside.

This is called the variable's **scope**. In many languages variables within a function are referred to as *local* variables, in contrast to *global* variables that are not created within functions and can be accessed by any part of the code.

## For loops

A for loop allows you to repeat an action *for* each item or number in a list. The loop needs the following ingredients:

* The initial value of a variable (the *initialization clause*)
* The condition that needs to be met for it to continue (*conditional clause*)
* What updates each time that it loops (*update clause*) - typically, an increment in the value of the variable
* What it does each time it loops

Here's an example which counts from 1 to 10, loops for each count, and prints the number:

`for (var i = 1; i <= 10; i = i+1) {
  console.log(i);
  }`

Here's another way of presenting the same code:

  `for (var i = 1; // set var i at 1
    i <= 10; // continue this loop while i is less than or equal to 10
    i = i+1) // change i to i+1 each time the loop runs
    {
    console.log(i); // send value of i to print in console
    }`
