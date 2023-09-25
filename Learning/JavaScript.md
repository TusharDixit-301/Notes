## Objects in JavaScript

* * *

- **For loop** :

```js
const band ={
    vocals : "Davey",
    guitarist : "Liam",
    drummer : "Robert"
}
for( let job in band){
            console.log("Jobs in  bands: ",band[job])	
    }	
```

- **Object function**:

```js
const band ={
    vocals : "Davey",
    guitarist : "Liam",
    drummer : "Robert"
}
console.log("Keys of object : ", Object.keys(band))
console.log("Keys of object : ", Object.values(band))
```

- **Destructing Object**:

```js
const band ={
    vocals : "Davey",
    guitarist : "Liam",
    drummer : "Robert"
}
const {vocals : artist} = band;
console.log(artist)
```

- **JavaScript classes**
    - Without Parameters

```js
// JavaScript classes
class Pizza {
    constructor() {
        this.crust = 'thin';
        this.size = 'small';
    }
    bake() {
        console.log(`Baking a pizza of size ${this.size} with ${this.crust} crust.`);
    }
}

const myPizza = new Pizza();
myPizza.bake();
```

- - With Parameters

```js
// Javascript classes
class Pizza {
   constructor(topping) {
   	this.crust = 'thin';
   	this.size = 'small';
       this.toppings = topping;
   }
   bake() {
   	console.log(`Baking a pizza of size ${this.size} with ${this.crust} crust of type ${this.toppings}.`);
   }
}

const myPizza = new Pizza("cheese");
myPizza.bake();

```

* * *
## JSON
* * *
JSON are widely used type of data.
```js
// JSON
const myObj = {
	name: 'John',
	age: 30,
	cars: {
		car1: 'Ford',
		car2: 'BMW',
		car3: 'Fiat',
	},
	hobbies: ['music', 'games', 'movies'],
	hello: function () {
		console.log('Hello there!');
	},
};
console.log(myObj);

// JSON.stringify() - convert a JavaScript object into a string
const myJSON = JSON.stringify(myObj);
// When you're converting an object to a JSON.stringify() then properties like functions will be ignored.
console.log(myJSON);
console.log(typeof myJSON);

// JSON.parse() - convert a string into a JavaScript object
const myParse = JSON.parse(myJSON);
console.log(myParse);
console.log(typeof myParse);
```

* * *
## Error Handling 
* * *
- Try, Catch and Finally blocks are being used for the error handling.
- "use strict" is used to imply some basic rules on our JS code. Example , `name = "Dave"` will not be considered as right you have to right, `let name = "Dave"`;
```js
'use strict';
const makeError = () => {
	try {
        // Error constructor is used to throw the error
		throw new Error('Custom Error');
	} catch (err) {
		console.error(err);
	}finally{
        // finally block is always executed
        console.log('finally block');
    }
};
makeError();
```

* * *
## Web Storage API
* * *
 * https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API
 * It is of two types:
    1. Local Storage : It is persistent storage and data is not deleted when browser is closed.
    2. Session Storage : It is temporary storage and data is deleted when browser is closed.
 * Any storage can only store string data. So, we need to convert our array or object into string.
 * We can use JSON.stringify() method to convert array or object into string.
 ```js
 /**
 * Web Storage API 
 * https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API
 * It is of two types:
    1. Local Storage : It is persistent storage and data is not deleted when browser is closed.
    2. Session Storage : It is temporary storage and data is deleted when browser is closed.
*/
const myArray = ['Eat', 'Sleep', 'Code', 'Repeat'];
const myObject = {
	name: 'John Doe',
	age: 25,
	city: 'New York',
	hobbies: ['Eat', 'Sleep', 'Code', 'Repeat'],
};

/**
 * Any storage can only store string data. So, we need to convert our array or object into string.
 * We can use JSON.stringify() method to convert array or object into string.
 */

// Session Storage
sessionStorage.setItem('myArray', JSON.stringify(myArray));
sessionStorage.setItem('myObject', JSON.stringify(myObject));
const myArrayFromSessionStorage = JSON.parse(sessionStorage.getItem('myArray'));
const myObjectFromSessionStorage = JSON.parse(sessionStorage.getItem('myObject'));
console.log(myArrayFromSessionStorage);
console.log(myObjectFromSessionStorage);

// Local Storage
localStorage.setItem('myArray', JSON.stringify(myArray));
localStorage.setItem('myObject', JSON.stringify(myObject));
const myArrayFromStorage = JSON.parse(localStorage.getItem('myArray'));
const myObjectFromStorage = JSON.parse(localStorage.getItem('myObject'));
 ```

* * *
## Modules
* * *
```js
// Modules

// File 1 :
export default playGuitar = () => {
	console.log('Playing 🎸');
};
const playDrums = () => {
	console.log('Playing 🥁');
};
const playPiano = () => {
	console.log('Playing 🎹');
};
export { playDrums, playPiano };

// File 2 :
// default import can be called without {}
import playGuitar from './main.js';
// named import must be called with {}
import { playDrums as Drums, playPiano as Piano } from './main.js';

console.log(playGuitar());
console.log(Drums());
console.log(Piano());
```
But when we are importing the all function in one go then we have to change the name of default export to default. Example :
```js
// Modules

// File 1 :
export default playGuitar = () => {
	console.log('Playing 🎸');
};
const playDrums = () => {
	console.log('Playing 🥁');
};
const playPiano = () => {
	console.log('Playing 🎹');
};
export { playDrums, playPiano };

// File 2 :
// Importing all the functions from main.js
import * as instruments from './main.js';

// console.log(playGuitar());  => this will show error we need to name it as default 
console.log(instruments.default()); // => this will work
console.log(instruments.Drums());
console.log(instruments.Piano());
```

* * *
## Higher Order function
* * *
- Higher order functions are functions which may receive one or more function as argument or they return any functions as a result.
```js
// post.js
export const posts = [
	{
		userId: 1,
		id: 1,
	},
	{
		userId: 1,
		id: 2,
	},
	{
		userId: 2,
		id: 11,
	},
	{
		userId: 2,
		id: 12,
	},

	{
		userId: 3,
		id: 21,
	},
	{
		userId: 3,
		id: 22,
	},
];

```

```js
/**
 *Higher Order Functions
 *Functions that operate on/with other functions.
 *They can:
 *Accept other functions as arguments
 *Return a function
 */
import { posts } from './post';

// 1. forEach
posts.forEach((post) => {
	console.log(post);
});

// 2. filter
const filteredPosts = posts.filter((post) => {
	return post.userId === 1;
});
console.log(filteredPosts);

// 3. map
const mappedPosts = posts.map((post) => {
	return post.id;
});
console.log(mappedPosts);

// 4. reduce
const reducedPosts = posts.reduce((acc, post) => {
    return acc + post.id;
}, 0);
console.log(reducedPosts);


```

* * *
## Fetch API with async & await, promises , thenables and callbacks
* * *
Complete notes : https://wesbos.com/javascript