---
title: 12. Let's make some magic! ✨ 
layout: post
---

Let's try to liven up our website and add some color to it.

Let's create our first function in the project!

In your JS file, we will define the following function:


```js
function getRandomColor() {
    console.log('Lets draw a color!')
}

getRandomColor();
```

Let's refresh our webpage in the browser, go to the console, and see what happened.

Our message appears. It's time to search for colors!

On most websites, colors are represented in hexadecimal format. For example, #FFFFFF represents white, #000000 represents black, and #FFA500 represents orange. As you can see, each color starts with the symbol '#' followed by 6 characters (letters A-F and/or digits 0-9). To create a random color, we need to randomly combine these characters.

Let's start by creating a variable that contains all the possible characters:

```js
var letters = '0123456789ABCDEF';
```

Our second variable will be the color. Its only constant element is the '\#' symbol, so for now, it will only contain that symbol:

```js
var color = '#';
```

Later on, we will add random letters from the letters variable to it.

The getRandomColor\(\) function should now look like this:

```js
function getRandomColor() {
    var letters = '0123456789ABCDEF';
    var color = '#';

}
```
Now we want to extract random letters from our letters variable and create a string consisting of 6 characters. The easiest way to do this is to extract random characters from letters 6 times. We can use a loop for this.

```js
function getRandomColor() {
    var letters = '0123456789ABCDEF';
    var color = '#';

    for (var i = 0; i < 6; i++) {

    }
}
```
Let's try to understand it:

For each i, which starts with the value zero and is less than 6, execute the command inside the curly braces, and then increment i by 1.

As you probably guessed, 6 comes from the fact that we need to extract each letter of our letters string 6 times. So let's start the randomization.

To extract an element from a list, we need to provide its index. Importantly, counting of list elements starts from zero. Looking at our variable:

```js
var letters = '0123456789ABCDEF';
```

To extract the first element \(which is the digit 0\), we need to write letters\[0\].

To extract the letter B, we use letters\[10\]. Okay, but what about our randomization?

