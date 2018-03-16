#### Useful Functions

#### Exercises

```javascript
// Flattening
let a = [[1, 2, 3], [4, 5], [6]]

a.reduce((x, y) => {
  return x.concat(y)
})

// Your Own Loop
const loop = (value, testF, updateF, bodyF) => {
  if (testF(value)) {
    bodyF(value)
    loop(updateF(value), testF, updateF, bodyF)
  }
}

loop(3, n => n > 0, n => n - 1, console.log)

// Everything
const every = (array, test) => {
  for (let elem of array) {
    if (!test(elem)) return false
  }
  return true
}
//**
const everysome = (array, test) => {
  return !array.some(e => !test(e))
}
```

