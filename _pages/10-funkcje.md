---
title: 10. Functions
layout: post
---

Sometimes we want to perform similar actions for different values. For example, we want to paint the entire house and need to calculate the wall area for each room. We have rooms with different dimensions, but the calculation process will be exactly the same:

We're painting a room with dimensions 6m x 5m and a height of 2.5m.

We add up the widths of the walls: 2*6 + 2*5 = 22

We calculate the wall area: 22 × 2.5 = 55

We calculate the ceiling area: 6 × 5 = 30

We add the wall and ceiling areas: 55 + 30 = 85

And we repeat this for 7 different rooms in our house. But we can simplify this. After all, we want to do something like this:


```js
let x = first_wall;
let y = second_wall;
let z = height;
let wallsWidth = 2*x + 2*y;
let wallsSurf = wallWidth * height;
let ceilingSurf = x * y;
let painting = wallsSurf + ceilingSurf;
```

Our variable elements are x, y, and z.

To perform such actions, we can use a function. The function definition looks like this:

```js
function functionName() {
    what should happen;
}

For example:
function greeting() {
    console.log('Hello World!');
}
```

Now we need to call the function:

```js
functionName();
greeting();
```

Each time the function is called, it will do the same thing.

But what about our variable parameters? Well, we define those parameters in parentheses after the function name. For example:

```js
function greeting(name) {
    console.log('Hello ' + name);
}
```

When calling the function, we need to provide the actual data in place of the parameter. For example:

```js
greeting('Marta');
>>> Hello Marta
greeting('Ania');
>>> Hello Ania
```

Let's go back to calculating the surface area. Our variable parameters are the width of one wall, the width of the second wall, and the height. So it looks like this:

```js
function paintingSurface(wall1, wall2, height) {
    ....
}
```

Now, let's define the content of our function:

```js
function paintingSurface(wall1, wall2, height) {
    var x = wall1;
    var y = wall2;
    var z = height;
    var wallsWidth = 2*x + 2*y;
    var wallsSurf = szer_scian * height;    
    var ceilingSurf = x * y;
    var paintingSurf = wallsSurf + ceilingSurf;

    console.log(paintingSurf)
}
```

And call the function:

```js
paintingSurface(6, 5, 2.5);
paintingSurface(3, 4, 2.5);
```

### Task:

In your JS file, create a function named `helloGirlsJS` that, when called, displays the following message: "Hi \[here it will output the name of the person given in the function call\]! We are happy to welcome you to girls.js!".


