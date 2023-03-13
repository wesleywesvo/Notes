# Useful methods

## Array.prototype.join()

### \* Parameter: specifies a string to separate each array entry

### \* Return: a string with all array elements joined

```javascript
const a = ['wind', 'water', 'fire'];
a.join(); // 'wind,water,fire'
a.join(''); // 'windwaterfire'
```

## Clone array using Array.prototype.slice(start, end)

### \* Parameter: start and end indices of the array

### \* Negative indices -> start from end of array and work backwards

### \* Returns: a new array (different reference in memory)

```javascript
const fruits = ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango'];
const citrus = fruits.slice(1, 3);
// fruits contains ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
// citrus contains ['Orange','Lemon']
```

## Merge array using 'Spread Syntax': ...

```javascript
const arr1 = ['a', 'b', 'c'];
const arr2 = ['d', 'e'];
// the spread operator is used on abc and de
const aToE = [...arr1, ...arr2];
console.log(aToE); // ['a', 'b', 'c', 'd', 'e'];
```

## Unknown number of arguments passed to functions

### - 'arguments' - array=like object inside functions that contains values of the arguments passed to that function

```javascript
function myFunc() {
    //method 1 - using a loop
    let args = [];
    for (let i = 0; i < arguments.length; i++) {
        args.push(arguments[i]);        //store arguments into an array
    }
    //method 2 - Using Array.from()
    let args = Array.from(arguments);   //store arguments into an array
}

myFunc(arg1, arg2, arg3, ...);
```
