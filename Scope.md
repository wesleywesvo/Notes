```javascript
function sum() {
	const startingValue = Math.floor(Math.random() * 100) + 1;

	return function funcFromSum(num) {
		console.log(`startingValue ${startingValue}`);
		return num + startingValue;
	};
}

const calculateSum = sum();

console.log(calculateSum(22));
console.log(calculateSum(33));
console.log(calculateSum(44));
console.log(calculateSum(55));
```

### The `sum()` function was invoked only one time

### The `startingValue` was assigned when called by `calculateSum`

### Calling `calculateSum` invokes `funcFromSum` and the starting value was stored in `funcFromSum` lexical environment.
