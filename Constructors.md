# Constructors Overview

### Constructor functions create and return an object instance.

### The `new` operator creates an object and returns the object implicitly.

```javascript
function Person(name, age = 0) {
	this.age = age;
	this.name = name;
	this.sayHello = function () {
		console.log(`Hi, my name is ${this.name}`);
	};
}

var wesley = new Person('Wesley');
console.log(wesley);
console.log(wesley.sayHello());
```

## Create prototype functions for a constructor function

```javascript
function Person(name, age = 0) {
	this.age = age;
	this.name = name;
}

Person.prototype.sayHello = function () {
	return `Hi, I am ${this.name}`;
};
let wesley = new Person('Wesley');
wesley.sayHello();
```
