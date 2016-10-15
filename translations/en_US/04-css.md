# CSS

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

Use double quotes.

```css
/* Good */
[type="..."]
[class^="..."]

.item:after {
  content: "";
}

/* Bad */
[type='...']
[class^='...']

.item:after {
  content: '';
}
```

Use a space after the selector.

```css
/* Good */
.item {
  ...
}

/* Bad */
.item{
  ...
}
```

Use a space before the property value.

```css
/* Good */
.item {
  color: #fff;
  margin: 10px;
}

/* Bad */
.item {
  color:#fff;
  margin:10px;
}
```

Use the semicolon after each value.

```css
/* Good */
.item {
  color: #fff;
  margin: 10px;
}

/* Bad */
.item {
  color:#fff;
  margin:10px
}
```

Use a selector per line.

```css
/* Good */
.item,
.box {
  color: #fff;
  margin: 10px;
}

/* Bad */
.item, .box {
  color:#fff;
  margin:10px
}
```

If the switch has only one property, use the same line (with space before and after the property value).

```css
/* Good */
.item { color: #fff; }

/* Bad */
.item {
  color:#fff;
}
```

Use hexadecimal values ​​in tiny and if you can abbreviate.

```css
/* Good */
.item { color: #fff; }

/* Bad */
.item { color: #FFFFFF; }
```

Not specify the drive for value `0`, except for the property `rotate`.

```css
/* Good */
.item {
  margin: 0;
  transform: rotate(0deg);
}

/* Bad */
.item {
  font-size: 0em;
  margin: 0px;
}
```

**[⬆ back to the top](#summary)**

## Comments

The comments before the code will always be referred to.

```css
/* Basic comment */

/**
 * Block comment
 *
 */

/* ==========================================================================
   Section
   ========================================================================== */

/* Sub-section
   ========================================================================== */
```

**[⬆ back to the top](#summary)**

## Declaration Order

The declaration of the property must be in alphabetical order.

```css
/* Good */
.item {
  background: #fff;
  color: #ffcc00;
  margin: 0;
  position: absolute;
}

/* Bad */
.item { 
  margin: 0;
  position: absolute;
  background: #fff;
  color: #ffcc00;
}
```

**[⬆ back to the top](#summary)**

## Name

Use `camelCase` compound names.

```css
/* Good */
.mainMenu { background: #fff; }

/* Bad */
.mainmenu { background: #fff; }
```

For easy reading, the children are identified with the `-` (hífen). 

```css
/* Good */
.mainMenu { ... }
.mainMenu-list { ... }

/* Bad */
.mainMenu { ... }
.mainMenu_list { ... }
```

For the name modifiers, use the `--`. 

```css
/* Good */
.mainMenu {
  background: #fff;
  margin: 10px;
}

.mainMenu--dark { background: #000; }

/* Bad */
.mainMenu { ... }
.mainMenu-dark { ... }
```

Choose names that give meaning its function.

```css
/* Good */
.mainMenu { ... }
.sidebar { ... }

/* Bad */
.mm { ... }
.sb { ... }
```

**[⬆ back to the top](#summary)**

## Performance

Do not use IDs

```css
/* Good */
.mainMenu { ... }
.sidebar { ... }

/* Bad */
#mainMenu { ... }
#sidebar { ... }
```

Always give preference to object orientation through classes.

```css
/* Good */
.container { ... }
.text { ... }

/* Bad */
div { ... }
p { ... }
```

Do not create complexity in the inheritance and always use classes.

```css
/* Good */
.mainMenu-list { ... }
.mainMenu-item { ... }
.mainMenu-text { ... }

/* Bad */
.mainMenu ul { ... }
.mainMenu ul li { ... }
.mainMenu ul .mainMenu-item span { ... }
```

Use a maximum of 3 elements when you need to change the behavior of a class, through another class.

```css
/* Good */
.sidebar .mainMenu { ... }
.page.on .mainMenu { ... }

/* Bad */
.page .sidebar .mainMenu a { ... }
```

Delete spaces and comments in the production environment.

```css
/* Good */
.mainMenu{...} .mainMenu-item{...}

/* Bad */
.mainMenu {
  ...
}

.mainMenu-item {
  ...
}
```

**[⬆ back to the top](#summary)**

## Media Queries

Always start development in `Mobile first`

```css
/* Good */
.mainMenu { ... }

@media (min-width: 768px) {
  .mainMenu { ... }
}

@media (min-width: 992px) {
  .mainMenu { ... }
}

/* Bad */
.mainMenu { ... }

@media (max-width: 767px) {
  .mainMenu { ... }
}
```

Keep the rules to a selector on mobile devices and so too dispositos, always together.

```css
/* Good */
.mainMenu-item { ... }

@media (min-width: 992px) {
  .mainMenu-item { ... }
}

.mainMenu-link { ... }

@media (min-width: 992px) {
  .mainMenu-link { ... }
}

/* Bad */
.mainMenu { ... }
.mainMenu-item { ... }
.mainMenu-link { ... }

@media (min-width: 992px) {
  .mainMenu { ... }
  .mainMenu-item { ... }
  .mainMenu-link { ... }
}
```

**[⬆ back to the top](#summary)**
