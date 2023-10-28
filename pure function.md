1. the function return values are identical for identical arguments
2. the function has no side effects

## Examples
The function return values are identical for identical arguments
```javascript
// Pure function
const sums = (x, y) => x + y

// Function depand on global variable (bad)
let y = 10
const sums = (x) => x + y

// Functoin that mutate global variables (bad)
const arr = [1, 2, 3, 4]
const modifyArr = (arr) =>{
	// mutate array
	arr[0] = 100
}
```