JavaScript has a built-in object called **Math**, which contains properties and methods related to mathematical functions and constants. For example, Math.PI will return us the value of the number Pi. You can find more about the Math object [here](https://developer.mozilla.org/pl/docs/Web/JavaScript/Referencje/Obiekty/Math). 

One of the methods in the Math object is the random\(\) method, which returns a random value between 0 and 1. Let's try it! Type Math.random\(\) multiple times in the browser console.

However, we want to generate a whole number between 0 and 16. So let's multiply our random value by 16:

```js
Math.random()*16;
```

We're getting closer. Now, we need whole numbers, not fractions. This is where another method of the Math object comes to help, floor\(\), which rounds numbers down to the nearest whole number. Let's try it in the console:

```js
Math.floor(14.567);
Math.floor(-1.38);
```

Our goal, however, is to round the result of random number generation between 0 and 16, which is:

```js
Math.floor(Math.random() * 16);
```

We will perform this randomization 6 times. Therefore, we should include this process inside our loop. Let's assign it to a variable:

```js
 function getRandomColor() {
    var letters = '0123456789ABCDEF';
    var color = '#';

    for (var i = 0; i < 6; i++) {
       var randomNumber = Math.floor(Math.random() * 16);
    }
}
```
The next step is to extract the letter at the randomized position from our letters string. If we wanted to extract the letter 'A', we would write

```js
letters[10]
```

However, at each loop iteration, we want to extract the letter that is currently stored in the variable randomNumber. Therefore, instead of 10, we will use randomNumber. For clarity, let's assign this value to a variable:

```js
function getRandomColor() {
    var letters = '0123456789ABCDEF';
    var color = '#';

    for (var i = 0; i < 6; i++) {
        var randomNumber = Math.floor(Math.random() * 16);
        var randomLetter = letters[randomNumber];
    }
}
```

Let's see what happens when we display the randomly generated letter:

```js
function getRandomColor() {    
    var letters = '0123456789ABCDEF';
    var color = '#';

    for (var i = 0; i < 6; i++) {
        var randomNumber = Math.floor(Math.random() * 16);
        var randomLetter = letters[randomNumber];
        console.log(randomLetter);
    }
}
```

And let's call our function:

```js
function getRandomColor() { 
    var letters = '0123456789ABCDEF';
    var color = '#';

    for (var i = 0; i < 6; i++) {
        var randomNumber = Math.floor(Math.random() * 16);
        var randomLetter = letters[randomNumber];
        console.log(randomLetter);
    }
}

getRandomColor();
```
We have random letters from letters! However, we want to add them to the color variable in order to obtain a color. We can achieve this by appending a new letter to the existing color value:

```js
function getRandomColor() {    
    var letters = '0123456789ABCDEF';
    var color = '#';

    for (var i = 0; i < 6; i++) {
        var randomNumber = Math.floor(Math.random() * 16);
        var randomLetter = letters[randomNumber];

        color += randomLetter;
    }
    console.log(color);
}

getRandomColor();
```

Great! But we don't want to display the color, we only want to return it so that we can use it in the future.

The `return` statement is used to return a value:

```js
function getRandomColor() {       
    var letters = '0123456789ABCDEF';
    var color = '#';

    for (var i = 0; i < 6; i++) {
        var randomNumber = Math.floor(Math.random() * 16);
        var randomLetter = letters[randomNumber];

        color += randomLetter;
    }

    return "#" + color;
}

getRandomColor();
```

We have a random color! Now we need to assign it to the text styles.

To separate different elements of a webpage, we use different tags. For example, we place the content of paragraphs between  &lt;p&gt;&lt;/p&gt; tags. &lt;div&gt;&lt;/div&gt; represents a block or a section. &lt;table&gt;&lt;/table&gt; is used for tables. &lt;ul&gt;&lt;/ul&gt; represents an unordered list, and &lt;ol&gt;&lt;/ol&gt; represents an ordered \(numbered\) list. &lt;li&gt;&lt;/li&gt; represents individual list items. &lt;h1&gt;&lt;/h1&gt;, &lt;h2&gt;&lt;/h2&gt;, &lt;h3&gt;&lt;/h3&gt;, &lt;h4&gt;&lt;/h4&gt;, &lt;h5&gt;&lt;/h5&gt;, &lt;h6&gt;&lt;/h6&gt; are heading tags of different levels. Some elements can be nested inside others. Some of them can appear multiple times on a page. To reference specific elements, we assign them an id \(unique to one element\) and a class \(which can be shared by different elements\). For example:

```
<p id="magic" class="title">Let’s make some magic!</p>
```

Let's place this text on our webpage between the tags and give it an id.

Now let's go back to our JS code. To find an element with a specific id on the page, we use the document.getElementById\(\) method. We provide the id name within the parentheses. It's a good practice to assign this element to a variable.

```js
var title = document.getElementById('magic');
```

Now let's create another function responsible for changing the text color.

```js
function changeColor() {

}
```

To change the color, we access the style object. If we type:
```js
console.log(title.style)
```
JavaScript will display all the properties of the style object. [ There ] (https://www.w3schools.com/jsref/dom_obj_style.asp) you will find an ordered list. What we need is the color property.

```js
function changeColor() {
    title.style.color
}
```

Additionally, we want to change this property by assigning it a new value, similar to changing the value of a variable.

```js
function changeColor() {
    title.style.color = new_kolor;
}
```

Our new color will be generated when the getRandomColor function is called:


```js
function changeColor() {
    title.style.color = getRandomColor();
}
```
Let's invoke the changeColor function and refresh our webpage multiple times.

But wouldn't it be better if our function could be reused and assigned to different elements on the page, not just the title?

If we decide to do that, we need to assign a parameter to our function. We include it in parentheses after the function name.

```js
function changeColor(text) {
}
```
Now the command to change the color needs to be assigned not to the title variable but to the function parameter that will change.

```js
function changeColor(text) {
    text.style.color = getRandomColor();
}
```

Now, when calling the function, we need to replace the parameter with an existing element on the page.

```js
changeColor(title);
```
But we're not done yet! Our text can have any color, but let's make it even more interesting. Let's change the color every 2 seconds!

To achieve this effect, we need to call our changeColor\(title\); function every two seconds.

We can use the setInterval\(\); method for that. It looks like this:

```js
setInterval(function() { 
    what_should_happen; 
}, coJakiCzas);
```

We measure time in milliseconds. 2 seconds is equal to 2000 milliseconds. So:


```js
setInterval(function() { 
    changeColor(title); 
}, 2000);
```

✨ Magic is happening! ✨ 

