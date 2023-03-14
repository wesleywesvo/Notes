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
