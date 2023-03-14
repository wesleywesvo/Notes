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

---

## Closure example

```javascript
function createObjectWithClosures() {
	let value = 0;

	/*
    function oneIncrementer() {
        value += 1;
    }
    function tensIncrementer() {
        value += 10;
    }
    function getValue() {
        return value;
    }
    function setValue(newNum) {
        value = newNum;
    }

    return {
        oneIncrementer: oneIncrementer,
        tensIncrementer: tensIncrementer,
        getValue: getValue,
        setValue: setValue,
    };
    */
	return {
		oneIncrementer() {
			value += 1;
		},
		tensIncrementer() {
			value += 10;
		},
		getValue() {
			return value;
		},
		setValue(newNum) {
			value = newNum;
		},
	};
}

let obj = createObjectWithClosures();
obj.oneIncrementer(); // value == 1
obj.tensIncrementer(); // value == 11
obj.setValue(7.5); // value == 7.5
```

```javascript
function once(func) {
	let counter = 0;

	return function () {
		if (counter++) {
			return 'the function has already been called...';
		}
		return func();
	};
}

function sayGoodbye() {
	return `Goodbye!`;
}

function isItFriday() {
	return `tgif`;
}

let test = once(sayGoodbye);
console.log(test()); //counter = 1; sayGoodbye
test = once(isItFriday); //counter = 0; store function isItFriday() to `test` variable
console.log(test()); //couunter = 1; isItFriday
console.log(test()); //counter = 2; "already called"
```
