## Exercise 1

a.) O(n), it takes n iterations for `a + n^2` to converge with `n^3`

b.) O(log n), `i` is cut in half each iteration

c.) O(sqrt(n)), inner loops are constant so don't add to the complexity. The `/2` is also constant so it too is disregarded.

d.) O(n log n), inner loop is linear, outer loop is logarithmic since `i` is doubling with each iteration.

e.) O(n^3), inner most loop is constant, so only the outer loops are considered.

f.) O(n), recursive loop runs until `bunnies` equals 0

g.) O(n), worst case scenario you have to go through the entire array.

## Exercise 2

a.) Iterate over the array backwards keeping track of the maximum element in the array and the current maximum difference. If the current item is larger than the previous max element, update the maximum element. If the element is smaller subtract it from the max element and set the max difference to the result if the result is greater than the current max difference. Continue iterating.

```javascript
function findMaxDiff(arr) {
  const n = arr.length;
  let maxElement = arr[n - 1];
  let maxDiff = 0;
  for (let i = n - 2; i > 0; i--) {
    maxElement = arr[i] > maxElement ? arr[i] : maxElement;
    if (maxElement > arr[i]) {
      maxDiff = Math.max(maxDiff, maxElement - arr[i]);
    }
  }
  return maxDiff;
}
```

b.)
