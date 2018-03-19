#### Encapsulation

It is common to put an underscore (`_`) character at the start of property names to indicate that those properties are private.

Separating interface from implementation is called encapsulation.

#### Methods

Methods are properties that hold function values

```javascript
let rabbit = {}
rabbit.speak = function(line) {
    console.log(`Rabbit says ${line}`)
}
```

When a function is called as a method—looked up as a property and immediately called, as in `object.method()`—the binding called `this` in its body automatically points at the object that it was called on.

We can use a functions's call method, which takes this value as first argument & treats further arguments as normal parameters.

> Arrow functions do not bind their own this, but can see the this binding of scope around them.

#### Prototypes

In addition to their set of properties, most objects also have a *prototype*. A prototype is another object that is used as a fallback source of properties.

> Many objects don’t directly have `Object.prototype` as their prototype, but instead have another object, which provides its own default properties. Functions derive from `Function.prototype`, and arrays derive from `Array.prototype`

You can use `Object.create` to create an object with a specific prototype.

```javascript
let protoRabbit = {
  speak(line) {
    console.log(`The ${this.type} rabbit says '${line}'`);
  }
};
let killerRabbit = Object.create(protoRabbit);
killerRabbit.type = "killer";
killerRabbit.speak("SKREEEE!");
// → The killer rabbit says 'SKREEEE!'
```

#### Class Notation

JavaScript classes are constructor functions with a prototype property

```javascript
class Rabbit {
  constructor(type) {
    this.type = type;
  }
  speak(line) {
    console.log(`The ${this.type} rabbit says '${line}'`);
  }
}

let killerRabbit = new Rabbit("killer");
let blackRabbit = new Rabbit("black");	
```



`class` can be used both in statement and in expression 
positions. When used as an expression, it doesn’t define a binding, but 
just produces the constructor as a value. You are allowed to omit the 
class name in a class expression.

```javascript
let object = new class { getWord() { return "hello"; } };
console.log(object.getWord());
// → hello
```

#### Maps

A *map* is a data structure that associates values with other values

plain objects derive from`Object.prototype` using plain objects as maps is dangerous

it is possible to create objects with *no* prototype. If you pass `null` to `Object.create`, the resulting object will not derive from `Object.prototype`, and can safely be used as a map

JavaScript comes with a class called `Map` that is written for this exact purpose

```javascript
let ages = new Map();
ages.set("Boris", 39);
ages.set("Liang", 22);
ages.set("Júlia", 62);

console.log(`Júlia is ${ages.get("Júlia")}`);
// → Júlia is 62
console.log("Is Jack's age known?", ages.has("Jack"));
// → Is Jack's age known? false
```

provides set get & has as part of interface of Map Object

#### 

