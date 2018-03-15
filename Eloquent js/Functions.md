#### Functions

Defining 

```javascript
const add = function (x , y) {
  return x + y
};
```

```javascript
function add (x , y) {
  return x + y
}
```

In second type of functions definition the function can be called before it is defined in the program.

Functions that do not return explicitly return *undefined*

All bindings from blocks *around* it are visible—both those in 
blocks that enclose it and those at the top level of the program. This 
approach to binding visibility is called *lexical scoping*.

### Arrow Functions

```javascript
const power = (base, exponent) => {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
};
```

For single param the parenthesis can be omitted around parameter list.

Arrow functions were added in 2015

### Optional Arguments

Functions are allowed to take less or more than the defined arguments.

If more args are provided they are ignored & if less are given then remaining args values are set to undefined.

An argument can have default value if value not provided. eg

```javascript
function power(base, exponent = 2) {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
}
```

### Closure

being able to reference a specific instance of a local binding in an enclosing scope—is called *closure*. A function that *closes over* some local bindings is called *a* closure.

```javascript
function multiplier(factor) {
  return number => number * factor;
}

let twice = multiplier(2);
console.log(twice(5));
// → 10
```

In the example, `multiplier` is called, and creates an environment in which its `factor` parameter is bound to 2. The function value it returns, which is stored in `twice`, remembers this environment. So when that is called, it multiplies its argument by 2.

#### Exercises

```javascript
const min = (x, y) => {
  return x < y ? x : y
}
console.log(min(-8, 7))

const isEven = function (n) {
  if (n < 0) n = -n
  if (n === 0) return true
  else if (n === 1) return false
  return isEven(n - 2)
}

console.log(isEven(-1))

const countChar = (s, x) => {
  let counter = 0
  for (let i = 0; i < s.length; i++) {
    if (s[i] === x) counter++
  }
  return counter
}

const countBs = s => {
  return countChar(s, 'B')
}

console.log(countBs('skcjowBcibbBBBcios'))
console.log(countChar("kakkerlak", "k"));

```

