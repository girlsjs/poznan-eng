---
title: 14. You're an object
layout: post
---

..because everything is an object ;/) It's another data type. It looks like this::

```js
let variable = {
    key1: value1,
    key2: value2,
    key3: value3
}
```

As you can see, it resembles an array. However, in an array, the order of elements is very significant. In the case of objects, the keys are crucial ;\)

If we want to represent a person as an object, we could do it in the following way:

```js
let person = {
    name: 'Natalia',
    age: 27,
    hobby: ['swimming', 'cycling', 'fantasy books']
}
```

To access a specific element of an object, we need to refer to its key, for example:

```js
person.hobby;
```

We can add new elements to an existing object:

```js
person.city = 'Poznań';
console.log(person);
```

We can also delete elements:

```js
delete person.hobby;
```

Sometimes, an object can contain another object:

```js
 let person = {   
    name: 'Natalia',
    age: 27,
    hobby: ['swimming', 'cycling', 'fantasy books'],
    city: 'Poznan',
    family: {
        mom: 'Anna',
        dad: 'Paweł',
        sister: 'Karolina'
    }
}
```

How to display the sister's name?

```js
person.family.sister;
```



