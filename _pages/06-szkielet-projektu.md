---
title: 6. Project wireframe
layout: post
---

Enough with printing variables in the console, it's time to create a wireframe for our project and start working with real files!

At the very beginning, create a new folder in a location of your choice \(for example, on the desktop\). This is where we will save the files for our project. We need three files - the first one with HTML code, the second one with CSS code, and the third one with JavaScript code. We can add such files from within the editor - open the folder you created in the editor and add new files, or you can just create files directly in the location of your choice. Just remember to add appropriate extensions to them.

### HTML file

First, create a file called `index.html` and paste the following code into it:

```
<!DOCTYPE html>
<html>
   <head>
      <title>Girls.JS - Poznan</title>
   </head>
   <body>
      <h1>Hello, Girls.JS!</h1>
   </body>
</html>
```

Now double-click on the `index.html` file you have saved in the folder. It should automatically open in your browser. You should see the caption **Let's make some magic here!** and be able to go to the console. Did it work? Great! Time to add the styles.



### CSS file

In the same folder, create another folder named `css`, and inside it, create a file called `style.css`. Now we need to tell the browser where to find the styles for our HTML code. To do that, add the following line inside the `<head>` tag of the HTML code:

`<link rel="stylesheet" href="css/style.css">`

In the `style.css` file, paste the following code:

```css
h1 { 
    color: red;
}
```
Save the `style.css` file and refresh your preview of the `index.html` file in the browser. The text **Let's make some magic here!** should now appear in red. This confirms that the style file is properly linked to the HTML file. Now it's time for the most important part - the JavaScript file.

### JavaScript file

In your folder, create another folder, this time named `js`. Inside it, create a file called `app.js`. This is where we will write all our JavaScript code that will make the magic happen on our webpage ;\) To connect our script to the HTML page, add the following line just before the closing &lt;/body&gt; tag:

`<script src="js/app.js"></script>`

But how will we know if our JS file is properly connected?

**We need to check the console!**

In the `app.js` file, add the following code:

`console.log('it works!');`

Save the JS file, refresh the preview of the index.html file in the browser, and go to the console. You should see the message "it works!" there. This indicates that your JS file is working correctly, and you can proceed with the next tasks :\)



