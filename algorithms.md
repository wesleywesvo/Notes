# Some Sorting Algorithms

## Bubble Sort

```javascript
function BubbleSort(list) {
	let min, max;

	for (let i = 0; i < list.length; i++) {
		for (let j = 0; j < list.length; j++) {
			min = list[j];
			max = list[j + 1];

			if (min > max) {
				list[j] = max;
				list[j + 1] = min;
			}
		}
	}

	return list;
}
```

### \*Compares each value to its adjacent value and swaps if necessary.

## Selection Sort

```javascript
function SelectionSort(list) {
	let min, temp;

	for (let i = 0; i < list.length; i++) {
		//assume list[i] is the minimum value
		//traverse array to find actual minimum
		for (let j = i + 1; j < list.length; j++) {
			if (list[j] < list[i]) {
				temp = list[j];
				list[j] = list[i];
				list[i] = temp;
			}
		}
	}

	return list;
}
```

### \* The outer loop is the index of the value assumed to be the minimum

### \* The inner loop is the index of the value to be compared
