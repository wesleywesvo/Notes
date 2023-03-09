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

### Compares each value to its adjacent value and swaps if necessary.
