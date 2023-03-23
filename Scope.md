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

# Global/Local

### Priority of scope chain is inner scope > outer scope (global scope is read last)

### Reading a variable will climb up the scope chain if undefined

```javascript
var a = 1;

function f1() {
	var b = 2;
	function f2() {
		console.log(a, b);
	}

	return f2;
}

var f2 = f1();
var b = 3;

function f3() {
	var a = 5;
	f2();
}

f3();
```

### Calling `f3()` calls the function `f2()` which is `console.log(a, b)`

### The value of `a` is the variable declared outside of `f1` and `f3` - the global scope which is `1` in this case

### The value of `b` is the variable declared in the local scope of `f1` and in this case it is `2`.
