---
title: 11. DOM
layout: post
---

DOM, which stands for **Document Object Model**, allows the JavaScript language to represent the structure of an HTML page.

In the developer tools, let's go back to the "Elements" tab. There, you can see the entire page. But how can we refer to an element using JavaScript?

Let's go back to the "Console" tab. We can refer to HTML elements using:

- **id** - `getElementById`

- **tag** \(e.g. div, p, ul\) - `getElementsByTagName`

- **class** - `getElementsByClassName`

- **selector** - `querySelector` i `querySelectorAll` \(the first one returns the first matching element, and the second one returns all matching elements\)

Now, let's try to store the header element from the page you're working with in a variable. You'll notice that in the `index.html` file, there's an `<h1>` tag with some content. Retrieve that element into a variable using the `querySelector` method. To make this method work, you need to call it on the HTML document, which is `document`, and then provide the chosen selector inside parentheses. Your code should look like this:  

`let header = document.querySelector("h1");`

Now, print this variable in the console and check if the HTML element has been stored in it. What do you see?

Once we know how to retrieve elements into variables, we can move forward! 

🪄 It's time for some magic!

