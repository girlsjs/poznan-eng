---
title: 13. And yet it's spinning! 🪐
layout: post
---

Copernicus stopped the Sun, and moved the Earth. We will move all 8 planets!

Download our package:  [LINK](https://drive.google.com/file/d/1nbT2_pX-eKDJi1JIGvDzoB4Tr_rCfAjk/view)

Inside, you will find the index.html, main.js, and main.css files.

When you open the index.html file in a browser, you will see 9 planet images.

Now let's take a look at this file in a text editor.

Our planets are list elements:

```markdown
<ul class="carousel">
    <li class="single-slide">…</li>
</ul>
```
As you can guess, our task is to create a carousel. We will start with its proper layout. We will use CSS styles for that, which we will include in the main.css file. To link the styles to our HTML file, we need to add another element between the &lt;head&gt;&lt;/head&gt; tags:



```markdown
<link rel="stylesheet" type="text/css" href="sciezka/do/pliku.css">
```
If you do it correctly, you should see a starry sky.

Now let's add our styles. You can find help on this website: [https://www.w3schools.com/css/](https://www.w3schools.com/css/). Don't hesitate to use Google search as well. To apply a style to specific elements, we need to refer to their class names. To do this in the CSS file, we need to write:

```css
.className {
    property: value;
}
```

for example:

```css
.carousel {
    background-color: green;
}
```
The background of the entire carousel should turn green.

Let's start by arranging the planets side by side. Each slide should have a `width` of `800px`. Set the width of the entire carousel to approximately `7300px`.

Also, let's make sure each planet is centered within slide \(`text-align: center;`\). But we still see more than one planet. So let's specify the `width` of the stage \(`.carousel-stage`\) and hide what doesn't fit inside \(`overflow: hidden;`\). Let's also center our stage \(`.carousel_stage, margin-left: auto; margin-right: auto;`\).

Now for the navigation. Do you see two arrows below the carousel? First, let's position them at the appropriate height, which is halfway up the carousel. Initially, give the carousel \(`.carousel`\) a `position: relative`. We will position the arrows relative to it. To make the arrows not appear under the carousel but "float in the air," give the navigation \(`.carousel-nav`\) a `position: absolute`. Let's place the arrows at the halfway point of the carousel's height. So, add `top: 50%` to the styles \(the navigation will then be positioned at 50% of the parent's height, which has `position: relative`\). But something doesn't quite match. The arrows are slightly too low. Exactly half their height too low. So let's apply a small transformation: `transform: translateY(-50%)`.

The next step is to place one arrow on the right and the other on the left side of the carousel. Use `float: left;` and `float: right;`, respectively.

It's time to set our planets in motion!

First, let's link the `main.js` file to our page. We do it similarly to the CSS file, but we use the `script` tag and include the path in the `src` attribute.

```markdown
<script src="sciezka/do/pliku.js"><script>
```

Go to the website, and then open the browser console. If everything is working, a message should appear.

Let's think about how our carousel should work. Imagine that it is a film strip, and at certain moments \(after clicking the arrow or after a specific time has elapsed\), the entire strip should move by the width of one frame \(which is one slide\).

So, let's go to the main.js file. Let's remove the current code. We'll start by defining our variables:

`carousel` for the carousel

`stage` for the carousel scene

`prev` for the "previous" button

`next` for the "next" button

Don't forget the keywords for defining variables \(i.e., use `let` or `const` here\).

Now, let's retrieve the HTML elements for our specified variables. We'll use the familiar `querySelector()` method, which will display the first element on the page with a specified attribute, such as a class.

```js
var carousel = document.querySelector('.carousel');
```

Download the elements for the remaining defined variables \(i.e., for our scene and two buttons\) using the same approach.

We still have one variable to define: `slide` for individual carousel elements. Here, we need to retrieve all slides, so we'll use the `querySelectorAll()` method.

Let's do the same with all elements on the page :\)

The next step is to determine the width by which our "strip" should move. As we mentioned, it's the width of one slide. Let's try to "extract" this value. We'll use the `clientWidth` property, which returns the width of the specified element. Let's try:

```js
var slideWidth = slide.clientWidth;
console.log(slideWidth);
```
Check what appears in the console. It displays a message that the value is undefined. So let's see what the variable `slide` contains. It shows a list of elements. JS cannot determine the width of the list of elements because our variable `slide` contains an array with all elements having the class `slide` that it found in the document. However, our code can handle a single element, for example, the first one. The first element in the list has an index of zero, so:

```js
var slideWidth = slide[0].clientWidth;
console.log(slideWidth);
```

The next step is to determine which slide is currently displayed. Initially, it will be the first slide, but as we know, in JS, the first element is element 0.

```js
var currentIndex = 0;
```

What happens when we reach the last element? We should go back to the first slide. So let's find the last element. First, we'll determine the total number of elements using the `length` property.

```js
var slidesNumber = slide.length - 1;
```

Where did the -1 come from? The `Slide.length` is the number of slides. which is 9. However, in JavaScript, element counting starts from 0, not 1. So the last slide won't have a value of 9 but 8.

OK, now it's time to write functions that will animate our carousel and move the entire carousel by the appropriate width. We'll use styles for this. Let's first try using CSS to move our carousel to the left by one slide, or 800px. The `position`, `left`, and `right` properties will help us with that.

Once you've accomplished that, go back to the JS file. We'll manipulate CSS values using JavaScript functions.

