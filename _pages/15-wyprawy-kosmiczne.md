---
title: 15. Space expeditions
layout: post
---

Programmers are changing the world. Their work is essential for space exploration. Let's try it ourselves :D

Since we haven't been able to send anyone into space yet, we will use the help and resources of NASA.

## What's happening on Mars?

First, we need to obtain an access key. We can do it here: [https://api.nasa.gov/index.html\#apply-for-an-api-key](https://api.nasa.gov/index.html#apply-for-an-api-key).

It will help us access the resources provided by NASA. You can find their list here: [https://api.nasa.gov/api.html\#how-do-i-see-my-current-usage?](https://api.nasa.gov/api.html#how-do-i-see-my-current-usage?)

Let's start with the picture of the day :\)

When you visit this address: [https://api.nasa.gov/planetary/apod?api\_key=DEMO\_KEY](https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY) you will see... an object. 

We have the date, description, addresses to photos in two sizes, type and title. We are going to create a page with the photo of the day as the background. Let's see what it is today :D


To get started, download the HTML, CSS and JS file package, which is available [HERE](https://drive.google.com/open?id=1HEAG_bmuEWIsIX939rXJP3xV-8PFj-0F).

We will start by changing the body background to an image. In CSS, `background-image` is used for this. To change the background using JS we will create a function whose argument will be the path to the image:

```js
function changeBackground(imageURL) {

}
```

We will use the `style` property, which we already know. In the list of all styles there is also `backgroundImage`. This is where we will assign the address to our image.

By default, it would look like this:

```js
document.body.style.backgroundImage = "url('img_unicorn.png')";
```

But our image address will change, and it will take the value we enter as an argument to the function, so:

```js
function changeBackground(imageURL) {
    document.body.style.backgroundImage = "url('" + imageURL + "')";
}
```

Now it's time to connect to the NASA api!

To start with, we will create a variable with the URL where the object with our image is hidden. Instead of DEMO_KEY, we will enter our key.

```js
let dataURL = 'https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY';
```

Now let's create a function `getPicture`. Inside it, we will write code that will retrieve data from the address indicated under `dataURL`. For this we will use the `fetch API` - a tool for dynamic data retrieval. This is fairly new and supported by new browsers.

We will try it one by one:

```js
function getPicture() {
    fetch(dataURL)
    .then((resp) => {
        console.log(resp);
    })
}
```

After running `fetch` it returns us a Promise. Promises allow us to control the order of the code execution. If any promise is fulfilled the next piece of code starts running \(then\). If there is something at the `dataURL` address, we access the response from that page and display it.

Another new element is the arrows `=>`. This is a simpler notation of the functions we know. Our function has one argument \(`resp`\) and this argument displays in the console. Let's call the function and look at our console. In it we have the response from the server. Let's convert it to a friendlier format, such as json. Most often, data in JSON format is taken from the server as text and then converted into an object. To convert our response from the server, let's add the `json()` method to it.

```js
function getPicture() {
    fetch(dataURL)
    .then((resp) => {
        return resp.json();
    })
}
```

This is also a Promise. Once it is fulfilled, we should be able to display our object. Let's check it out.

```js
function getPicture() {
    fetch(dataURL)
        .then((resp) => {
            return resp.json();
        })
        .then((data) => {
            console.log(data);
        });
}
```

We have our object! However, we are interested in a specific element: `hdurl`. Remember how we display a given value in an object? Exactly - by referring to the key.

```js
function getPicture() {
    fetch(dataURL)
        .then((resp) => {
            return resp.json();
        })
        .then((data) => {
            console.log(data.hdurl);
        });
}
```

And there is our url, which we should use as an argument in the `changeBackground` function:

```js
function getPicture() {
    fetch(dataURL)
        .then((resp) => {
            return resp.json();
        })
        .then((data) => {
            changeBackground(data.hdurl);
        });
}
```

Do we already know what the photo of the day is?

### On to conquering Mars!

Now let's take the next step. Let's see what's happening on Mars. We will use the rover, which bravely captures its daily adventures, and you can find the data from those expeditions at this link: [https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?sol=1000&api\_key=DEMO\_\_KEY](https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?sol=1000&api_key=DEMO__KEY)

You can see that there are many more objects waiting for us under that link than a moment ago. Let's make use of them!

Let's start by assigning our URL to a variable:

```js
let urlMars = "https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?sol=1000&apikey=DEMO_KEY";
```

Let's create a new function that will use the familiar `fetch API`:

```js
function getMarsPicture() {
    fetch(urlMars)
        .then((resp) => {
            return resp.json();
        })
        .then((data) => {
            console.log(data);
        });
}
```
Let's call the function and see what happens in the console. We have an object with the key `photos` (it might have taken a while for something to appear in the console). Let's check what's inside, that is, under the `photos` key:

```js
function getMarsPicture() {
    fetch(urlMars)
        .then((resp) => {
            return resp.json();
        })
        .then((data) => {
            console.log(data.photos);
        });
}
```

Inside we have an array of objects. Now let's check how many objects there are:

```js
function getMarsPicture() {
    fetch(urlMars)
        .then((resp) => {
            return resp.json();
        })
        .then((data) => {
            console.log(data.photos.length);
        });
}
```

A lot! Now let's see what's inside the first object:

```js
function getMarsPicture() {
    fetch(urlMars)
        .then((resp) => {
            return resp.json();
        })
        .then((data) => {
            console.log(data.photos[0]);
        });
}
```
That's closer to what we expect. We can make something out of something like this :\) We have an object, inside it is the key `img_src` with the address of the image. We will use it. Let's make a gallery on our page. It will be located in a `div` tag with ID `content`. So let's create a variable:

```js
let gallery = document.getElementById('content');
```
Now let's create a function called `createGallery` with the argument `dataList`. It will be the long array we extracted from `data.photos`:

```js
function createGallery(dataList) {
}
```

Inside the function, we will use a loop to create 9 images and add them to the page. In HTML, we display an image using the `img` tag:

```markdown
<img src="image_address" class="class/classes" alt="text_if_image_not_available">
```

That's how it looks in HTML. How can we do it using JavaScript? Let's start with a loop that will iterate 9 times:

```js
function createGallery(dataList) {
    for(let i = 0; i < 9; i++) {

    }
}
```

Each time, we will create a new element and assign it to the variable img. We create a new element using:

```js
document.createElement('tag_name');
```

In our case, the tag name is `img`, so:

```js
function createGallery(dataList) {
    for(let i=0; i < 9; i++) {
        let img = document.createElement('img');
    }
}
```

The next step is to insert a new element into the `content` div. This can be done using the `appendChild('name_insert_element')` method.

```js
function createGallery(dataList) {
    for(let i=0; i < 9; i++) {
        let img = document.createElement('img');
        gallery.appendChild(img);
    }
}
```

Let's check our page.

We're missing the image paths. Let's go back to the `getMarsPictures` function. We had an array with many objects inside, and each object had the `img_src` we needed. Let's assign our array to a variable:

```js
function getMarsPicture() {
    fetch(urlMars)
        .then((resp) => {
            return resp.json();
        })
        .then((data) => {
            let pictureList = data.photos;
        });
}
```

We have the list that we will use in the `createGallery` function. So let's call `createGallery` with this argument inside the `getMarsPicture` function:

```js
function getMarsPicture() {
    fetch(urlMars)
        .then((resp) => {
            return resp.json();
        })
        .then((data) => {
            let pictureList = data.photos;
            createGallery(pictureList);
        });
}
```
Okay, but what is hiding under our `pictureList`? Let's check it using `console.log`. In the `createGallery` function, let's display our `dataList` argument in the console. Now let's call the `getMarsPicture` function. Inside it, we also call the `createGallery` function:

```js
function createGallery(dataList) {
    for(let i=0; i < 9; i++) {
        let img = document.createElement('img');
        gallery.appendChild(img);
        console.log(dataList);
    }
}
```

We have 9 arrays, and each contains our objects. But for each loop iteration, we only need 1 object. The object with an index that matches ours. Therefore, let's display only objects with an index equal to `i`:

```js
function createGallery(dataList) {
    for(let i=0; i < 9; i++) {
        let img = document.createElement('img');
        gallery.appendChild(img);
        console.log(dataList[i]);
    }
}
```

We're closer now - we have 9 objects. But we only need the value that is hidden under `img_src`, so let's display it:

```js
function createGallery(dataList) {
    for(let i=0; i < 9; i++) {
        let img = document.createElement('img');
        gallery.appendChild(img);
        console.log(dataList[i].img_src);
    }
}
```

Getting better. Now, instead of displaying it, let's assign it to a variable and move it before adding `img` to `gallery`:

```js
function createGallery(dataList) {
    for(let i=0; i < 9; i++) {
        let img = document.createElement('img');
        let imgPath = dataList[i].img_src;
        gallery.appendChild(img);
    }
}
```

Now, how do we add `imgPath` to our `img` element? By using the `src` attribute. It's similar to the `style` attribute. We need to assign a value to it:

```js
function createGallery(dataList) {
    for(let i=0; i < 9; i++) {
        let img = document.createElement('img');
        let imgPath = dataList[i].img_src;
        img.src = imgPath;
        gallery.appendChild(img);
    }
}
```

Now let's call the `getMarsPictures` function and see what's happening on Mars!


