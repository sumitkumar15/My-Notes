#### Arrays

`let x = [1, 3, 5]`

can access elements as x[0], x[1]

[ y ] - notation evaluates y & then accesses the array element

###### some array methods

```javascript
push pop shift unshift slice indexOf lastIndexOf concat
```

passing `concat` an argument that is not an array, that value will be added to the new array as if it was a one-element array

#### Objects

declaration

```javascript
let obj = {
    wiki : "js"
    "no wiki" : "no js"
}
```

if a property name in curly brace notation isn’t followed by a value, its value is taken from the binding with the same name

properties can be accessed like

`obj.wiki` if literal property name is used

`obj["x"]` here x is evaluated first & then element is accessed

#### Looping 

Another way of looping array

```javascript
for (let elem of arr) {
    console.log(elem)
}
```

#### Rest Parameters

A function can accept any number of arguments if defined like

```javascript
function max(...numbers) {
  let result = -Infinity;
  for (let number of numbers) {
    if (number > result) result = number;
  }
  return result;
}
```

the rest param is bound to an array of all further arguments.

> (...) also works as spread operator
>
> eg: an array can be passed to max() function by spreading elements of array
>
> `let x = [2, 3, 5, 1]`
>
> `console.log(max(...x))`

#### Destructuring

```javascript
// destructuring array
function destruct([a, b, ...c]) {
  console.log(a, b)
}
destruct([1,2,3,4,5])
// 1 2
```

destructuring null or undefined will give an error

```javascript
// destructuring Objects
let {name, a} = {name: "sk", a: 50, b:11}
console.log(name)
// "sk"
```

#### Exercises

```javascript
// The sum of range
const range = (a, b, step = 1) => {
  let arr = []
  if (step > 0) {
    for (let i = a; i <= b; i += step) arr.push(i)
  } else {
    for (let i = a; i >= b; i += step) arr.push(i)
  }
  return arr
}
console.log(range(1, 5))
console.log(range(5, 2, -1))

const sum2 = x => {
  let s = 0
  for (let e of x) s += e
  return s
}

console.log(sum2([1, 2, 3, 4, 5]))

// Reversing An Array
const reverseArray = x => {
  let arr = []
  for (let i = x.length - 1; i >= 0; i--) {
    arr.push(x[i])
  }
  return arr
}

const reverseArrayInPlace = x => {
  for (let i = 0; i < (x.length / 2); i++) {
    let temp = x[i]
    x[i] = x[x.length - 1 - i]
    x[x.length - 1 - i] = temp
  }
  return x
}

// A List
const arrayToList = x => {
  if (x.length === 0) return null
  return {
    value: x[0],
    rest: arrayToList(x.slice(1))
  }
}

const listToArray = x => {
  const arrHelper = (y, acc) => {
    if (y == null) return acc
    return arrHelper(y.rest, acc.concat(y.value))
  }
  return arrHelper(x, [])
}

const prepend = (x, xs) => {
  return {
    value: x,
    rest: xs
  }
}

const nth = (xs, n) => {
  if (n === 0) return xs.value
  return nth(xs.rest, n - 1)
}

//Deep Comparison
const deepEqual = (obj1, obj2) => {
  let t1 = typeof obj1
  let t2 = typeof obj2
  if (t1 !== t2) return false
  if (t1 !== 'object') {
    return obj1 === obj2
  }
  if (obj1 === null && obj2 === null) return true
  let k1 = Object.keys(obj1)
  let k2 = Object.keys(obj2)
  if (k1.length === k2.length) {
    for (let i = 0; i < k1.length; i++) {
      if (!deepEqual(obj1[k1[i]], obj2[k2[i]])) return false
    }
    return true
  }
  return false
}
```

