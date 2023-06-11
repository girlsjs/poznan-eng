---
title: 3. Konsola przeglądarki
layout: post
---


To start your journey with JavaScript, it's worth getting familiar with the browser console. This is the place where you are able to quickly test the code, but also find information about errors that have occurred. In Chrome browser, you can open the console using Ctrl+Shift+J, and in Firefox, you can use Ctrl+Shift+K. In both browsers, the F12 key would work as well ;) Alternatively, you can right-click anywhere on an open page, select "Inspect" and then navigate to the "Console" tab when the developer tools open.

![](/poznan/assets/devtools.png)

Type `console.log('Hello World!');` in the console and press Enter. 
Your message should be displayed below. Now, enter `console.log(33+5);`.

You have just performed your first JavaScript operations!

Note that anything you enter directly into the console \(within the browser\) won't be saved. However, it is very useful when you want to check the values of variables, for example. When you want something to be continuously displayed in the console, you'll need to enter the code in your JavaScript file and then check the console. The console is a very important tool when working with code. It allows us to check if we have assigned values to variables correctly, if our functions are working correctly, and so on. But first, let's move on to the page content!

Now, let's go to the "Elements" tab. Here, you can see the entire structure of your page, which includes the HTML and CSS code. HTML is responsible for the frame of our page, i.e. it tells the browser what elements are to be on the page \(e.g., headers, images, text blocks\). CSS, on the other hand, is responsible for the appearance of elements. CSS rules define properties such as the color of a header.

![](/poznan/assets/elements.png)

Right-click on any element of the page and choose "Inspect". Now you can easily find it in the page structure. When you hover over a part of the HTML code, the corresponding element will be highlighted. This allows you to easily identify which part of code is responsible for the selected elements.

![](/poznan/assets/code-part.png)

Here you should also find the "Styles" tab, where you can see all the styles applied to the element you just selected.

![](/poznan/assets/styles.png)

For example, the highlighted text **KOBIECA STRONA JAVASCRIPTU** has the following styles:  
`background: #ffc303;`  
`padding: 2px 10px;`

Let's change the `background` value to `red`;

![](/poznan/assets/bg-red.png)

The background of our text has changed color! It's worth noting that these changes are not permanent. If we refresh the browser now, our color change will disappear. Such modifications directly in the browser are used to check how our page would look with specific CSS styles. To make our header have a red background all the time, we would have to make a change in the code file.
