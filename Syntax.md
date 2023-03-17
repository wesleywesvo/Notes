# General Function Syntax

### Traditional way

```javascript
function myFunc (argument1, argument2, ...) {
    //do stuff
    return something;
}
```

### Arrow Notation

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

### Functions with Unknown Number of Arguments

#### \* Method overloading (Java) does not exist in JS

```javascript
function myFunc(x, y) {
	if (y === undefined) {
		//do stuff with x
	}
	return stuff;
}
```

#### \* Parameters can be assigned a default value if no argument is passed

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
