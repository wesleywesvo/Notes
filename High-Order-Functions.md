# High-Order Functions

### Functions that return functions

## Small Example

```javascript
const stranger = () => {
	// things is the value the stranger function returns
	return function things() {
		return 'stranger things';
	};
};

stranger(); //outputs the function itself:
//things() {return "stranger things";}

stranger()(); //outputs 'stranger things'
```

### Output: 'Called Value and Other Value'

```javascript
function yourFunctionRunner() {
	let args = Array.from(arguments);
	let str = [];

	for (let i = 0; i < args.length; i++) {
		str += args[i]();
	}
	return str;
}

function callThisFunction() {
	return 'Called Value';
}

function andThisFunction() {
	return ' and Other Value';
}

yourFunctionRunner(callThisFunction, andThisFunction);
```
