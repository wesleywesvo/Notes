# Constructors Overview

### - Constructor functions create and return an object instance.

```javascript
function Person(name, age) {
	this.age = age;
	this.name = name;
}

var Wesley = new Person('Wesley', 23);
console.log(Wesley);
```
