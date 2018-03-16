### Value Types

#### Number

1. Numeric value types are numbers
2. Each Number is 64 bit long
3. The actual maximum whole number that can be stored is in the range of 9 quadrillion (15 zeros)
4. For very big or very small numbers, use scientific notation by adding an *e* (for *exponent*), followed by the exponent of the number.
5. Remainder’s ('%') precedence is the same as that of multiplication and division referred modulo
6. Three special Values considered numbers but behave differently in js.
   - Infinity
   - -Infinity
   - NaN (operations that don't yield meaningful result)

#### Strings

1. single quotes, double quotes, or backticks can be used to mark strings, as long as the quotes at the start and the end of the string match.
2. whenever a backslash (`\`) is found inside quoted text, it indicates that the character after it has a special meaning. This is called *escaping* the character
3. JavaScript’s representation uses 16 bits per string element
4. Strings cannot be divided, multiplied, or subtracted, but the `+` operator *can* be used on them. It does not add, but it *concatenates*
5. Backtick quoted strings are called template literals
   1. eg `half of 100 is ${100 / 2}`
   2.  inside `${}` in a template literal, its result will be computed, converted to a string, and included at that position
   3. The example produces “*half of 100 is 50*”.

#### Boolean

true and false

[^NaN]: There is only one value in JavaScript that is not equal to itself, and that is NaN (“not a number”).

### Operators

#### Logical Operators

1. and (&&)
2. or (||)
3. not ( ! )
4. Comparison operators(<, <=, >, >=, ==, ===)

Operator precedence ( || < && < comparison ops)

#### Empty Values

used to denote the absence of a *meaningful* value

1. null
2. undefined

### Automatic Type Conversion

```javascript
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("five" * 2)
// → NaN
console.log(false == 0)
// → true
```

The `null` in the first expression becomes `0`, and the `"5"` in the second expression becomes `5` (from string to number). 

In the third expression, `+` tries string concatenation before numeric addition, so the `1` is converted to `"1"` (from number to string).

> The rules for converting strings and numbers to Boolean values state that `0`, `NaN`, and the empty string (`""`) count as `false`, while all the other values count as `true`. Because of this, expressions like `0 == false` and `"" == false` are also true. When you do *not* want any automatic type conversions to happen, there are two additional operators: `===` and `!==`. The first tests whether a value is *precisely* equal to the other, and the second tests whether it is not precisely equal.

### Short-circuiting of logical operators

Logical and & or operators in js are lazy i.e they will not evaluate remaining expression if the output is determined by only evaluating first few operands. This is called *short-circuit evaluation*