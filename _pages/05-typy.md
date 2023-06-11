---
title: 5. Types
layout: post
---

`sum` with a value of 99 is a variable of type \(**number**\). In addition to numbers, JS also uses other data types:

**string** - a string of characters. They are written in quotation marks or apostrophes, e.g. 'JS programmers are cool'

**variable of logical type \(boolean\)**- true \(logical truth\) lub false \(logical false\)

**null**- meaning an empty object

**undefined**- undefined value


To check the type of a variable, you can use `typeof`, for example, `typeof sum`.


Now, try creating a variable with your name. In the console, type `let name = "enter your name here";`. Then, write `console.log(name);`. You should see your name in the console. Check the type of your `name` variable by typing `console.log(typeof name);` in the console.

Spróbuj teraz stworzyć zmienną ze swoim imieniem. W konsoli wpisz `let name = "tu podaj swoje imię";` Następnie napisz `console.log(name);`. Powinnaś zobaczyć swoje imię w konsoli. Sprawdź jakiego typu jest Twoja zmienna `name` przez wpisanie w konsoli `console.log(typeof name);`



### Numbers and Operators

We can perform mathematical operations on numbers using operators, as shown in the table below.

Let's assume we have following variables:

```js
let y = 8;

let z = 4;

```

|  | Operator | Equation | Result |
| :--- | :--- | :--- | :--- |
| + | Addition | x = y + z | x = 12 |
| - | Subtraction | x = y - z | x = 4 |
| \* | Multiplication | x = y \* z | x = 32 |
| / | Division | x = y / z | x = 2 |
| % | Remainder | x = y % 3 | x = 2 |
| ++ | Increment | x = ++y | x = 9 |
|  |  | x = y++ | x=8; y = 9; |
| -- | Decrement | x = --y | x = 7 |
|  |  | x = y-- | x = 8; y = 7 |

Now, try writing a few of these operations in the console. First, create two arbitrary number variables, and then use `console.log` to print the results of the operations in the console.

### Strings

**We can also perform certain operations on strings, for example we can add them to each other \(this is called concatenation\).**

```js
let text_1 = "Hello";
let text_2 = "Jack";
let text_3 = text_1 + ', ' + text_2 + '!'; // Hello, Jack!
```

Create a variable named `surname` and assign it your last name. Then, define another variable named `fullName` and make its value your two previous variables, so your name and surname, separated by a space. Print the value of the `fullName` variable in the console.

**The `length` property is used to determine the length of a string.**

```js
text_3.length; // 12
```

Check the lengths of three of your string variables \(`name`, `surname`, `fullName`\) by printing them in the console.

**We can also change the case of characters in a string to uppercase or lowercase:**

```js
text_3.toUpperCase(); // HELLO, JACK!
text_3.toLowerCase(); // hello, jack!
```

Make your name in the `name` variable uppercase.

**Another method is to check the position of a substring within a string:**

```js
text_3.indexOf('Jack'); // 7
```

Find out the position of the letter 'a' in your first name.

**We can also replace parts of a string:**

```js
text_3.replace('Jack', 'Mary');
```

This will replace the first occurrence of the given string \(in our case 'Jack'\) with a new string \('Mary'\).

### Task

Create a variable named `hello` and assign the following text to it: "Hello, \[enter your name\]!". Then, using the `replace` method, modify the text to look like this: "Hello, JavaScript!".

