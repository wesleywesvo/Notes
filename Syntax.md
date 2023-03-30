# General Function Syntax

## Traditional way

```javascript
function myFunc (argument1, argument2, ...) {
    //do stuff
    return something;
}
```

## Arrow Notation

```javascript
const myFunc = (argument1, argument2, ...) => {
    //do satuff
    return something;
}

const myFunc = (argument1) => {
    //do stuff with argument1
    //having only one argument eliminates the need for a return statement
}
```

## Functions with Unknown Number of Arguments

### \* Method overloading (Java) does not exist in JS

```javascript
function myFunc(x, y) {
	if (y === undefined) {
		//do stuff with x
	}
	return stuff;
}
```

### \* Parameters can be assigned a default value if no argument is passed

```javascript
function myFunc(x, y = 10) {
	return x + y;
}
```

# Objects with Function Properties

```javascript
function setPropsOnObj(obj) {
	obj.x = 7;
	obj.y = 8;
	obj.onePlus = function (num) {
		num += 1;
		return num;
	};
}

const setPropsOnObj = (obj) => {
	obj.x = 7;
	obj.y = 8;
	obj.onePlus = (num) => (num += 1);
};

object = {};
setPropsOnObj(object);
```

# Factory Functions + Methods in Prototype Chain

```javascript
const puppyProto = {
    bark() {
      console.log('Ruff, Ruff');
    },
    sleep() {
      console.log('zzzZZZZZzzzz');
    }
};

function puppyFactory(name, breed) {
	const puppy = Object.create(puppyProto);		//create puppy object with methods in Prototype chain (defined above)
	puppy.name = name;
	puppy.breed = breed;
	return puppy;
}

const zach = puppyFactory('zach, 'beagle');		//create a puppy object
```

# for..of vs for..in

## for ... of loops

### Executes a loop that operates on a sequence of values from an iterable object

### Arrays, Strings, `arguments` object

```javascript
for (let variable of iterable) {
	//statement
}

let arr = ['a', 'b', 'c'];
for (let element of arr) {
	console.log(element); //prints out each element of the array
}
```

## for ... in loops

### Executes a loop that iterates over all enumerable string properties of an object

### Properties created by simple assignment or property initializer are enumerable by default

### Enumerable properties can be visited by Object.keys()

```javascript
for (let property in object) {
	//statement
}

let obj = { a: 1, b: 2, c: 3 };
for (let prop in obj) {
	console.log(prop); //prints out each property in form of a string
}
```
