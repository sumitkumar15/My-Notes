#### Binding

`let caught = 5 * 5`

1. This statement defines a binding caught.

2. Empty binding returns `undefined`

3. A single `let` statement may define multiple bindings. The definitions must be separated by commas `let one = 1, two = 2;`

4. binding using var & const

   1. ```javascript
      var name = "Ayda";
      const greeting = "Hello ";
      ```

      const defines a constant value binding & cannot be reassigned

#### Binding Names

1. any unreserved word in js

2. must not start with digit

3. can include ($) & ( _ ) but no other special characters

4. list of reserved words & keywords

5. may not contain spaces

   1. ```
      break case catch class const continue debugger default
      delete do else enum export extends false finally for
      function if implements import interface in instanceof let
      new package private protected public return static super
      switch this throw true try typeof var void while with yield
      ```

      ​

### Exercises

###### #Looping a triangle

```javascript
let s = '#'
for (let i = 0; i < 7; i++) {
  console.log(s)
  s += '#'
}
```

###### #FizzBuzz

```javascript
for (let i = 1; i <= 100; i++) {
  if (i % 3 === 0) {
    console.log('Fizz')
  } else if (i % 5 === 0) {
    console.log('Buzz')
  } else console.log(i)
}

for (let i = 1; i <= 100; i++) {
  if (i % 3 === 0 && i % 5 === 0) {
    console.log('FizzBuzz')
  } else if (i % 3 === 0) {
    console.log('Fizz')
  } else if (i % 5 === 0) {
    console.log('Buzz')
  } else console.log(i)
}
```



###### #Chess board

```javascript
function chBoard (n) {
  let str = ''
  for (let i = 0; i < n; i++) {
    if (i % 2 === 0) {
      for (let j = 0; j < n; j++) {
        if (j % 2 === 0) str = str + ' '
        else str += '#'
      }
      str += '\n'
    } else {
      for (let j = 0; j < n; j++) {
        if (j % 2 === 0) str = str + '#'
        else str += ' '
      }
      str += '\n'
    }
  }
  return str
}

console.log(chBoard(8))
```

