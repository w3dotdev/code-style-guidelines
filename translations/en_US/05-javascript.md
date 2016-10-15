# Javascript

## Summary

1. [Global](01-global.md)
  1. [Identation](01-global.md#identation)
2. [Commits](02-commits.md)
  1. [English](02-commits.md#english)
  2. [Task number](02-commits.md#task-number)
  3. [Status](02-commits.md#status)
  4. [Message convention](02-commits.md#message-convention)
3. [HTML](03-html.md)
  1. [Syntax](03-html.md#syntax)
  2. [Comments](03-html.md#comments)
  3. [Character Encoding](03-html.md#character-encoding)
  4. [Attribute Order](03-html.md#attribute-order)
  5. [Performance](03-html.md#performance)
  6. [Base Code](03-html.md#base-code)
4. [CSS](04-css.md)
  1. [Syntax](04-css.md#syntax)
  2. [Comments](04-css.md#comments)
  3. [Declaration Order](04-css.md#declaration-order)
  4. [Name](04-css.md#name)
  5. [Performance](04-css.md#performance)
  6. [Media Queries](04-css.md#media-queries)
5. [Javascript](05-javascript.md)
  1. [Syntax](05-javascript.md#syntax)
  2. [Comments](05-javascript.md#comments)
  3. [Variables](05-javascript.md#variables)
  4. [Performance](05-javascript.md#performance)

## Syntax

Always use a semicolon.

```javascript
// Good
const $items = document.querySelectorAll('.items');

// Bad
const $items = document.querySelectorAll('.items')
```

Use single quotes.

```javascript
// Good
let string = 'Default';
const target = $element.getAttribute('data-target');

// Bad
let string = "Default";
const target = $element.getAttribute("data-target");
```

Keep `else` on the same line lock` if`.

```javascript
// Good
if ( true ) {
  ...
} else {
  ...
}

// Bad
if ( true ) {
  ...
}
else {
  ...
}
```

Use space between operators.

```javascript
// Good
for (i = 0; i < 10; i++) {
  ...
}

// Bad
for (i=0;i<10;i++) {
  ...
}
```

Use space outside the `()`, but not inside.

```javascript
// Good
if (condition) {
  statement
}

// Bad
if( condition ){
  statement
}
```

Always use `{}` for conditional blocks.

```javascript
// Good
if (condition) {
  statement
} else if (condition) {
  statement
} else {
  statement
}

// Bad
if (condition) statement;
else if (condition) statement;
else statement;
```

To check equality, always use `===`.

```javascript
// Good
if (foo === 'foo') {
  statement
}

// Bad
if (foo == 'foo') {
  statement
}
```

**[⬆ back to the top](#summary)**

## Comments

Use `//` for single line comment.

```javascript
// Good
// Description

// Bad
/**
 * Description
 */
```

Use the comment from one line above the related code.

```javascript
// Good
// set the default status to true
const status = this._status || true;

// Bad
const status = this._status || true; // set the default status to true
```

Use `/** ... */` para blocos de comentários

```javascript
// Good
/**
 * Description
 * @param {String} Description of the param
 */

// Bad
//
// Description
//
```

You may have comments to share prefix.

- FIXME - a problem that needs to be reviewed
- TODO  - suggestion for a solution to the problem that needs to be implemented

```javascript
// FIXME: shouldn't use a global here
total = 0;

// TODO: total should be configurable by an options param
this.total = 0;
```

A syntax tip to write the reviews is the [JSDuck](https://github.com/senchalabs/jsduck/wiki).

```javascript
/**
 * @class Class name
 * @param {String} Description of the param
 * @extends name of the 
 * Documentation for the class
 */

 /**
 * @event click
 * Documentation for the event
 * @param {String} Description of the param
 */

/**
 * @method Method name
 * Documentation for the method
 * @param {String} Description of the param
 * @return {String} Description of the return
 */

/**
 * @property {Boolean} [property=false]
 * Description
 */

/**
 * @class Class name
 * Documentation for the class
 *
 * @constructor
 * Documentation for the constructor
 * @param {String} Description of the param
 */
```

**[⬆ back to the top](#summary)**

## Variables

Always use `let` or `const` to declare variables. But will result in global variables.

```javascript
// Good
const gallery = new Gallery();

// Bad
gallery = new Gallery();
```

Use the statement `let` or `const` by variable.

```javascript
// Good
const items = getItems();
const name = 'name';
const status = 'open';

// Bad
const items = getItems(),
    name = 'name',
    status = 'open';
```

Group its `const` and then the `let`s.

```javascript
// Good
const status = true;
const items = getItems();
let name;
let i;
let length;

// Bad
let i, len, status,
    items = getItems(),
    status = true;

// Bad
let i;
const items = getItems();
let status;
const status = true;
let len;
```

Create the variables which need them.

```javascript
// Good
function checkName(hasName) {
  if (hasName === 'test') {
    return false;
  }

  const name = getName();

  if (name === 'test') {
    this.setName('');
    return false;
  }

  return name;
}

// Bad - unnecessary function call
function checkName(hasName) {
  const name = getName();

  if (hasName === 'test') {
    return false;
  }

  if (name === 'test') {
    this.setName('');
    return false;
  }

  return name;
}
```

Do not chain variable assignments. By chaining variable assignments, it creates implicit global variables.

```javascript
// Good
(function example() {
  let a = 1;
  let b = a;
  let c = a;
}());

console.log(a); // undefined
console.log(b); // undefined
console.log(c); // undefined

// the same applies for `const`

// Bad
(function example() {
  // JavaScript interprets this as
  // let a = ( b = ( c = 1 ) );
  // The let keyword only applies to variable a; variables b and c become
  // global variables.
  let a = b = c = 1;
}());

console.log(a); // undefined
console.log(b); // 1
console.log(c); // 1
```

Evitar o uso de incrementos e decrementos unários (++, --).

```javascript
// Good
let array = [1, 2, 3];
let num = 1;
let increment = num += 1;
let decrement = num -= 1;

array.forEach((value) => {
  value += 1;
});

// Bad
let array = [1, 2, 3];
let num = 1;
let increment = num ++;
let decrement = -- num;

for(let i = 0; i < array.length; i++){
  let value = array[i];
  ++value;
}
```

**[⬆ back to the top](#summary)**

## Performance

```javascript

```

**[⬆ back to the top](#summary)**
