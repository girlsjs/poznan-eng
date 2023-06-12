---
title: 8. Loops
layout: post
---

Let's say we want to do something multiple times, for example, send the same message five times or assign an identifier to the next 30 books in our book collection. Repeating the same action multiple times is not very efficient. That's where we can use loops. To repeat something multiple times, we need a counter - to know where we are and whether we should finish or continue repeating the given script.

For instance, let's assume that we want to write the message "Hi, we are happy to welcome you to girls.js!" five times in the console. We can do it this way:

```js
console.log("Hi, we are happy to welcome you to girls.js!");
console.log("Hi, we are happy to welcome you to girls.js!");
console.log("Hi, we are happy to welcome you to girls.js!");
console.log("Hi, we are happy to welcome you to girls.js!");
console.log("Hi, we are happy to welcome you to girls.js!");
```

That's a lot of typing, right? We can simplify this code!


### The for Loop

The for loop looks like the following:

```js
for (counter initialization; condition to check whether to finish the loop or not; increase/decrease the counter) {
    code to repeat a certain number of times
}
```

Let's modify our code with the message!

counter initialization - we start from 0, so we create a variable \(which exists only for the loop\) as follows:

`let i = 0;`

end of the loop - we repeat the action until the counter reaches 5, which is:

`i <= 5;`

increasing/decreasing the counter - after each loop iteration, our counter increases by one, so:

`i += 1`

Therefore, the loop will look like this:

```js
for (let i = 0; i <= 5; i += 1) { 
     console.log("Hi, we are happy to welcome you to girls.js!");
}
```

We can also decrease the counter. Since we want the message to be repeated five times, we can write it like this:

counter initialization - we start from 5, so `let i = 5;`

end of the loop - repeat until we reach 0, that is, until `i` is greater than zero,`i > 0;`

increase/decrease counter - each loop counts down from five, i.e. `i -= 1;`


```js
for (let i = 5; i > 0; i -= 1) {
  console.log("Hi, we are happy to welcome you to girls.js!");  
}
```

Try writing the above loop in your JS file. Make sure the code repeats 10 times.

It's time for our books! Let's remember - we want to assign an identifier (id) to the next 30 books.

We can do it like this:

```js
console.log("id-1");
console.log("id-2");
console.log("id-3");
console.log("id-4");
console.log("id-5");
console.log("id-6");
....
console.log("id-30");
```

But such code would take up a lot of space. So let's use loops! Notice that this time we are repeating the same action, but the string we want to display is changing. It increases exactly by 1. Our counter behaves in a similar way!
Check what happens when you try to display the value of our counter in the console \(since it's a variable, simply enter its name\).

```js
for (let i = 0; i < 30; i += 1){
  console.log(i);
}
```
The console displayed numbers from 0 to 29. After all, we start counting from 0 and repeat the code as long as it is less than 30. When it reaches 30, we stop the loop. Therefore, we need to slightly modify our loop. Our id starts from 1, and we repeat the loop as long as the elements are less than **or equal** to 30.

```js
for (let i = 1; i <= 30; i += 1) {
  console.log(i);
}
```
Great! Now let's add the missing id element, which is the string "id-". We can use concatenation for this. When we add a string to a number, JavaScript converts the whole thing into a string!

```js
for (let i = 1; i <= 30; i += 1) { 
     console.log("id-" + i);
}
```

### Task

Use the above loop to assign ids to 50 books. Write the code in your JS file.


### The while Loop

Aside from the `for` loop in JavaScript, there is a `while` loop, the structure of which looks like this:

```js
while (expression that checks if the loops should be executed further) {
    the code you want to repeat as long as the condition in parentheses is met
}
```

The `for` loop is executed a specific number of times. The while loop runs as long as the expression in parentheses is true.
However, notice that this loop doesn't have a counter. That's why it's often added manually. Let's go back to our message for 5 people:

```js
let counter = 0;
while(counter < 5) {
    console.log("Hi, we are happy to welcome you to girls.js!");  
    counter += 1;

}
```

We define the variable that serves as our counter outside the loop. With each iteration, we increase the counter by 1.

### Task

In your JS file, write a `while` loop that writes "JavaScript is awesome!" in the console 10 times.


