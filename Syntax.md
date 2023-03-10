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

# General Object Syntax/Methods

#### \* When objects are being compared their reference in memory is being compared

## \* Object.assign(target, source, ..., source)

```javascript
const obj = { location: 'NYC', temperature: 75 };
const copyOfObj = Object.assign({}, obj);
```

#### \* If we compared the two objects, it would be false because Object.assign() creates a new reference in memory

#### \* Object.assign() only copies primitive values, does not copy a property if the property happens to be an object

```javascript
const objToClone = {
	one: 'one',
	two: 'two',
	three: {
		a: 'a',
		b: 'b',
		c: 'c',
	},
};

const clone = Object.assign({}, objToClone);
```

#### \* Property 'three' is an object and is not being copied, but being referenced now
