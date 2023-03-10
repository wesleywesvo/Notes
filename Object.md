# General Object Syntax/Methods

#### \* When objects are being compared their reference in memory is being compared

## Object.assign(target, source, ..., source)

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

## Accessing Values

### \- Dot notation: "object'."objectProperty'

### \- Bracket notation: 'object'['property']

### - Bracket notation allows acces to properties by evaluating the variable in the square bracket []

```
value[x] and value.x are not the same
value.x fetches the value from the property named 'x'
value[x] evaluates 'x' in [] to get the property name
```

## Assigning properties

### Standard

```javascript
let wheelTotal = 4;
let color = 'red';
let bike = {
	wheelTotal: 4,
	color: 'red',
	beginPedaling: function () {
		console.log(`pedaling!`);
	},
};
```

### Shorthand

#### - Useful for when the variable name is the desired property name

```javascript
let wheelTotal = 4;
let color = 'red';
let bike = {
	wheelTotal,
	color,
	beginPedaling() {
		console.log(`pedaling!`);
	},
};
```

### Example of creating an object using functions

#### - Using the `function` keyword requires an explicit return statement

```javascript
function createCalculator() {
	return {
		sum: 0,
		value() {
			return this.sum;
		},
		add(num) {
			this.sum += num;
		},
		subtract(num) {
			this.sum -= num;
		},
		clear() {
			this.sum = 0;
		},
	};
}

const createCalculator = () => ({
	sum: 0,
	value() {
		return this.sum;
	},
	add(num) {
		this.sum += num;
	},
	subtract(num) {
		this.sum -= num;
	},
	clear() {
		this.sum = 0;
	},
});

let calc1 = createCalculator();
let calc2 = createCalculator();
```
