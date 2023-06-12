---
title: 4. Variables
layout: post
---

In the previous chapter, we entered a simple mathematical operation 33 + 5 in the browser console. However, if we wanted to use the same equation multiple times in different parts of the code, it would be very inconvenient. That's why we use variables. A variable is a name defined by us with a specific value. Variables allow us to store pieces of code that we can use later. In a variable we can store, for example, the result of an equation that we just recalled.

How to define such a variable?

```js
var sum = 33 + 5;
```

`var` is the keyword that defines a variable. `sum` is the name of our variable. `33 + 5` is the operation whose result will be the value of our variable. When we enter `var sum = 33 + 5;` in the console and then type `sum`, the console will return 38. From now on, for the JavaScript language `sum` is the same as `38`.

### var

`var` comes from the English word "variable" and represents a variable. Every variable definition consists of the keyword `var` followed by the name of the variable. Variable names can consist of letters, numbers, and certain special characters, usually starting with a lowercase letter. Variable names should be meaningful, i.e., instead of naming variables as `xyz`, we should use names like `sum`, `result`, etc. This way, it will be easier to navigate our code.

Just because we assigned a value to a variable doesn't mean that it must always remain the same. We have the ability to overwrite that variable by assigning it a new value. For example, we can simply write `sum = 99`. From that point on, `sum` in JavaScript will represent the value 99. When we overwrite the value of a variable, we don't write `var` before its name. We only use `var` when defining the variable for the first time. Afterwards, we simply use the variable's name.


### let and const

Currently, the ES6 standard is also being used, which is a newer version of the JavaScript language. According to this standard, variables can be created using the keywords `let` or `const`.

If we create a variable using `let`, we can assign it a value any number of times, i.e., we can overwrite it \(similar to var discussed earlier\). In that case, we can have code like this:

```js
let sum;
sum = 15;
sum = 20;
```

On the other hand, when we create a variable by `const`, it is fixed and we cannot assign it a different value than the one we assigned at the very beginning. Trying to assign `const` a new value will cause us to see an error in the console.

```js
const sum = 15;
sum = 20; // wyświetli błąd w konsoli z informacją TypeError: Assignment to constant variable.
```

Using `let` and `const` in our code is very useful because it allows us to distinguish between values that can be overwritten and those that must remain the same throughout the code. For example, let's say we have a converter that always has the same value. We can use `const` to define it and ensure that its value is not overwritten.

Considering the benefits that the differences between `let` and `const` provide, it is good to use them in our code instead of creating all variables using `var`.

### Task

Create two variables in the console with arbitrary numbers. 
One using `let` and the other using `const`. 
Try overwriting both values and see what is displayed in the console.


