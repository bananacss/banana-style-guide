# NodeJS code style guide

> 💛 The [BananaCSS](https://github.com/bananacss/bananacss) NodeJS code style guide.

## Table of contents

- [Indentation](#indentation)
- [Whitespace](#whitespace)
- [Semicolons](#semicolons)
- [Quotes](#quotes)
- [Line length](#line-length)
- [References](#references)
- [Object](#object)
- [Array](#array)
- [Braces and Linebreaks](#braces-and-linebreaks)
- [Descriptive conditions](#descriptive-conditions)
- [Ternary operator](#ternary-operator)
- [Method chaining](#method-chaining)

<hr>

### Indentation

The unit of **tab** indentation is 2 spaces.

```js
// Bad
if (condition) {
// statements
}
```

```js
// Good
if (condition) {
  // statements
}
```

### Newlines

*Use UNIX-style newlines (\n), and a newline character as the last character of a file.*

### Semicolons

*Always use semicolons.*

```js
// Bad
let foo
```

```js
// Good
let foo;
```

### Quotes

*Use single quotes*

```js
// Bad
const foo = "bar";
```

```js
// Good
const foo = 'bar';
```

### Line length

*Avoid lines longer than 80 characters.*

```js
// bad
const exampleMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';
```

```js
// good
const exampleMessage = 'This is a super long error that was thrown because ' +
  'of Batman. When you stop to think about how Batman had anything to do ' +
  'with this, you would get nowhere fast.';
```

### References

*const*

```js
// bad
var foo = "bar";
var foo = "bar";
```

```js
// good
const foo = "bar";
const foo = "bar";
```

*let*

```js
// bad
var count = 1;
if (condition) {
  count += 1;
}
```

```js
// good, use the let.
let count = 1;
if (condition) {
  count += 1;
}
```

*Declare one variable per declaration statement*

```js
// Bad
const foo = require('./bar'),
      foo = require('./foo');
```

```js
// Good
const foo = require('./bar');
const foo = require('./foo');
```

### Object

```js
// bad
const foo = new Object();
```

```js
// good
const foo = {};
```

```js
// bad
const foo = {"good": 'code'
        , is generally: 'pretty'
        };
```

```js
// Good
const foo = {
  good: 'code',
  'is generally': 'pretty',
};
```

### Array

```js
// bad
const foo = new Array();
```

```js
// good
const foo = [];
```

```js
// Bad
const foo = [
  'hello', 'world'
];
```

```js
// Good
const foo = ['hello', 'world'];
```

### Braces and Linebreaks

*Always have spaces, braces and span multiple lines.*

```js
// Bad
if(condition) doSomething();

while(condition) iterating++;
```

```js
// Good
if (condition) {
  // statements
}

while (condition) {
  // statements
}

```

### Descriptive conditions

*Any non-trivial conditions should be assigned to a descriptively named variable or function:*

```js
// Bad
if (password.length >= 4 && /^(?=.*\d).{4,}$/.test(password)) {
  // statements
}
```

```js
// Good
const isValidPassword = password.length >= 4 && /^(?=.*\d).{4,}$/.test(password);

if (isValidPassword) {
  // statements
}
```

### Ternary operator

*The ternary operator should not be used on a single line. Split it up into multiple lines instead.*

```js
// Bad
var foo = (condition) ? 1 : 2;
```

```js
// Good
var foo = (condition)
  ? 1
  : 2;
```

### Method chaining

```js
// Bad
user
.findOne({ name: 'foo' })
.populate('bar')
.exec(function(err, user) {
  return true;
});

// Bad
user.findOne({ name: 'foo' })
  .populate('bar')
  .exec(function(err, user) {
    return true;
  });
```

```js
// Good
user
  .findOne({ name: 'foo' })
  .populate('bar')
  .exec(function(err, user) {
    return true;
  });
```

## References

Project inspired by [idiomatic.js](https://github.com/rwaldron/idiomatic.js), [Node.js Style Guide](https://github.com/felixge/node-style-guide), [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) and [Zeno Rocha Coding Style](https://github.com/zenorocha/my-coding-style).

<hr>

## License

[MIT License](https://github.com/bananacss/banana-style-guide/blob/master/LICENSE.md) © [Afonso Pacifer](http://afonsopacifer.com/)
