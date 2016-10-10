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

Sempre use ponto e vírgula 

```javascript
// Good
const $items = document.querySelectorAll('.items');

// Bad
const $items = document.querySelectorAll('.items')
```

Use aspas simples

```javascript
// Good
let string = 'Default';
const target = $element.getAttribute('data-target');

// Bad
let string = "Default";
const target = $element.getAttribute("data-target");
```

Mantenha o `else` na mesma linha do fechamento do `if`.

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

Use espaço entre os operadores.

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

Use espaço fora dos `()`, mas não dentro.

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

Sempre use `{}` para os blocos condicionais.

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

Para checar a igualdade, sempre use `===`;

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

**[⬆ voltar ao topo](#summary)**

## Comments

Use `//` para comentário de uma linha

```javascript
// Good
// Description

// Bad
/**
 * Description
 */
```

Use o comentário de uma linha acima do código referente. 

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

Pode ter comentários com prefixo de ação.

- FIXME - um problema que precisa ser revisto
- TODO  - sugestão de uma solução para o problema que precisa ser implementado

```javascript
// FIXME: shouldn't use a global here
total = 0;

// TODO: total should be configurable by an options param
this.total = 0;
```

Uma sugestão de sintaxe para escrever os comentários é o do [JSDuck](https://github.com/senchalabs/jsduck/wiki).

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

**[⬆ voltar ao topo](#summary)**

## Variables

## Performance
