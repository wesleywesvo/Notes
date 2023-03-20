# Classes

### Old constructor syntax

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

### Can define constructors using the `class` keyword

### Allows creation of prototype methods without calling Constructor.prototype

```javascript
class Person {
	//define the constructor method
	constructor(name, age = 0) {
		this.age = age;
		this.name = name;
	} //no need for a comma here

	//define prototype methods
	sayHello() {
		return `Hi, me ${this.name}`;
	}

	changeAge(newAge) {
		this.age = newAge;
	}
}

//invoke class same way as a normal constructor
let wesley = new Person('Wesley', 23);
wesley.sayHello();
```

# Subclasses

## Using the `call()` method to reference what `this` is

### Simple example below

```javascript
let person = { first: 'Cody', last: 'TheAdmin' };

function greet(greeting) {
	console.log(`${greeting} ${this.first} ${this.last}!`);
}

//if greet() is invoked normally, there was no argument in `greeting`
greet.call(person); //"undefined Cody TheAdmin!
//invoke greet() with proper arguments:
//greet(`the object that `this` should reference`, following arguments defined in the function)
greet.call(person, 'Hello'); //"Hello Cody TheAdmin!"
```

## Using call() with constructors

```javascript
function GithubUser(username, billingPlan = 'free') {
	this.username = username;
	this.billingPlan = billingPlan;
	this.repositories = [];
}
//GithubUser prototype method
GithubUser.prototype.editBillingPlan = function (newPlan) {
	this.billingPlan = newPlan;
};

//**  GithubAdminUser is a subclass of GithubUser  **//
function GithubAdminUser(username) {
	//`this` references GithubAdminUser
	//then it will invoke constructor GithubUser with (username, 'paid') args
	//`this` in the GithubUser constructor will reference GithubAdminUser
	GithubUser.call(this, username, 'paid');
	this.adminAccess = true;
}

//AdminUser's internal prototype methods should share the same methods as GithubUser
GithubAdminUser.prototype = Object.create(GithubUser.prototype);
GithubAdminUser.prototype.constructor = GithubAdminUser; //constructor

//AdminUser's prototype methods
GithubAdminUser.prototype.updatePermissions = function () {};
GithubAdminUser.prototype.deleteUser = function () {};

const user = new GithubAdminUser('admin');
// user prototype methods == `updatePermissions(), deleteUser()`
// user internal prototype method == GithubUser methods == `editBillingPlan()`
console.dir(user);
```

![Image](https://github.com/wesleywesvo/Notes/blob/main/Images/Subclass%20visual.png)

## Using `class`, `extends`, and `super` keyword
