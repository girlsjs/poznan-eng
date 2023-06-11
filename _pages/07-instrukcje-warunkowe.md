---
title: 7. Conditional instructions
layout: post
---

Some events only happen when a certain condition is met. For example, water starts boiling when it reaches a temperature of 100 degrees, and you open a door only when you have the right key. The same thing happens in the JavaScript language - a conditional statement executes a selected code depending on whether the value of a given expression is logically true \(true\) or logically false \(false\).


### if...else...

The conditional statement is structured with the **if** expression as its key element.

```js
if (condition) {

    ...command that executes when a condition is met
}
```

for example:

```js
let x = 34;

if (x < 100) {
    console.log('The number is lower than 100');
}
```

```js
 if (x < 10) {
     console.log('The number is lower than 10');
 }
```

Another element of the conditional statement is the **else** statement, which is executed when the condition is not met.

for example:

```js
let x = 34;

if (x < 100) {
     console.log('The number is lower than 100');
} else {
     console.log('The number is higher than 100');
}


if (x < 10) {
     console.log('The number is lower than 10');
} else {
     console.log('The number is higher than 10');
}
```

We can also check several conditions one by one. The **else if** is used for this:


```js
if (x < 10) {
     console.log('The number is lower than 10');
}  else if (x > 10) {
     console.log('The number is higher than 10');
} else {
     console.log('The number is equal to 10');
}
```

In your JavaScript file, create two variables named a and b. Assign two different numbers to them. Then write the following condition: if a is greater than b, the console should display the message "a is greater than b". If b is greater, you should see "b is greater than a" in the console.


### switch

**Conditions can also be checked using the `switch` command.**

```js
let language = 'Spanish';

switch (language) {
    case 'English': 
        console.log('Hello!');
        break;
    case 'French':
        console.log('Salut');
        break;
    case 'Spanish':
        console.log('Hola!');
        break;
    case 'Polish':
        console.log('Cześć!');
        break;
    default:
        console.log(`I don't know this language`);
}
```

Notice that each case ends with the keyword **break;**. Break interrupts the execution of the switch command. This means that if any of the specified cases is met, further comparisons will not be executed. If we omit this keyword, even if a successful match occurs, the next checks will still be performed. Our switch statement is concluded with a special case called **default**, which will be selected when all other cases are incorrect.

### Task:

Create a variable named `weather` in your JS file and assign the value "sun" to it. Then, using the `switch` statement, make the following text appear in the console:

* when the variable `weather` is equal to "sun" - "It's sunny! 🌞"
* when the variable `weather` is equal to "rain" = "It's raining! 🌧️"
* when the variable `weather` is equal to "wind" = "It's windy! 🌬️"

Now assign the value "rain" to the variable `weather` and see how the text in the console changes. Check the same thing by assigning the value "wind" to it.

**Instruction if..else... uses comparison operators**

Everything is not always either greater or lesser or equal. After all, it can be greater than or equal to, less than or equal to, etc. In JS, we have the following comparison operators at our disposal:

`let x = 34;`

| Operator | Description | Example | Returns |
| :--- | :--- | :--- | :--- |
| == | equal to | x == 56 | false |
| != | not equal to | x != 56 | true |
| === | equal value and equal type | x === 34 | true |
|  |  |  |  |
|  |  | x === "34" | false |
| !== | not equal value or not equal type | x !== "34" | true |
|  |  | x !== 34 | false |
| &gt; | greater than | x &gt; 67 | false |
| &lt; | less than | x &lt; 67 | true |
| &gt;= | greater than or equal to | x &gt;= 56 | false |
| &lt;= | less than or equal to | x &lt;= 56 | true |

Note that in JS, a single equals sign assigns a value to a variable, for example. The double equals sign ==, on the other hand, is a comparison of two values, or more precisely, a check to see if they are the same.

**We can also encounter logical operators:**

`let x = 34;`

`let y = 13;`

| Operator | Opis | Przykład | Wynik |
| :--- | :--- | :--- | :--- |
| && | and | \(x &lt; 100 && y &gt; 10\) | True \(x is less than 100 **i** y is greater than 10\) |
| II | or  | \(x &gt; 80 II y &gt; 10\) | True, because x is not greater than 80, but y is greater than 10 |
| ^ | xor \(one of, but not two simultaneously\) | \(x === 34 ^ y === 13\) | False, because both are true |
| ! | not | !\(x == y\) | True, because we negate  that x is equal to y |