Let's create a function called `goToSlide()`. Its result is to be the changed value of the `left` property of our carousel. It is supposed to be enough to show the corresponding slide. A small hint - we will use the `slideWidth` variable for this and the position of the slide we want to see.

Let's start from the beginning. To change the `left` value of the carousel, we'll use the `style.left` method. This allows us to change the position of an element relative to its left edge.

```js
function goToSlide() {
    carousel.style.left = ...;
}
```
Let's think about what value `length` should have to show the second slide. What about the third and fourth slides? Do you notice any general rule?

Yes! We multiply `slideWidth` by the position of the specific slide!

So let's try:

Assume that the variable `index` represents the position of our slide. Let's define it as 3\ (position of the 4th slide\).


```js
function goToSlide() {
    carousel.style.left = 3 * (-slideWidth);
}
```

Call this function in the console.

It works!

However, there's a slight problem - we have multiple slides, each with a different `index`. Writing a separate function for each slide would be inefficient. So let's use function parameters! With that, we can use the same function for different values.

```js
function goToSlide(index) {
    carousel.style.left = index * (-slideWidth);
}
```

Let's call this function in the console by typing, for example, `goToSlide(3);` `goToSlide(1);` ` `goToSlide(4);`.

It works! The only thing is that now the `currentIndex` should also change. It should be equal to the number we entered as an argument. So let's add this change to our function:

```js
function goToSlide(index) {
    carousel.style.left = index * (-slideWidth);
    currentIndex = index;
}
```

Let's move on to navigation :\)

Clicking on the `carousel-next` button should take us to a slide with an index that is 1 higher. Clicking on the `carousel-prev` button should take us to a slide with an index that is 1 lower than the current index.

So let's create two functions. Firstly:

```js
 function slideToNext() {
 }
```

It is supposed to move the slides forward by 1 each time it is called. That is, we are using the `goToSlide()` function here. But what will be our argument? As we mentioned earlier, each call to our function is to move us to a slide with an index 1 greater than the index of the current slide. We store the index of the current slide in the `currentIndex` variable. So our argument is `currentIndex + 1`.

```js
function slideToNext() {
    goToSlide(currentIndex + 1);
}
```

Let's do an analogy with `slideToPrev`.

The next step is to call both functions when clicking on buttons. Clicks are events that take place on the page. They can be triggered by the user \(like a click\), or some element on the page. Submitting a form, loading an image, are also events. Examples of events on the page are:

| Event: | Description: |
| :--- | :--- |
| blur | object is no longer active |
| change | The object has changed its content \(e.g., a form field\). |
| click | click on the object |
| dblclick | double click on the object |
| focus | selecting an object on the site |
| keydown |pressing a key on the keyboard |
| input | while holding the key |
| keyUp | releasing a key on the keyboard |
| load | When the object has been loaded \(it can even be a whole page\). |
| mouseover | when the cursor is on a particular object |
| mouseout | when the cursor has left an object |
| contextmenu | when right clicked and context menu appeared |
| wheel | when you spin the mouse wheel |
| resize | when we resize the browser window |
| select | when the content of the object has been selected |
| submit | when the form has been sent |
| unload | user leaves the page |
| animationstart | css animation will begin |
| animationend | css animation will end|

We will use the `addEventListener` method to keep track of whether an event has taken place.

```js
element.addEventListener('event_as_string', what_should_happen, optionally_true_lub_false);
```

We will create a separate function for all events on the page. We will call it `bindEvents`:

```js
function bindEvents() {
}
```

Let's start with the back button. It is under the `prev` variable. On this variable, let's call the `addEventListener` method:

```js
function bindEvents() {
    prev.addEventListener();
}
```

And now the arguments. We want to track the `event` of the click, that is, the `click`. It is to call the `slideToPrev` function. Let's put it in the right place:

```js
function bindEvents() {
    prev.addEventListener('click', slideToPrev);
}
```

Let's add an analogous event to the `bindEvents` function for the `next` button.

Let's call the `bindEvents` function to see if the buttons work :\)

Great! However, look what will happen if we keep clicking `next` or `back`. - the planets disappear. Our carousel keeps moving 800px. We need to limit it. After the last planet, let it go back to the first one, and when we want to go back from the first one, let it show us the last planet.

Let's take another look at our function:

```js
function goToSlide(index) {
    carousel.style.left = index * (-slideWidth);
    currentIndex = index;
}
```

Everything that happens depends on the index. So let's make it so that if the index is greater than the index of the last planet, it becomes 0, and if it is less than the index of the first planet, it becomes equal to the index of the first planet.

We will use the conditional statement \(if... else\) to do this. That is, if the index is less than 0 we change it to the value of `slidesNumber`.

```js
function goToSlide(index) {
    if (index < 0) {
        index = slidesNumber;
    }

    carousel.style.left = index * (-slideWidth);
    currentIndex = index;
}
```

And if it is greater than `slidesNumber` - we change it to 0.

```js
function goToSlide(index) {
    if (index < 0) {
        index = slidesNumber;
    } else if (index > slidesNumber) {
        index = 0;
    }

    carousel.style.left = index * (-slideWidth);
    currentIndex = index;
}
```
Let's check it out now.

Add some more life to the carousel - let it spin on its own. We'll use the already familiar `setInterval` method for this.

We should create an `autorotate` function.


```js
function autorotate() {
}
```

Let the `slideToNext` function be executed every 4s \(4000 ms\):

```js
function autorotate() {
    setInterval(slideToNext, 4000);
}
```

And let's call the `autorotate` function.

And now everything is spinning! :\)

