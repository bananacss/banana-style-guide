# NodeJS code style guide

> 💛 The [BananaCSS](https://github.com/bananacss/bananacss) NodeJS code style guide.

## Table of contents

- [Indentation](#indentation)
  - Tab indentation:small_blue_diamond:
- [Newlines](#newlines)
  - UNIX-style newlines
- [Naming Conventions](#naming-conventions)
  - Avoid single letter names
  - lowerCamelCase:small_blue_diamond:
- [Semicolons](#semicolons)
  - Always use semicolons:small_blue_diamond:
- [Quotes](#quotes)
  - Single quotes:small_blue_diamond:
- [Operators](#operators)
  - The === operator:small_blue_diamond:
  - Spaces for separate operators:small_blue_diamond:
- [Line length](#line-length)
  - 80 characters:small_blue_diamond:
- [References](#references)
  - const:small_blue_diamond:
  - let:small_blue_diamond:
  - One const or let per declaration statement
- [Object](#object)
  - Literal syntax:small_blue_diamond:
  - x
- [Array](#array)
  - Literal syntax:small_blue_diamond:
  - x
- [Functions](#functions)
  - Function declarations:small_blue_diamond:
  - Arrow function notation:small_blue_diamond:
- [New lines](#new-lines)
  - Parentheses () and commas
  - Method chaining
- [Braces and Linebreaks](#braces-and-linebreaks)
  - Braces with all blocks
  - Multi-line blocks with if and else:small_blue_diamond:
- [Descriptive conditions](#descriptive-conditions)
  - Descriptively named for non-trivial conditions
- [Ternary operator](#ternary-operator)
  - Split it up into multiple lines instead
- [Comments](#comments)
  - Write comments that explain higher level mechanisms
  - Don't use comments to trivial things

:small_blue_diamond: == Covered by ESLint rules.

<hr>

### Indentation

*The unit of indentation is 2 spaces.*

**ESLint:** [indent](http://eslint.org/docs/rules/indent)

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

<hr>

### Newlines

*Use UNIX-style newlines (\n), and a newline character as the last character of a file.*

<hr>

### Naming Conventions

*Avoid single letter names. Be descriptive with your naming.*

```js
// bad
function q() {
  // statements
}
```

```js
// good
function query() {
  // statements
}
```

*Use lowerCamelCase*

**ESLint:** [camelcase](http://eslint.org/docs/rules/camelcase.html)

```js
// Bad
let is_cached;
```

```js
// Good
let isCached;
```

<hr>

### Semicolons

*Always use semicolons.*

**ESLint:** [semi](http://eslint.org/docs/rules/semi.html)

```js
// Bad
let foo
```

```js
// Good
let foo;
```

<hr>

### Quotes

*Use single quotes*

**ESLint:** [quotes](http://eslint.org/docs/rules/quotes.html)

```js
// Bad
const foo = "bar";
```

```js
// Good
const foo = 'bar';
```

<hr>

### Operators

*Use the === operator*

**ESLint:** [eqeqeq](http://eslint.org/docs/rules/eqeqeq.html)

```js
// Bad
const foo = "bar";

if (foo == 45) {
  // statements
}
```

```js
// Good
const foo = 'bar';

if (foo === 45) {
  // statements
}
```

*Use spaces for separate operators*

**ESLint:** [space-infix-ops](http://eslint.org/docs/rules/space-infix-ops.html)

```js
// Bad
let foo=4+5;
```

```js
// Good
let foo = 4 + 5;
```

<hr>

### Line length

*Avoid lines longer than 80 characters.*

**ESLint:** [max-len](http://eslint.org/docs/rules/max-len)

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

<hr>

### References

*Use const for all of your references; avoid using var.*

**ESLint:** [prefer-const](http://eslint.org/docs/rules/prefer-const.html) and [no-const-assign](http://eslint.org/docs/rules/no-const-assign.html)

```js
// bad
var foo = "bar";
var foo = "bar";
```

```js
// good
const foo = 'bar';
const foo = 'bar';
```

*If you must reassign references, use let instead of var.*

**ESLint:** [no-var](http://eslint.org/docs/rules/no-var.html)

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

*Declare one const or let per declaration statement*

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

<hr>

### Object

*Use the literal syntax for object creation.*

**ESLint:** [no-new-object](http://eslint.org/docs/rules/no-new-object.html)

```js
// bad
const foo = new Object();
```

```js
// good
const foo = {};
```

*x*

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

<hr>

### Array

*Use the literal syntax for array creation.*

**ESLint:** [no-array-constructor](http://eslint.org/docs/rules/no-array-constructor.html)

```js
// bad
const foo = new Array();
```

```js
// good
const foo = [];
```

*x*

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

<hr>

### Functions

*Use function declarations instead of function expressions.*

**ESLint:** [func-style](http://eslint.org/docs/rules/func-style)

```js
// bad
const foo = function () {
};
```

```js
// good
function foo() {
}
```

*When you must use function expressions (as when passing an anonymous function), use arrow function notation.*

**ESLint:** [prefer-arrow-callback](http://eslint.org/docs/rules/prefer-arrow-callback.html)

```js
// bad
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});
```

```js
// good
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
```

<hr>

### New lines

*Parentheses () and commas , are not followed by indented children on new lines.*

```js
// Bad
foo.bar(
  'string',
  () => {
    tatements
  }
);
```

```js
// Good
foo.bar('string', () => {
  statements
});
```

*Method chaining*

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

<hr>

### Braces and Linebreaks

*Use braces with all blocks.*

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

*If you're using multi-line blocks with if and else, put else on the same line as your if block's closing brace.*

**ESLint:** [brace-style](http://eslint.org/docs/rules/brace-style.html)

```js
// bad
if (condition) {
  // statements
}
else {
  // statements
}
```

```js
// good
if (condition) {
  // statements
} else {
  // statements
}
```

<hr>

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

<hr>

### Ternary operator

*The ternary operator should not be used on a single line. Split it up into multiple lines instead.*

```js
// Bad
const foo = (condition) ? 1 : 2;
```

```js
// Good
const foo = (condition)
  ? 1
  : 2;
```

<hr>

### Comments

*Try to write comments that explain higher level mechanisms or clarify difficult segments of your code.*

```js
// Bad

const foo = "var(--bar)";

// Regexp
if (foo.replace(/var\(/, "").replace(/\)/, "") === "--bar") {
  // statements
}
```

```js
// Good

let foo = 'var(--bar)';

let value = foo
              .replace(/var\(/, '') // Remove the 'var('
              .replace(/\)/, ''); // Remove the ')'

if (foo === '--bar') {
  // statements
}
```

*Don't use comments to trivial things.*

```js
// Bad

// Create the AST
const ast = css.parse('.a{color:#000;}');
```

```js
// Good

const ast = css.parse('.a{color:#000;}');
```

<hr>

## References

Project inspired by [idiomatic.js](https://github.com/rwaldron/idiomatic.js), [Node.js Style Guide](https://github.com/felixge/node-style-guide), [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) and [Zeno Rocha Coding Style](https://github.com/zenorocha/my-coding-style).

<hr>

## License

[MIT License](https://github.com/bananacss/banana-style-guide/blob/master/LICENSE.md) © [Afonso Pacifer](http://afonsopacifer.com/)
