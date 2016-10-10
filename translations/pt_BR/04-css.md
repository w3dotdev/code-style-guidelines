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

## Comments

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

## Declaration Order

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

## Name

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

## Performance

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

## Media Queries

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
