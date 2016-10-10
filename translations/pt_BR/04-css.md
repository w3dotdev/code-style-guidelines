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
  1. [HTML Syntax](03-html.md#html-syntax)
  2. [HTML Comments](03-html.md#html-comments)
  3. [HTML Character Encoding](03-html.md#html-character-encoding)
  4. [HTML Attribute Order](03-html.md#html-attribute-order)
  5. [HTML Performance](03-html.md#html-performance)
  6. [HTML Base Code](03-html.md#html-base-code)
4. [CSS](04-css.md)
  1. [CSS Syntax](04-css.md#css-syntax)
  2. [CSS Comments](04-css.md#css-comments)
  3. [CSS Declaration Order](04-css.md#css-declaration-order)
  4. [CSS Name](04-css.md#css-name)
  5. [CSS Performance](04-css.md#css-performance)
  6. [CSS Media Queries](04-css.md#css-media-queries)
5. [Javascript](05-javascript.md)
  1. [Javascript Syntax](05-javascript.md#javascript-syntax)
  2. [Javascript Comments](05-javascript.md#javascript-comments)
  3. [Javascript Variables](05-javascript.md#javascript-variables)
  4. [Javascript Performance](05-javascript.md#javascript-performance)

## CSS Syntax

Use aspas duplas

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

Use um espaço após o seletor 

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

Use um espaço antes do valor da propriedade 

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

Use o ponto e vírgula após cada valor 

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

Use um seletor por linha 

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

Se o seletor tiver apenas uma propriedade, use na mesma linha ( Com espaço antes da propriedade e depois do valor)

```css
/* Good */
.item { color: #fff; }

/* Bad */
.item {
  color:#fff;
}
```

Usar valores hexadecimais em minúsculo e abreviar se puder. 

```css
/* Good */
.item { color: #fff; }

/* Bad */
.item { color: #FFFFFF; }
```

Não especificar a unidade para valor `0`, exceto para a propriedade `rotate`.

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

**[⬆ voltar ao topo](#summary)**

## CSS Comments

Os comentários sempre estarão antes do código a que se refere.

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

**[⬆ voltar ao topo](#summary)**

## CSS Declaration Order

A declaração das propriedades, devem ser em ordem alfabética.

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

**[⬆ voltar ao topo](#summary)**

## CSS Name

Use `camelCase` para nomes compostos

```css
/* Good */
.mainMenu { background: #fff; }

/* Bad */
.mainmenu { background: #fff; }
```

Para fácil leitura, os filhos são identificados com o `-` (hífen). 

```css
/* Good */
.mainMenu { ... }
.mainMenu-list { ... }

/* Bad */
.mainMenu { ... }
.mainMenu_list { ... }
```

Para o nome de modificadores, usamos o `--`. 

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

Escolha nomes que dão significado a função da mesma.

```css
/* Good */
.mainMenu { ... }
.sidebar { ... }

/* Bad */
.mm { ... }
.sb { ... }
```

**[⬆ voltar ao topo](#summary)**

## CSS Performance

Não use IDs

```css
/* Good */
.mainMenu { ... }
.sidebar { ... }

/* Bad */
#mainMenu { ... }
#sidebar { ... }
```

Sempre dê preferência para a orientação a objetos por meio das classes.

```css
/* Good */
.container { ... }
.text { ... }

/* Bad */
div { ... }
p { ... }
```

Não crie complexidade na herança e sempre use classes.

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

Use no máximo 3 elementos, quando for necessário alterar o comportamento de uma classe, por intermédio de outra classe.

```css
/* Good */
.sidebar .mainMenu { ... }
.page.on .mainMenu { ... }

/* Bad */
.page .sidebar .mainMenu a { ... }
```

Eliminar espaços e comentários, no ambiente de produção.

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

**[⬆ voltar ao topo](#summary)**

## CSS Media Queries

Sempre comece o desenvolvimento em `Mobile first`

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

Mantenha as regras para um seletor em dispositos móveis e demais dispositos, sempre juntos.

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

**[⬆ voltar ao topo](#summary)**
