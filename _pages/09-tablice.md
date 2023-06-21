---
title: 9. Arrays
layout: post
---

Variables you have learned so far have contained only one element - a string, a number, or a boolean value. However, sometimes we need to work with a whole list of data. Arrays are used to store such data.

```js
let array = ["orange", 34, true, "mandolin", 45 [67, 56, "red"]];
```

We create an array by enclosing the data in square brackets and separating the elements with commas. In an array, we can store different types of data: strings, numbers, boolean variables, and even other lists.

Let's create a list of friends, for example:

```js
let friends = ["Michał", "Marta", "Mikolaj", "John", "Natalia", "Ania"];
```

To display an element from the list, we refer to the list and the position of the desired element.


NOTE!

The order of elements starts from 0. So:


```js
console.log(friends[0]);
>>> Michał

console.log(friends[3]);
>>> John
```

In your JS file, create an array called "group" that contains the names of all the people you're working with in the workshop. Then, print the name of the first person in the console.

Similar to strings, we can determine the length of an array using the **length** property.

```js
console.log(friends.length); 
>>> 6
```

Now, print the length of the array containing the names of people in your group to the console. Then, log the name of the person who is listed as the last one.

To add a new element, we use the **push** method:

```js
friends.push('Kasia');

console.log(friends);
>>> ["Michał", "Marta", "Mikolaj", "John", "Natalia", "Ania","Kasia"]
```
Using this method, we add a new element to the end of the array.

Add another random name to your "group" array using the `push` method, and then print it to the console.

We can also overwrite an existing element in the array at a specific position:

```js
friends[2] = "Tomek";

console.log(friends);
>>> ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia"]
```

Overwrite the most recently added name in your "group" array with a different one. Once again, print the last name to the console.

We can combine different arrays. Create an array with the names of friends from work and another array with the names of friends from parties.

To create an array that contains the names of all your friends, we will use the `concat` method:

```js
let work_friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia"];
let party_friends = ["Asia", "Kamil", "Bartek", "Ola", "Weronika", "Czarek"];

let all_friends = work_friends.concat(party_friends);

console.log(all_friends);
>>> ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia", "Asia", "Kamil", "Bartek", "Ola", "Weronika", "Czarek"]
```
Check the console to see how the new array created using `concat` looks.

To "extract" a portion of an array, we use the `slice` method. It requires specifying from which element to start and on which element to end.

```js
let friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia"];

let part = friends.slice(1, 4);
console.log(part);
>>> Marta, Tomek, John
```
Now, create another array whose elements will be the first and second name from the "group" array. Use the `slice` method for this.

The `splice` method is used to remove or replace a portion of an array.

```js
array.splice(from which element, how many elements to remove, what to put there in change)

let friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia"];

friends.splice(2,1);
console.log(friends);
>>> Michał, Marta, John, Natalia, Ania, Kasia,
```

In this example, I start at position 2, remove one element, and do not add any new elements.


```js
let friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia"];

friends.splice(2, 0, "Patrycja");
console.log(friends);
>>> Michał, Marta, Patrycja, John, Natalia, Ania, Kasia,
```
I start with the element in the second position, remove one element, add the element "Patrycja".

Now, using `splice`, remove the first name from the "group" array and replace it with another arbitrary name.
**NOTE:** `friends.slice` does not modify the friends array; it only returns specific elements. `friends.splice` modifies the `friends` array. This is an important distinction.


### Searching for an Element

The `indexOf` method is used to search for the position of an element. It returns the index of the given element or -1 if it is not found.

```js
let friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia"];

if (friends.indexOf('Marta') !== -1) {
    console.log('Marta can be found in this array!');
} else {
    console.log('Marta cannot be found in this array!');
}
```

Using `indexOf()`, check the position of your name in the "group" array.

### Looping through an array

A loop is an excellent way to iterate through the elements of an array. Let's use it to print our friends. To print a specific element of an array, we specify its index:

```js
let friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia"];

console.log(friends[0]);
console.log(friends[1]);
console.log(friends[2]);
console.log(friends[3]);
....
```
However, there are two problems. Firstly, it is not very efficient. Secondly, what if we don't know the number of elements on the list and how many times we need to repeat the same code?

Let's try using a `for` loop:

counter initialization - the first position in the list has an index of 0, so we start counting from 0: `let i = 0;`

counter end - we repeat the loop until it goes through all the elements in the array. We determine the number of elements using the `length` property. So, we repeat the loop as long as the counter is less than the number of friends: `i < friends.length`

counter increment/decrement - after each iteration, we move on to the next person, so we increase the counter by 1: `i += 1;`

```js
let friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia"];
for (let i = 0; i < friends.length; i += 1) {
    console.log(friends[i]);
}
```

Let's practice this again by returning to our message. Let's say we want to personalize it and display something like:

"Hi Michał! We are happy to welcome you to girls.js!"

To achieve this, we just need to add the missing greeting text to our previous loop:

```js
let friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania","Kasia"];
for(let i = 0; i < friends.length; i+=1) {
    console.log("Hi " + friends[i] +"! We are happy to welcome you to girls.js!");
}
```

### Task:

Using a `for` loop, make the console display on girls.js a greeting message for every person in your "group" array. The text should be as follows: "Hi \[name\]! We are happy to welcome you to girls.js!"

### Task:

Using the loop, find and list all the vowels from the sentence: 

"Nad rzeczką opodal krzaczka, mieszkała kaczka-dziwaczka, lecz zamiast trzymać się rzeczki, robiła piesze wycieczki."

(it's a polish song for kids - not so rhyming translation: "Above the river near the bush, there lived a quack duck, but instead of sticking to the river, she made hikes.")

Hint1: Polish vowels are: A, E, I, O, U (Ó), Y, Ą, Ę

Hint2: the string can be treated as an array of characters ;-\)

